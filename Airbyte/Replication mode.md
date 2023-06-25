### Cursor
- 1 cái pointer chỉ vào bảng data đang có, để track xem dữ liệu gần nhất được gửi vào bảng là gì và không gửi lại các dữ liệu đó nữa

### Full refresh vs Incremental
![[Pasted image 20230507155208.png]]

### Full refresh: Overwrite vs Append
![[Pasted image 20230507155316.png]]

### Incremental: Append vs Deduped history
**Limitation**
	- Nếu nguồn dữ liệu xóa 1 record đi thì lần sync tiếp theo sẽ không có record đó (Duh!), nhưng trong bảng destination vẫn tồn tại phiên bản gần nhất của record
**Append**
	- Nếu record được cập nhật -> Sẽ có nhiều dòng của record đó với cái giá trị của cursor khác nhau trong bảng destination
**Deduped History**
	- Tạo 1 cái bảng riêng để chứa các phiên bảng cũ của record và chỉ lưu phiên bản mới nhất trong bảng destination
![[Pasted image 20230507155741.png]]

### Change Data Capture
- Có vẻ là nó không áp dụng được cho nguồn dữ liệu của mình
