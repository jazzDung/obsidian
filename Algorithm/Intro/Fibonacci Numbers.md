#algorithm #fibonacci
## Bài toán
Fibonacci là gì thì biết rồi nhé

## Naive algo
1. **Tính toán kiểu recursive**

```python

x = 1
y =2
print(x+y)
```
```python
fibonacci(i) = fibonacci(i-1) + fibonacci(i-2)

```
2. **Tại sao nó lại chậm vậy?**
- Cần tính tất cả các số fibonacci trước đó
- Nhiều số fibonacci cần tính đi tính lại nhiều lần
![[Pasted image 20230319134933 1.png]]

## Algo xịn
1. Sử dụng array
```python
def fibobo(n):
	fibonacci = []
	fibonacci[0] = 0
	fibonacci[1] = 1
	
	for i in range (n):
		fibonacci[i] = fibonacci[i-1] + fibonacci[i-2]
	
	return fibonacci[n]
```
2. **Tại sao nó lại nhanh?**
- Các số fibonacci chỉ cần tính 1 lần và được lưu lại trong array