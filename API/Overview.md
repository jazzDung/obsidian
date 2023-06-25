## Định nghĩa
- Tạm hiểu API là 1 cái hợp đồng
	- Mình viết đúng implementation theo những gì API cần
	- API thực hiện 1 task theo cái implementation đó

## Why REST API?
- Tác vụ nặng được xử lý trên cloud, không phụ thuộc vào phần cứng

## HTTP là gì?
- Là 1 cái protocol để nhận và gửi dữ liệu
- Client gửi 1 yêu cầu nào đó, gồm có URL (Địa chỉ) và hành động (Cụ thể là "Get")  và server thực hiện hành động đó, và trả về content cho client
	- Khi nhập URL web: content là HTML, hypertext, hình ảnh, file...
- Các hành động (Request method)
	- GET: Chỉ đọc dữ liệu, không thay đổi
	- POST: Gửi dữ liệu
	- PUT: Update dữ liệu
	- PATCH: 
	- DELETE: Xóa dữ liệu
	- Tương ứng với các hành động trong CRUD

## RESTful là gì?
- REST: Representational State Transfer

1. How REST API sit on top of web
	- Người dùng gửi request cho server
	- Server không biết người dùng là ai, và không lưu lại thông tin của họ
	- Nếu muốn gửi thông tin log in hoặc key, cần phải ghi nó ở request header trong mỗi lần gửi request

2. 