## Định nghĩa
- Khi gọi trực tiếp tên bảng -> Khi update tên bảng cần cập nhật ở tất cả các file -> Lâu vãi
- Sources lưu các tên bảng trong file yml
- Sau đó tên các bảng đó sẽ được thể hiện trong Lineage graph
	![[Pasted image 20230410162802.png]]
- Thay vì gọi 
	```sql
	from raw.stripe.payment
	```
	thì gọi 
	```C
	{{source('stripe','payments')}}
	```

## yml file

```yml
version: 2

sources:
  - name: jaffle_shop
    database: raw
    schema: jaffle_shop
    tables:
      - name: orders #table name
		
		# Source freshness block
	    loaded_at_field: _etl_loaded_at
	    freshness:
		    warn_after: {count: 12, period: hour}
		    error_after: {count: 24, period: hour}
		
      - name: customers
      
      - # Test block
        columns:
	      - name: id
		    tests:
			  - unique
			  - not_null
```

## Source freshness
- Kiểm tra độ mới dữ liệu dựa theo trường trong bảng và trả về cảnh báo hoặc lỗi tùy vào config
- loaded_at_field: chọn trường trong bảng để check
	- Lấy max trường này trù đi thời gian hiện tại và so với mốc thời gian trong config


![[Test#Source testing]]
