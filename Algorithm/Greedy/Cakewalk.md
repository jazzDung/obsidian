#algorithm  #greedy 

## Bài toán
![[Pasted image 20230405162207.png]]

## Trường hợp đặc biệt
- Không có?

## Thuật toán

```python
def marcsCakewalk(calorie):
    calorie.sort(reverse = True)
    
    miles = 0
    
    for i in range(len(calorie)):
        miles += (2**i)*(calorie[i])

    return miles

if __name__ == '__main__':
    n = int(input().strip())

    calorie = list(map(int, input().rstrip().split()))

    result = marcsCakewalk(calorie)

    print(str(result))
```

## Complexity
