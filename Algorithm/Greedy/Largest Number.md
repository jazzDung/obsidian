#algorithm #greedy  

## Bài toán

## Trường hợp đặc biệt

## Thuật toán
```python

def minimumAbsoluteDifference(arr):
    arr.sort()
    
    min_difference = abs(max(arr) - min(arr))
    
    for i in range (len(arr) - 1):
        difference = abs(arr[i] - arr[i+1])
        if difference < min_difference:
            min_difference = difference
    
    return min_difference

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input().strip())

    arr = list(map(int, input().rstrip().split()))

    result = minimumAbsoluteDifference(arr)

    fptr.write(str(result) + '\n')

    fptr.close()

```

## Complexity
O(n)