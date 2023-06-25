#algorithm  #gcd #ucln
## Bài toán
Là tìm ước chung lớn nhất đó

## Naive Algo
Thử tất cả các số d từ 1 đến A để tìm ước chung lớn nhất của A và B

## Algo xịn
1. **Ý tưởng**: 
	- B chia A dư A'
	- UCLN(A,B) = UCLN(B,A') = UCLN(A',B)
2. **Thuật toán**
```python
def gcd(a, b):
    c = b%a
    if c != 0:
        return gcd(c,a)
    else:
        return a
```
