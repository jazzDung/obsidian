
Em notes lại một số phần còn chưa được giải quyết tốt trong Data warehouse để mn cũng thảo luận thêm nhé ạ:

- Data structure:
    - Các bảng fact_period còn một số vấn đề về dư thừa về các user ko có action, hoặc hiện tại mới có các bảng daily nhưng nhu cầu người dùng muốn linh hoạt xem theo nhiều period khác
    - Phân bổ các bảng về các schema phù hợp
- Chưa chuẩn hoá data quality
- Chưa có cơ chế phân quyền query trong nội bộ team data và các team khác


# Tổ chức datawarehouse

1. Cách tổ chức
	- Dimension modelling: 
	- Schema
		- Theo môi trường: import, staging, intermediate, marts (dwh)
		- Staging -> chuẩn hoá tên trường, múi giờ
		- Intermediate -> Tính toán, transform, chưa đến dữ liệu cuối
		- dwh (mart) -> Thiết kế cho end user
	- Chia quyền
		- Hiện là tất cả mn trong team đều có chung quyền -> Muốn thay đổi quyền theo team
	- Fact
		- fact_: Record nguyên tử
		- fact_period: Tổng hợp theo 1 period (daily, quarterly)
		- fact_acc: 
	- Map
		- Để lưu mối quan hệ giữa 2 entity
	- Naming convention
		- 