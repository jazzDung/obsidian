## là gì?
- Giống hệt như các vật thể dạng chồng ngoài đời
	- Phần tử mới nhất được xếp lên đỉnh (Hành động gọi là Push)
	- Chỉ có thể lấy phần tử trên đỉnh ra khỏi stack (Hành động gọi là Pop)
	- Tóm lại là cơ chế Last In First Out (LIFO)

## khi nào dùng?
- Mô phỏng các vật thể dạng chồng ngày đời
- Dùng cho các bài toán có các vật thể đi theo cặp và cần đảm bảo các cặp trùng khớp với nhau
	- Kiểm tra xem các bracket có khớp nhau không khi code {} , [] , ()
- Cơ chế undo redo trong app
- Implement recursion
- Implement Depth First Search

## độ phức tạp của các hành động
- O(1): push, pop, peek (nhìn phần tử trên đỉnh), size (Lấy kích thước)
- O(n): search

## implement như nào?
- Implement từ 1 cái linked list là được nhá
	- Singly hay doubly đều được
	- Với singly thì phần đỉnh của stack phải là đầu của linked list
	- Thêm các function sau
		1. push: thêm phần tử vào đít của linked list (Thêm vào đầu nếu là singly)
		2. pop: bỏ phần tử cuối của linked list (Bỏ head nếu là singly)