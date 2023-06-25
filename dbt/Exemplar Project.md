## Thành phần DAG
- Xanh lá cây: Bảng dữ liệu
- Xanh dương: Model
	- Gắn 1:1 với bảng dứ liệu
	- Thực chất là SQL để biến đổi dữ liệu

## Test
- Sử dụng file yml để config thông tin và các bài test cho model
	- Tên, description
	- Các trường tác động (Có vẻ thế)
	- Các điều kiện cho dữ liệu
		- unique
		- not null

## Deployment
- Nhóm các lệnh lại với nhau thành job, tạo lịch trình chạy
	- Có vẻ giống Airflow