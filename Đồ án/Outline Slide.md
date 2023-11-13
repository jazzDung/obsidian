# Introduction <font color="#00b050">1</font>
- Làm animation dữ liệu đi từ 1 đầu vào -> 3, 4 đầu ra, để nhiều màu, sau đó hiện ra tên Financial Data Platform, sau đó mờ hết đằng sau đi và hiện nốt các thông tin còn lại của đồ án

# Analysis / Bài toán / Motivation 
### Nói về các Data Platform khác
- Thiếu khả năng cho người dùng tạo ra các chỉ báo của riêng mình
- Process thu thập dữ liệu cứng nhắc, thiếu đi 1 giao diện thân thiện để quản lý các luồng dữ liệu, thời gian setup 1 luồng dữ liệu mất nhiều thời gian.
- Quản trị dữ liệu kém
- Sử dụng các công cụ cũ, learning curve lớn, cần được maintain bởi Data Engineer, trong khi những người thật sự có hiểu biết nghiệp vụ (BI, BA) biết rõ cần những loại dữ liệu gì thì không biết sử dụng
- Các luồng dữ liệu cần được kích hoạt thủ công, hoặc đặt lịch cơ bản, muốn áp dụng các điều kiện chạy phức tạp hơn thì cần code phức tạp
- Công cụ orchestration chỉ hoạt động như công cụ chạy command line -> Không thực sự quản lý được trạng thái, log của các luồng dữ liệu
- Việc tạo thêm các luồng dữ liệu cho mục đích thử nghiệm, adhoc là cực kỳ khó khắn
- Các công cụ sử dụng không được thiết kế để dễ dàng triển khai trên cloud
- Các data platform cũ được triển khai sử dụng tài nguyên công ty -> Tốn kém và khó duy trì

# Công cụ sử dụng

### PostgreSQL + TimescaleDB
- TimescaleDB tối ưu cho dữ liệu time-series 
### Airbyte
- Cung cấp giao diện thân thiện
- Các connector có sẵn, và hỗ trợ rất nhiều nguồn dữ liệu = Thời gian setup luồng dữ liệu chỉ tính bằng phút
- Khả năng xây dựng connector cho các nguồn dữ liệu chưa hỗ trợ cực nhanh
- Cung cấp khả năng normalize dữ liệu trước khi qua các bước transformation.
### dbt
- Thao tác phần lớn sử dụng SQL, quen thuộc với team BI
- Cực kỳ dễ thực hiện các luồng biển đổi dữ liệu adhoc và có thể chạy luồng đơn lẻ ngay từ máy tính cá nhân
- Built-in test, custom test và package bên thứ 3 đem đến khả năng quản trị dữ liệu cực kì tốt
### Dagster
- Thực sự kiểm soát log và trạng thái của luồng dữ liệu
- Sensor cho phép thiết lập các điều kiện chạy luồng dữ liệu phức tập và context-based hơn

# Viết về những thứ đã implement trong đồ án
### Airbyte
- Tạo connector, nhấn mạnh vào incremental stream
- Nói về khả năng normalize trước khi vào bảng

### dbt

