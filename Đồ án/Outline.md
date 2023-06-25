
> [!NOTE]  Độ dài dự kiến
> **55 - 60 trang**


# Chương 1. Giới thiệu đề tài <font color="#f79646">1 - 4</font>

### 1.1 Đặt vấn đề <font color="#f79646">1-1</font>
- Nhu cầu của thị trường
- Nêu ra các bài toán/nhu cầu người dùng chưa được đáp ứng

### 1.2 Mục tiêu và phạm vi đề tài <font color="#f79646">1-2</font>
- Các platform hiện hành và pros & cons của chúng
- Nêu nội dung đồ án và những bài toán /nhu cầu mà đồ án sẽ giải quyết

### 1.3 Định hướng giải pháp <font color="#f79646">1-2</font>
- Miêu tả chung chung về cách hoạt động hệ thống

### 1.4 Bố cục đồ án <font color="#f79646">2-3</font>
- Tóm tắt nội dung của từng chương bên dưới


# Chương 2. Xây dựng nền tảng dữ liệu thị trường chứng khoán <font color="#f79646">4 - 11</font>

### 2.1 Thông tin chung về TTCK Việt Nam <font color="#f79646">4 - 7</font>

**2.1.1 Các khái niệm cơ bản <font color="#f79646">4-5</font>**
- Chứng khoán là gì
- Thị trường chứng khoán là gì
- Các thành phần tham gia TTCK: Nhà phát hành, nhà đầu tư, công ty chứng khoán
- Cổ phiếu là gì
- Chỉ số chứng khoán là gì...

**2.1.2 Khảo sát các ứng dụng nền tảng dữ liệu TTCK tại Việt Nam <font color="#f79646">5 - 7</font>**
- Nói về các platform hiện tại: SSI, VNDIRECT, TCBS: Pros & Cons

### 2.2 Tổng quan về Modern Data Stack <font color="#f79646">7 - 10</font>

**2.2.1 Lí do cho việc sử dụng MDS** <font color="#f79646">7 - 8</font>
- Khả năng kết hợp các cloud-based service và các integration
- Big Data
- ETL -> ELT

**2.2.2 Tổng quan các thành phần MDS** <font color="#f79646">8 - 10</font>
- Ingestion
- Warehouse
- ELT tools
- Orchestration
- Reverse ETL tools
- Business intelligence

### 2.3 Tổng quan thiết kế nền tảng dữ liệu chứng khoán <font color="#f79646">10 - 11</font>

**2.3.1 Tổng quan yêu cầu chức năng <font color="#f79646">10 - 10</font>**
- Nói về yêu cầu ở 3 khía cạnh
	- Tính năng (Người dùng có thể làm gì)
	- Dữ liệu (Thu thập, lưu trữ, xử lý)
	- Giao diện (Các yêu cầu thẩm mỹ)

**2.3.2 Yêu cầu phi chức năng <font color="#f79646">10 - 10</font>**
- Các yêu cầu về trải nghiệm sử dụng của platform

**2.3.3 Thiết kế hệ thống <font color="#f79646">11 - 11</font>**
- Miêu tả các thành phần của platform (Tương ứng với 3 phân hệ đồ án)
	- Thu thập, tổ chức lưu trữ dữ liệu, lên lịch trình tính toán chỉ báo
	- Triển khai Kubernetes
	- Ứng dụng và quản lý nền tảng
	- Mô tả về luồng hoạt động của hệ thống và từng thành phần


# Chương 3. Công nghệ sử dụng <font color="#f79646">11 - 21</font>

### 3.* Các nội dung có chung cho toàn bộ mục công nghệ
- Mục đích sử dụng công cụ
- Pros & Cons của công cụ so với các alternative
- Thành phần tổng quan của hệ thống và vai trò của từng thành phần

### 3.1 Công nghệ nhập dữ liệu - Airbyte <font color="#f79646">11 - 12</font>
- CDK Connector
- Sync mode

### 3.2 Công nghệ lưu trữ dữ liệu - PostgreSQL <font color="#f79646">12 - 14</font>
- Nói về các thành phần của PostgreSQL (Cần tìm hiểu thêm) 
- TimescaleDB

### 3.3 Công nghệ biến đổi dữ liệu - dbt <font color="#f79646">14 - 16</font>
- dbt core
- Models
- Tests
- DAG presentation
- Documentation

### 3.4 Công nghệ lập lịch trình - Dagster <font color="#f79646">16 - 18</font>
- Asset
- Job
- Schedule
- Sensor

### 3.5 Công nghệ đóng gói và triển khai phần mềm - Docker <font color="#f79646">18 - 20</font>
- Docker Image
- Docker Container
- Docker Compose
- Docker Hub

### 3.6 Công cụ lập trình và bổ trợ - Python <font color="#f79646">20 - 21</font>
- Tương tác với DB: **sqlalchemy**
- Gửi Email: **smtplib**
- Có thể sẽ có model ML hoặc các nhu cầu phát sinh thêm lib khác


# Chương 4. Xây dựng phân hệ quản lý và lập trình trình tính toán chỉ báo

### 4.1 Thiết kế luồng thu thập dữ liệu  <font color="#f79646">21 - 25</font>

**4.1.1 Thiết kế connector** <font color="#f79646">21 - 24</font>
- Specification <font color="#f79646">21 - 21</font>
- Schema <font color="#f79646">21 - 22</font>
- Stream và Sub stream <font color="#f79646">22 - 23</font>
- Incremental Sync <font color="#f79646">23 - 24</font>
- Đóng gói thành Docker image và publish trên Docker hub <font color="#f79646">24 - 24</font>

**4.1.2 Setup connector, source, và connection** <font color="#f79646">24 - 25</font>
- Pull connector image và setup
- Setup địa chỉ PostgreSQL làm source
- Tạo các connection

### 4.2 Thiết kế cơ sở dữ liệu <font color="#f79646">25 - 35</font>
- Phân chia schema <font color="#f79646">25 - 25</font>
- Tạo Timescale Hypertable và nén dữ liệu trong các bảng theo trường thời gian <font color="#f79646">25 - 26</font>
- Giải thích ý nghĩa các trường trong bảng <font color="#f79646">26 - 35</font>
- Giải thích các bên tác động vào bảng, và cách sử dụng 1 số dữ liệu quan trọng <font color="#f79646">26 - 35</font>

### 4.3 Thiết kế luồng biến đổi dữ liệu và tính toán chỉ báo <font color="#f79646">35 - 39</font>

**4.3.1 Biến đổi dữ liệu** <font color="#f79646">35 - 37</font>
- Định nghĩa các bảng nguồn (source)
- Định nghĩa các bảng đích dưới dạng (dimension) 
- Xây dựng model hoàn chỉnh từ source -> staging -> dimension
- Xây dựng các model kiểm thử 
- Khởi tạo documentation, DAG

**4.3.2 Tính toán chỉ báo** <font color="#f79646">37 - 39</font>
- Định nghĩa các hàm SQL sử dụng trong việc tính toán
- Giải thích công thức tính các chỉ báo và ý nghĩa của nó 
- Lặp lại quy trình giống 4.3.1

### 4.4 Thiết kế lịch trình thu thập, biến đổi và tính toán dữ liệu <font color="#f79646">39 - 43</font>

**4.4.1 Setup resource** <font color="#f79646">39 - 39</font>
-  Định nghĩa các config, mật khẩu, username cần khởi tạo

**4.4.2 Tạo asset** <font color="#f79646">39 - 41</font>
- Tạo Airbyte asset
- Tạo dbt asset
- Tạo các asset dựa trên hàm python phục vụ các job nhất định

**4.4.3 Tạo job, schedules, sensor** <font color="#f79646">41 - 43</font>
- Cách tạo job, các loại job và sự phụ thuộc giữa các asset trong job (Đặc biệt là job tính toán)
- Sensor, giải thích cách hoạt động các sensor có trong hệ thống
- Cron và cách sử dụng Cron trong schedules.
- Các tính năng kiểm thử job

### **4.5 Trình tự sinh model theo truy vấn người dùng** <font color="#f79646">? - ?</font>

**4.5.1 Tích hợp model người dùng với Dagster** <font color="#f79646">2 trang</font>
- Xác định các dependency asset của model

**4.5.2 Quản lý vòng đời model, thông báo cho người dùng <font color="#f79646">2 trang</font>**
- Định nghĩa các job, sensor dùng cho mục đích quản lý model người dùng
- Định nghĩa các hình thức cảnh báo người dùng khi có nhu cầu

### 4.6 Lập trình đáp ứng yêu cầu phi chức năng <font color="#f79646">43 - 44</font>

**4.6.1 Tốc độ phản hồi** <font color="#f79646">43 - 43</font>
- Miêu tả kích thước dữ liệu
- Nói về tốc độ tính toán tại các giai đoạn trong hệ thống (Thu thập, biến đổi, tính toán chỉ báo, lập lịch trình và khởi tạo model theo truy vấn người dùng)

**4.6.2 Tính chịu lỗi** <font color="#f79646">43 - 44</font>
- Miêu tả tính năng kiểm thử được áp dụng trong từng giai đoạn trong hệ thống


# Chương 5. Thực nghiệm và đánh giá <font color="#f79646">44 - 52</font>

### 5.1 Xây dựng ứng dụng <font color="#f79646">44 - 45</font>

**5.1.1 Thư viện và công cụ sử dụng** <font color="#f79646">44 - 44</font>
- IDE, Quản lý Database
- Quản lý phiên bản
- Virtual Environment cho python
- Đóng gói môi trường (Docker)

**5.1.2 Cấu hình thiết bị** <font color="#f79646">44 - 45</font>
- Liệt kê cấu hình máy cloud

### 5.2 Triển khai <font color="#f79646">45 - 50</font>

**5.2.1 Quá trình triển khai các thành phần** <font color="#f79646">45 - 46</font>
- Liệt kê toàn bộ các nội dung đã triển khai trong đồ án như:
	- Airbyte connector, connection, test
	- dbt model, DAG, test
	- Dagster asset, job, sensor, schedule, DAG, test

**5.2.2 Kết quả nhận được** <font color="#f79646">46 - 47</font>
- Liệt kê các thống kê về hệ thống như:
	- Lượng mã nguồn
	- Dung lượng cài đặt
	- Dung lượng dữ liệu database
	- Thời gian hoàn thành các luồng/job/toàn bộ DAG

**5.2.3 Minh họa chức năng** <font color="#f79646">47 - 50</font>
- Giao diện Airbyte, log sau khi thu thập dữ liệu thành công
- Documentation screen của dbt
- Asset graph, danh sách job và log sau khi chạy job thành công của Dagster

### 5.3 Kiểm thử <font color="#f79646">50 - 52</font>
- Lập bảng, định nghĩa các bài test với hệ thống và kết quả


# Chương 6. Kết luận và hướng phát triển <font color="#f79646">52 - 54</font>

### 6.1 Kết luận <font color="#f79646">52 - 52</font>
- Nói 1 ít về thành phẩm: Các tính năng, pros & cons so với platform hiện hành
- Nói về những thứ đã vận dụng, kiến thức mới học thêm được trong quá trình làm đồ án

### 6.2 Hướng phát triển <font color="#f79646">52 - 53</font>
- Nói xem có làm cái gì để cho đồ án nó phát triển hơn được không

### 6.3 Tài liệu tham khảo <font color="#f79646">53 - 54</font>