Trong 1 bảng tên là user
- Entity type: Là chỉ bảng user
- Entity: Là 1 record trong bảng user
- Attribute type: Là 1 cột nhất định
- Entity: Là 1 record nhất định

DBMS làm được những gì?
- Hỗ trợ query
- View mechanism: Sử dụng view để tùy biến cách biểu diễn dữ liệu cho các người dùng khác nhau mà không làm thay đổi content cấu trúc bảng
- Consistency: Đảm bảo khi thay đổi các dữ liệu không liên quan, đầu front end sử dụng dữ liệu còn lại của db không bị ảnh hưởng 

Naming convention
- DB: user
- Field: user_id
- Foreign key: cùng tên với original key

Database design
- Để làm gì: đảm bảo integrity, loại bỏ anomaly
- Là: Tách dữ liệu ra nhiều bảng để bảo toàn data integrity khi cập nhật dữ liệu
- Schema = Biểu diễn kiến trúc cho database
- Conceptual schema: bảng A phụ thuộc bảng B, ...
- Logical schema: Bảng A có trường a,b,c. Trường a là foreign key cho bảng B ....
- Physical schema: Dùng DBMS gì, host ở đâu, server như nào

Data integrity
- Entity integrity: Have uniqueness between entities
- Referential integrity: Đảm bảo mối quan hệ giữa các entity
- Domain integrity: Giá trị trong trường thỏa mãn yêu cầu về đặc tính dữ liệu (độ dài, range, loại dữ liệu, thuộc 1 nhóm các giá trị định trước...)

Database terms
- Record = row = tuple = entry
- Attribute = Field 
- Table = File
- Value = 1,2,3, True, False, "Lmao"
- Normalization: Design database để đáp ứng nhu cầu
- SQL = Structured Query Language = DDL (data definition lang) + DML (Data manipulation lang)
- Keywords = SELECT, ALTER, UPDATE, ....
- Client = người truy cập dữ liệu
- Server = đưa db hoặc 1 mảnh db cho client
- Views = cách biểu thị dữ liệu
- Intermediary table = Junction table = 

Atomic values
- Giá trị chỉ chứa đúng 1 thứ / 1 thông tin
	- Phạm đinh gia dũng -> không atomic
	- First name = Phạm, Last name = Dũng -> Atomic

Relationship
- one-to-one: 1 prof dạy 1 subject
	- Bảng prof có foreign key đến bảng subject 
	- Bảng subject có foreign key đến bảng prof
- one-to-many: 1 prof dạy nhiều subject
	- Bảng subject có foreign key đến bảng prof
	- Bảng prof không có foreign key
- many-to-many: 1 prof dạy nhiều subject, 1 subject có thể có nhiều lớp do prof khác nhau dạy
	- Bảng Intermediary = Bảng class
	- Bảng class có foreign key đến bảng prof và bảng subject