#algorithm  #warmup

## Bài toán
![[Pasted image 20230405155729.png]]

## Các trường hợp đặc biệt
- 12h PM
- 12h AM

## Giải
```python
def timeConversion(s):
    
    #Convert time
    if s[-2:] == 'PM':
	    # Take care of 12PM
        if s[:2] != '12':
            s = str(int(s[:2]) + 12) + s[2:] 
            
	# Take care of 12AM
    elif s[:2] == '12':
        s = "00" + s[2:]
        
    #Remove AM/PM suffix
    s = s[:-2]    
    
    return s

if __name__ == '__main__':

    s = input()

    result = timeConversion(s)

    print(result + '\n')
```

## Complexity
O(n) thui