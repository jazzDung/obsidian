#dbt #command

## Command cho dev
- Khởi tạo và chạy các model
```bash
dbt run #run all model
dbt run --select model_name #run selected model
dbt run --select +model_name #run selected model and downstream models
dbt run --full-refresh #run with refresh for BigQuery, used to auto drop old table/view before create new one
dbt run -s folder_name #run all model in folder models/folder_name 
```

- Test các model, kiểm tra các điều kiện đề ra trong file yml
```bash
dbt test
dbt test -s folder_name #test all model in folder models/folder_name
dbt test --select test_type:generic #test all generic test
dbt test --select test_type:singular #test all singular test
dbt test --select source:source_name #test a specific source
dbt test --select model_name #test a specific model
```

- Chạy + Test combo
```bash
dbt build #Run và test cùng lúc
```

- Tạo documentation cho người ngoài đọc
```bash
dbt docs generate
```

- Hiển thị document và DAG trên dbt core
```bash
dbt docs generate
dbt docs serve
```

- Query dữ liệu từ bảng
```SQL
select * from {{ source('stripe', 'payment')}}
```

- Query dữ liệu từ Model trước
```SQL
select * from {{ ref("stg_orders")}}
```

- Create config block (Override ym; file)
```java
{{
     config( materialized = 'table' )
}}
```

- Kiểm tra source freshness
```bash
[dbt] source freshness
```