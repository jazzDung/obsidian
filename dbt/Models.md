#dbt #bigdata #dataplatform

## Định nghĩa
- Đơn giản là các lệnh select SQL
	- Qua từng bước trong Model, tạo ra các bảng trung gian hoặc Vỉew
	- Qua đó dần dần biến đổi dữ liệu
- Config cách model được xây dựng bằng cái file yml, chứ không phải chọc ngoáy vào SQL

## Naming convention
1. [[Sources]] table
	- Dữ liệu thô được load từ trước
2. Stages [[Models]]
	- Xây dựng 1:1 với bảng
	- Xử lý nhanh, làm sạch bảng
	- stg_name
3. Bảng trung gian (Intermediate table)
	- Model giữa staging và final
	- Luôn được xâu dựng lên trên staging, không xây dựng thẳng lên trên sources table
4. Fact [[Models]]
	- Những thông tin đã hoặc đang xảy ra
	- Chứa các dữ liệu được cập nhật khi có sự kiện xảy ra
	- Ví dụ như model để ghi các order khách hàng chẳng hạn
5. Dimension
	- Các trường thông tin
		- Người, địa điểm, user, công ty, product, khách hàng


## File hierachy
``` console
dbt-learn
├── analysis
├── dbt_modules
├── logs
├── macros
├── models
    └── marts
        └── core
            └── dim_customers.sql  
    └── staging
        └── jaffle_shop
            ├── stg_customers.sql
            └── stg_orders.sql 
    └── tests
        └── assert_positive_total_for_payments.sql
├── snapshots
├── target
├── tests
├── .gitignore
├── dbt_project.yml
└── README.md
```


## Ref
- Khi compile thì IDE tự dịch ref thành bảng địa chỉ
	```SQL
	{{ ref('stg_customers') }}
	-> analytics.dbt_jsmith.stg_customers
	```