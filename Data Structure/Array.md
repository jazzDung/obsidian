## Khi nào dùng array?
- Lưu trữ dữ liệu sequential
- Lưu trữ object tạm thời
- Dùng làm buffer

## Array hoạt động như nào?
- Array sẽ được đặt trong bộ nhớ liền kề, tức là dữ liệu các phần tử nằm kề nhau sẽ được lưu trong các địa chỉ kề nhau trong bộ nhớ
- Mỗi phần tử được reference bằng số thứ tự, gọi là index
	- Đây là cách duy nhất để tiếp cận phần tử trong array
- Khi cần tiếp cận một phần tử
	- Bắt đầu từ phần tử ở đầu array -> di chuyển qua từng phần tử cho đến khi đến phần tử yêu cầu

## Dynamic array hoạt động như nào?
- Khởi tạo 1 static array với kích thước (Capacity) lớn hơn 1 tí so với dữ liệu ban đầu (Length)
- Khi thêm dữ liệu vào và length > capacity, khởi tạo 1 static array mới với capacity gấp đôi array cũ và copy toàn bộ dữ liệu sang

## Static vs dynamic array
|                  | Static array | Dynamic array |
| ---------------- | ------------ | ------------- |
| Tiếp cận phần tử | $O(n)$       | $O(1)$        |
| Tìm kiếm phần tử | $O(n)$       | $O(n)$        |
| Điền phần tử     | n/a          | $O(n)$        |
| Xóa phần tử      | n/a          | $O(1)$        |
| Thêm phần tử và  | n/a          | $O(n)$        |

## Implement Dynamic Array như nào?
- Biến
	- 1 static array
	- Số phần tử ban đầu do người dùng quyết định (Len)
	- Độ dài thật của array (Capacity)