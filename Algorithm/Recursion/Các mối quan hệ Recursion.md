## Master theorem cho bài toán giảm
$T(n) = aT(n-b) + f(n)$
$a>0, f(n) = O(n^k) \space với \space k>=0$ 
- Với $a<1$
	- $T(n) = O(n^k)$
- Với a = 1
	- $T(n) = O(n^{k+1})$
- Với a >1
	- $T(n) = O(n^k * a^{n/b}))$

## Master theorem cho bài toán chia
$T(n) = aT(n/b) + f(n)$
$Với f(n) =O(n^klog_pn)*$
- Khi $log_ba > k$
	- $T(n) =O(n^{log_ba}$
- Khi $log_ba = k$
	- $T(n) =O(n^{log_ba}$

![[Pasted image 20230511140558.png]]

## $T(n) = T(n-1) + 1$
Complexity: $O(n)$
```C
void Test(int n)
{
	if(n>0)
	{
		printf("/d", n); //take 1 calculation
		Test(n-1);
	}
}

Test(5)
```

## $T(n) = T(n-1) + n$
Complexity: $O(n^2)$
```C
void Test(int n)
{
	if(n>0) //
	{
		for (i=1, i<n,i++) //loop n times
		{
			printf("/d", n); //take 1 calculation
		}
		Test(n-1); //n-1 more time
	}
}

Test(5)
```

## $T(n) = T(n-1) + log(n)$
Complexity: $O(nlog(n))$
```C
void Test(int n)
{
	if(n>0) //
	{
		for (i=1, i<n,i=i*2) //loop n times
		{
			printf("/d", n); //take 1 calculation
		}
		Test(n-1); //n-1 more time
	}
}

Test(5)
```

## $T(n) = 2T(n-1) + log(n)$
Complexity: $O(2^n)$
```C
void Test(int n)
{
	if(n>0)
	{
		printf("/d", n); //take 1 calculation
		Test(n-1); 
		Test(n-1);
	}
}

Test(5)
```