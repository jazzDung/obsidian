**Bước 1:** 
- Nếu có quyền vào repo thì tạo branch, tự sửa, xong tạo merge request với tên là mã task Jira (CM-1724) hoặc là mã task của mình và nội dung thay đổi
- Nếu không có thì nhờ người khác đổi =)))

**Bước 1.5:**
- Với MDP
	- MR từ branch mình vào main -> Nhờ anh Kiên/Trung
	- MR từ branch vào dag -> Nhờ anh Kiên/Trung
	- Paste commit hash id vào gitops Prod -> MR vào main -> Nhờ anh Trung

**Bước 2:**
Lên [Change Management](https://entrade.atlassian.net/jira/core/projects/CM/board)
- Nếu là các thay đổi mà ảnh hưởng đến việc tính toán dữ liệu hoặc dữ liệu khách hàng, cho vào tab <font color="#0070c0">GOLIVE SAU BATCH</font>
- Còn lại (Phần lớn các thay đổi của mình) cho vài <font color="#0070c0">OPEN</font>

**Bước 3:** 
- Lên 1 con post như sau, hướng dẫn viết post ở đây (Anh Phúc làm ơn gửi em)

- Với MDP
![[Pasted image 20230908090618.png]]

- Thêm config cơ bản
![[Pasted image 20230725141201.png]]

**Bước 4:**
- Yêu cầu anh Trung approve MR
- Sau khi đồng ý thì kéo cái post đó sang tab <font color="#0070c0">APPROVED</font>

**Bước 5:**
- Lên channel Techies![[Pasted image 20230725141836.png]]
- Reply với link task jira cần golive![[Pasted image 20230725141949.png]]

**Bước 6:**
- Rejoice



### Commit message
- CM-1908 update airflow 




Trước khi commit phải xoá các file với config có thông tin database

- build được image voứ code hiện tại
- K8s và k9s để access vào container dùng image kia
- Acess xong thì chạy lệnh crawl để test
