#test #testing #algorithm

## Tại sao lại sai?
1. Sai code (Kiểu đơn giản là nó ra kết quả sai)
2. Không phủ hết các trường hợp đặc biệt
3. Chạy quá chậm
4. Runtime error

## Lo cái trường hợp đặc biệt
- **Các trường hợp cần lo**
	- n = 0
	- n = 1
	- n = cái số lớn nhất theo giới hạn bài toán

> **Luôn luôn tính kết quả của các trường hợp này BẰNG TAY trước khi check kết quả của thuật toán để không bị ảo tưởng sức mạnh**

## Lo cái chạy quá chậm
- Sử dụng timer để xem chương trình chạy bao lâu
```python
time.clock()
```

- Kiểm tra complexity của thuật toán
	- Nếu nó chạy nhanh trên tập dữ liệu nhỏ và chạy lâu vãi cứt trên tập dữ liệu to -> U dead bro
	- Nếu nó chạy trên tập dữ liệu mà bị lâu vl không có kết quả -> Có thể có infinite loop

## Lo cái runtime error
- Các lỗi khả thi
	- Chia 0
	- Overflow với loại dữ liệu đang dùng (Số lớn quá mức cho phép)

## Lo cái kết quả sai
- Các sửa khả thi
	- Dùng 1 thuật toán khác (Chậm hơn cũng được) mà biết chắc chắn là đúng 100%
	- Dùng cả 2 thuật toán để tìm kết quả trên 1 đống dữ liệu random cho đến khi 2 kết quả khác nhau

## Tạo stress test cho thuật toán

Test on the examples from the problem statement. Then make a few other small tests, solve them manually and check that your program outputs the correct answer. Generate a big input and launch your program to check that it works fast enough and doesn't consume too much memory. Test for corner cases: smallest allowed values and largest allowed values of all input parameters, equal numbers in the input, very long strings, etc. Then make a stress test. After all these tests passed, submit the solution.

- Sample stress test

```python
import max_pairwise_product, max_pairwise_product_better, random, os

def testing(num_test, max_size, max_num):
    i = 0
    while i < num_test:
        i += 1
        
        # Input size
        list_size = random.randint(2, max_size)

        # Create input
        input = [(random.randint(1, max_num)) for i in range(list_size)]
        first = max_pairwise_product.max_pairwise_product(input)
        second = max_pairwise_product_better.max_pairwise_product(input)

        print(f"Test {i}")
        print(f"Input: {input}")

        if first != second:
            print(f"VÃI L SAI RỒI BRO")
  
        print(f"First algo: {first}\nSecond algo: {second} \n")

if __name__ == '__main__':
    testing(int(input("num_test: ")), int(input("max_size: ")), int(input("max_num: ")))

```
