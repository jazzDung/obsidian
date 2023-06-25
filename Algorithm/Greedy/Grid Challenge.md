#algorithm #greedy  

## Bài toán

## Trường hợp đặc biệt

## Thuật toán
```python


def gridChallenge(input):

    grid = []

    for item in input:
        grid.append(''.join(sorted(item)))

    result = True
    
    for i in range(len(grid[0])):
        for j in range(len(grid)-1):

            if grid[j+1][i] < grid[j][i]:
                result = False
                break
    
    return result

if __name__ == '__main__':
    t = int(input().strip())

    for t_itr in range(t):
        n = int(input().strip())

        grid = []

        for _ in range(n):
            grid_item = input()
            grid.append(grid_item)

        result = gridChallenge(grid)
        
        if result == True:
            print("YES")
        elif result == False:
            print("NO")

```

## Complexity
Với input là $m$ dòng, mỗi dòng có $n$ character, $O(mn)$