
# input, output

1. Yêu cầu input theo kiểu từng số, xong quy đổi ra list?

	```python
	0 1 2 3 4
	-> [0,1,2,3,4]
	```
	
	```python
	if __name__ == '__main__':
	    a = list(map(int, input().rstrip().split()))
	    b = list(map(int, input().rstrip().split()))
	    result = someFunction(a, b)
	```


2. Yêu cầu output cũng kiểu print từng character cách nhau? 
	- Không nên viết thẳng vào function
	- Cứ cho function trả về list hay cái gì cũng được
	- Output sẽ được quyết định ở main

	```python
	def listFunction():
		return a_list # [1,2,3,4,5]
	```
	
	```python
	# Use OS write
	if __name__ == '__main__':
		fptr = open(os.environ['OUTPUT_PATH'], 'w')
	    result = listFunction()
	    fptr.write(' '.join(map(str, result)))
	    fptr.write('\n')
	    fptr.close()
	    
	-> 1 2 3 4 5
	```
	
	```python
	# Use simple print
	if __name__ == '__main__':
		result = listFunction()
	    result = ' '.join(map(str, result))
	    print(result)
	    
	-> 1 2 3 4 5
	```

3. Yêu cầu in output thành từng dòng?
	```python
	[1,2,3,4,5]
	->
	1
	2
	3
	4
	5
	```
	
	```python
	result = function()
	for item in result:
		print(item)
	```

