#algorithm #greedy  

## Bài toán
![[Pasted image 20230406235012.png]]

## Trường hợp đặc biệt
- Các trường hợp mà có A và B hoàn hảo ngay từ đầu
	- Khi làm theo yêu cầu sửa 1 phần tử trong B sẽ mất đi 1 Beautiful Pair

## Ý tưởng
- Bốc các beautiful pair ra khỏi A và B
- Xét những gì còn lại trong A và B
	- Nếu còn nhiều hơn 1 phần từ trong A và B thì tức là việc sửa phần tử trong B sẽ tăng thêm 1 pair
	- Nếu không còn phần tử nào trong A và B tức là việc sửa 1 phần tử trong B sẽ giảm đi 1 pair

## Thuật toán
```python
def beautifulPairs(A, B):
    
    pair = 0
    b_changed = False
    for i in range(len(A)):
        for j in range(len(B)):
            if A[i] == B[j]:
                pair += 1
                A[i] = -1 #Make sure that this element will not be consider again
                B[j] = -2 #Make sure that this element will not be consider again
        
    B = [value for value in B if value != -1] # Check for remaining unmatched element
    
    if len(A) >= 1:
        pair +=1
    else:
        pair -=1
        
    return pair

if __name__ == '__main__':
    n = int(input().strip())

    A = list(map(int, input().rstrip().split()))

    B = list(map(int, input().rstrip().split()))

    result = beautifulPairs(A, B)

    print(str(result) + '\n')


```

## Complexity
- Loop 2 lần, mỗi lần loop qua n phần tử của input
	- $O(n^2)$


