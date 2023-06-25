#algorithm #greedy  

## Bài toán
![[Pasted image 20230407224738.png]]

## Trường hợp đặc biệt

## Ý tưởng

- Sử dụng list.pop() khi

## Thuật toán
```python
def largestPermutation(k, arr):
            
    X = sorted(arr)
  
    if k > len(arr):
        return sorted(arr, key = lambda x: -x) #O(n logn)
    
    i = 0
    while k > 0 and len(X) > 0: #O(n)
        
        x = X.pop() #O(1)
        if x != arr[i]:
            a = arr.index(x) #O(n)
            arr[a], arr[i] = arr[i], arr[a] #O(n)
            k -= 1
        i += 1
    
    return arr
    
    return result      

```

```python
Python by shashank21j

n,k = map(int,raw_input().split())
arr = map(int,raw_input().split())
brr = [0 for _ in range(n+1)]
for i in range(n):
    brr[arr[i]] = i
for i in range(n):
    if k == 0:
        break
    if arr[i] == n-i:
        continue
    else:
        ind = brr[n-i]
        arr[i],arr[ind] = arr[ind],arr[i]
        brr[arr[i]],brr[arr[ind]] = brr[arr[ind]],brr[arr[i]]
    k -=1
print " ".join(map(str,arr))
```

## Complexity
- $O(n logn)$ tại các trường hợp K > độ dài array
- $O(n^2)$ các trường hợp còn lại