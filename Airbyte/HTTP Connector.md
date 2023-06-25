- Connector UUID: c15a655 4-e948-497c-b573-aaab716e6651
- Tạo docker image cho connector
```bash
docker build . -t airbyte/source-<name>:dev
```

- Update connector lên db sau docker build
```bash
# Vào repo của docker container
docker exec -ti airbyte-db psql -U docker -d airbyte

# Query để update bảng thông tin connector
UPDATE actor_definition SET public = true WHERE name = ‘{connector_name}’;

# or just
UPDATE actor_definition SET public = true WHERE true;

```

- Khi test connector
```python
# Create virtual enviroment
python -m venv .venv

# Activate venv
source .venv/bin/activate

# Run with config file
python main.py read --config secrets/config.json --catalog integration_tests/configured_catalog.json

```

- Các link API để xem dữ liệu
```python
https://fiin-core.ssi.com.vn/Master/GetListOrganization?language=vi

https://apipubaws.tcbs.com.vn/stock-insight/v1/stock/bars-long-term?ticker=TCB&type=stock&resolution=D&from=1649955600&to=1650560400


```

- Biến đổi input cho lịch sử giá stock
```python
def stock_historical_data (symbol, start_date, end_date):
    """
    This function returns the stock historical daily data.
    Args:
        symbol (:obj:`str`, required): 3 digits name of the desired stock.
        start_date (:obj:`str`, required): the start date to get data (YYYY-mm-dd).
        end_date (:obj:`str`, required): the end date to get data (YYYY-mm-dd).
    Returns:
        :obj:`pandas.DataFrame`:
        | tradingDate | open | high | low | close | volume |
        | ----------- | ---- | ---- | --- | ----- | ------ |
        | YYYY-mm-dd  | xxxx | xxxx | xxx | xxxxx | xxxxxx |
    Raises:
        ValueError: raised whenever any of the introduced arguments is not valid.
    """ 
    fd = int(time.mktime(time.strptime(start_date, "%Y-%m-%d")))
    td = int(time.mktime(time.strptime(end_date, "%Y-%m-%d")))
    data = requests.get('https://apipubaws.tcbs.com.vn/stock-insight/v1/stock/bars-long-term?ticker={}&type=stock&resolution=D&from={}&to={}'.format(symbol, fd, td)).json()
    df = json_normalize(data['data'])
    df['tradingDate'] = pd.to_datetime(df.tradingDate.str.split("T", expand=True)[0])
    df.columns = df.columns.str.title()
    df.rename(columns={'Tradingdate':'TradingDate'}, inplace=True)
    return df

```

-   Step 1: Create the source using the template
-   Step 2: Install dependencies for the new source
-   Step 3: Define the inputs needed by your connector
-   Step 4: Implement connection checking
-   Step 5: Declare the schema of your streams
-   Step 6: Implement functionality for reading your streams
-   Step 7: Use the connector in Airbyte
-   Step 8: Write unit tests or integration tests

## Step 2: Install dependencies for the new source
- Điền các Python dependency cho nguồn ở file setup.py trong trường install_requires
	- Mỗi khi thay đổi dependency cần chạy lại pip install -r requirements.txt

- File main.py dùng để chạy thử connector trong quá trình dev (Nhưng chỉ là chạy bằng Airbyte local, chứ không chạy trên docker)
```console
# from airbyte-integrations/connectors/source-<name>python main.py specpython main.py check --config secrets/config.jsonpython main.py discover --config secrets/config.jsonpython main.py read --config secrets/config.json --catalog sample_files/configured_catalog.json
```

- Chạy thử trên docker

```bash
# First build the container
docker build . -t airbyte/source-<name>:dev

# Then use the following commands to run it
docker run --rm airbyte/source-<name>:dev spec
docker run --rm -v $(pwd)/secrets:/secrets airbyte/source-<name>:dev check --config /secrets/config.json
docker run --rm -v $(pwd)/secrets:/secrets airbyte/source-<name>:dev discover --config /secrets/config.json
docker run --rm -v $(pwd)/secrets:/secrets -v $(pwd)/sample_files:/sample_files airbyte/source-<name>:dev read --config /secrets/config.json --catalog /sample_files/configured_catalog.json
```