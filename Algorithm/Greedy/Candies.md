#algorithm #greedy  

## Bài toán
![[Pasted image 20230406230724.png]]

## Trường hợp đặc biệt
- Ví dụ như 1,2,3,5,3,2,1
	- Thì kẹo distribution là 1,2,3,4,3,2,1 chứ không phải 1,2,3,4,1,1,1 nhá

## Ý tưởng
1.  Với những học sinh có điểm lớn hơn người bên trái thì khá dễ, cứ +1 kẹo so với học sinh bên trái là được.
2. Học sinh có điểm nhỏ hơn người bên trái thì khó hơn. Theo cái trường hợp đặc biệt trên thì có thể thấy là ta sẽ khi 1 học sinh có điểm cao hơn học sinh bên phải, ta không thể biết được chắc kèo số kẹo sẽ phát cho học sinh đó là bao nhiêu mà không nhìn tất cả những học sinh còn lại ở phía bên phải
	- Ví dụ như 1,2,3,5,3,2,1 phải nhìn hết cả 3 học sinh cuối mới biết được thằng số 5 sẽ có 3 cái kẹo, vì nếu nó chỉ có 1 cái kẹo thì 2 thằng sau ăn đb ăn cứt

3. Vậy nên ý tưởng sẽ là chạy 1 lần từ bên trái qua phải (Để tính kẹo cho trường hợp 1) và chạy 1 lần từ phải qua trái (Để tính kẹo cho trường hợp 2)

## Thuật toán
```python

def candies(arr):
    distrubution = [1 for _ in range(len(arr))]
    
    for i in range(len(arr)-1):
        if arr[i+1] > arr[i]:
            distrubution[i+1] = distrubution[i]+1
            
            # print(arr[i+1], arr[i])
        
    for i in reversed(range(len(arr)-1)):
        if arr[i+1] < arr[i]:
            if distrubution[i] < distrubution[i+1]+1:
                distrubution[i] = distrubution[i+1]+1 
            
            # print(arr[i+1], arr[i])

    print(distrubution)
            
    return sum(distrubution)
    
if __name__ == '__main__':
    n = int(input().strip())

    arr = []

    for _ in range(n):
        arr_item = int(input().strip())
        arr.append(arr_item)

    result = candies(n, arr)

    print(str(result) + '\n')

```

## Complexity
- Loop 2 lần, mỗi lần loop qua n phần tử của input
	- $O(2n)$