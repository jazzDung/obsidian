## là gì?
- Nó là 1 cái linked list, nhưng đuôi sẽ không trỏ vào Null mà trỏ vào node đầu của list
	- Việc này khiến cho list technically không có đầu đuôi
- Giống như linked list thì circular list cũng có singly và doubly circular list

## lợi thế so với linked list
- So với singly
	- Có thể tiếp cận bất cứ node nào từ bất cứ node nào (Singly không đi từ node sau sang node trước được)
- Tiết kiệm thời gian đi từ node đầu đến node cuối

## bất lợi so với linked list
- Không cẩn thận thì trong quá trình tìm phần tử có thể lặp vô tận
- Phức tạp hơn linked list

## dùng khi nào?
- dùng trong các trường hợp cần tiếp cận các phần tử theo 1 vòng lặp
	- kiểu multiplayer game này