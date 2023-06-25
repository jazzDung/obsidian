---
jupyter:
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.10.6
  nbformat: 4
  nbformat_minor: 2
  orig_nbformat: 4
---

::: {.cell .markdown}
### 1. How to import numpy? {#1-how-to-import-numpy}
:::

::: {.cell .code execution_count="2"}

``` python
import numpy as np
```
:::

::: {.cell .markdown}
### 2. How to create a 1D array? {#2-how-to-create-a-1d-array}

Q. Create a 1D array of numbers from 0 to 9
:::

::: {.cell .code execution_count="3"}
``` python
np.arange(start=0, stop=10, step=1)
```

::: {.output .execute_result execution_count="3"}
    array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
:::
:::

::: {.cell .code execution_count="4"}
``` python
np.arange(10)
```

::: {.output .execute_result execution_count="4"}
    array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
:::
:::

::: {.cell .markdown}
### 3. How to create a boolean array? {#3-how-to-create-a-boolean-array}
:::

::: {.cell .code execution_count="8"}
``` python
np.full([3,3], True)
```

::: {.output .execute_result execution_count="8"}
    array([[ True,  True,  True],
           [ True,  True,  True],
           [ True,  True,  True]])
:::
:::

::: {.cell .code execution_count="6"}
``` python
np.ones([3,3], dtype=bool)
```

::: {.output .execute_result execution_count="6"}
    array([[ True,  True,  True],
           [ True,  True,  True],
           [ True,  True,  True]])
:::
:::

::: {.cell .markdown}
### 4. How to extract items that satisfy a given condition from 1D array? {#4-how-to-extract-items-that-satisfy-a-given-condition-from-1d-array}

Q. Extract all odd numbers from
:::

::: {.cell .code execution_count="11"}
``` python
arr = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])

arr[arr%2 ==1]
```

::: {.output .execute_result execution_count="11"}
    array([1, 3, 5, 7, 9])
:::
:::

::: {.cell .markdown}
### 5. How to replace items that satisfy a condition with another value in numpy array? {#5-how-to-replace-items-that-satisfy-a-condition-with-another-value-in-numpy-array}

Q. Replace all odd numbers in arr with -1
:::

::: {.cell .code execution_count="14"}
``` python
arr = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])

arr[arr%2==1] = -1
arr
```

::: {.output .execute_result execution_count="14"}
    array([ 0, -1,  2, -1,  4, -1,  6, -1,  8, -1])
:::
:::

::: {.cell .markdown}
### 6. How to replace items that satisfy a condition without affecting the original array? {#6-how-to-replace-items-that-satisfy-a-condition-without-affecting-the-original-array}

Q. Replace all odd numbers in arr with -1 without changing arr
:::

::: {.cell .code execution_count="16"}
``` python
arr = np.array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
out = np.where(arr%2 == 0,arr,-1)
out
```

::: {.output .execute_result execution_count="16"}
    array([ 0, -1,  2, -1,  4, -1,  6, -1,  8, -1])
:::
:::

::: {.cell .markdown}
### 7. How to reshape an array? {#7-how-to-reshape-an-array}

Q. Convert a 1D array to a 2D array with 2 rows
:::

::: {.cell .code execution_count="20"}
``` python
arr = np.arange(10)
np.reshape(arr, [2,-1])
```

::: {.output .execute_result execution_count="20"}
    array([[0, 1, 2, 3, 4],
           [5, 6, 7, 8, 9]])
:::
:::

::: {.cell .markdown}
### 8. How to stack two arrays vertically? {#8-how-to-stack-two-arrays-vertically}

Q. Stack arrays a and b vertically
:::

::: {.cell .code execution_count="22"}
``` python
a = np.arange(10).reshape(2,-1)
b = np.repeat(1, 10).reshape(2,-1)
```
:::

::: {.cell .code execution_count="24"}
``` python
# Method 1:
np.concatenate([a, b], axis=0)
```

::: {.output .execute_result execution_count="24"}
    array([[0, 1, 2, 3, 4],
           [5, 6, 7, 8, 9],
           [1, 1, 1, 1, 1],
           [1, 1, 1, 1, 1]])
:::
:::

::: {.cell .code execution_count="23"}
``` python
# Method 2:
np.vstack([a, b])
```

::: {.output .execute_result execution_count="23"}
    array([[0, 1, 2, 3, 4],
           [5, 6, 7, 8, 9],
           [1, 1, 1, 1, 1],
           [1, 1, 1, 1, 1]])
:::
:::

::: {.cell .code execution_count="25"}
``` python
# Method 3:
np.r_[a, b]
```

::: {.output .execute_result execution_count="25"}
    array([[0, 1, 2, 3, 4],
           [5, 6, 7, 8, 9],
           [1, 1, 1, 1, 1],
           [1, 1, 1, 1, 1]])
:::
:::

::: {.cell .markdown}
### 9. How to stack two arrays horizontally? {#9-how-to-stack-two-arrays-horizontally}

Q. Stack the arrays a and b horizontally.
:::

::: {.cell .code}
``` python
a = np.arange(10).reshape(2,-1)
b = np.repeat(1, 10).reshape(2,-1)
```
:::

::: {.cell .code execution_count="26"}
``` python
# Method 1:
np.concatenate([a, b], axis=1)
```

::: {.output .execute_result execution_count="26"}
    array([[0, 1, 2, 3, 4, 1, 1, 1, 1, 1],
           [5, 6, 7, 8, 9, 1, 1, 1, 1, 1]])
:::
:::

::: {.cell .code execution_count="27"}
``` python
# Method 2:
np.hstack([a, b])
```

::: {.output .execute_result execution_count="27"}
    array([[0, 1, 2, 3, 4, 1, 1, 1, 1, 1],
           [5, 6, 7, 8, 9, 1, 1, 1, 1, 1]])
:::
:::

::: {.cell .code execution_count="33"}
``` python
# Method 3:
np.r_['-1', a, b]
```

::: {.output .execute_result execution_count="33"}
    array([[0, 1, 2, 3, 4, 1, 1, 1, 1, 1],
           [5, 6, 7, 8, 9, 1, 1, 1, 1, 1]])
:::
:::

::: {.cell .markdown}
### 10. How to generate custom sequences in numpy without hardcoding? {#10-how-to-generate-custom-sequences-in-numpy-without-hardcoding}

Q. Create the following pattern without hardcoding. Use only numpy
functions and the below input array a.
:::

::: {.cell .code execution_count="48"}
``` python
a = np.array([1,2,3])
#> array([1, 1, 1, 2, 2, 2, 3, 3, 3, 1, 2, 3, 1, 2, 3, 1, 2, 3])

repeat_1 = np.repeat(a, 3)
repeat_2 = np.r_[a,a,a]
np.hstack([repeat_1, repeat_2])
```

::: {.output .execute_result execution_count="48"}
    array([1, 1, 1, 2, 2, 2, 3, 3, 3, 1, 2, 3, 1, 2, 3, 1, 2, 3])
:::
:::

::: {.cell .markdown}
### 11. How to get the common items between two python numpy arrays? {#11-how-to-get-the-common-items-between-two-python-numpy-arrays}

Q. Get the common items between a and b
:::

::: {.cell .code execution_count="69"}
``` python
a = np.array([1,2,3,2,3,4,3,4,5,6])
b = np.array([7,2,10,2,7,4,9,4,9,8])
# array([2, 4])
```
:::

::: {.cell .code execution_count="58"}
``` python
np.unique(a[a==b])
```

::: {.output .execute_result execution_count="58"}
    array([2, 4])
:::
:::

::: {.cell .code execution_count="70"}
``` python
np.intersect1d(a,b)
```

::: {.output .execute_result execution_count="70"}
    array([2, 4])
:::
:::

::: {.cell .markdown}
### 12. How to remove from one array those items that exist in another? {#12-how-to-remove-from-one-array-those-items-that-exist-in-another}

Q. From array a remove all items present in array b
:::

::: {.cell .code execution_count="71"}
``` python
a = np.array([1,2,3,4,5])
b = np.array([5,6,7,8,9])
# array([1,2,3,4])
```
:::

::: {.cell .code execution_count="75"}
``` python
np.setdiff1d(a,b)
```

::: {.output .execute_result execution_count="75"}
    array([1, 2, 3, 4])
:::
:::

::: {.cell .markdown}
### 13. How to get the positions where elements of two arrays match? {#13-how-to-get-the-positions-where-elements-of-two-arrays-match}

Q. Get the positions where elements of a and b match
:::

::: {.cell .code execution_count="77"}
``` python
a = np.array([1,2,3,2,3,4,3,4,5,6])
b = np.array([7,2,10,2,7,4,9,4,9,8])
#> (array([1, 3, 5, 7]),)
```
:::

::: {.cell .code execution_count="78"}
``` python
np.where(a==b)
```

::: {.output .execute_result execution_count="78"}
    (array([1, 3, 5, 7]),)
:::
:::

::: {.cell .markdown}
### 14. How to extract all numbers between a given range from a numpy array? {#14-how-to-extract-all-numbers-between-a-given-range-from-a-numpy-array}

Q. Get all items between 5 and 10 from a.
:::

::: {.cell .code execution_count="79"}
``` python
a = np.array([2, 6, 1, 9, 10, 3, 27])
# (array([6, 9, 10]),)
```
:::

::: {.cell .code execution_count="94"}
``` python
a[(a < 11) & (a >5)]
```

::: {.output .execute_result execution_count="94"}
    array([ 6,  9, 10])
:::
:::

::: {.cell .code execution_count="95"}
``` python
a[np.where((a < 11) & (a >5))]
```

::: {.output .execute_result execution_count="95"}
    array([ 6,  9, 10])
:::
:::

::: {.cell .markdown}
### 15. How to make a python function that handles scalars to work on numpy arrays? {#15-how-to-make-a-python-function-that-handles-scalars-to-work-on-numpy-arrays}

Q. Convert the function maxx that works on two scalars, to work on two
arrays.
:::

::: {.cell .code execution_count="97"}
``` python
def maxx(x, y):
    """Get the maximum of two items"""
    if x >= y:
        return x
    else:
        return y

maxx(1, 5)
#> 5

a = np.array([5, 7, 9, 8, 6, 4, 5])
b = np.array([6, 3, 4, 8, 9, 7, 1])
#> array([ 6.,  7.,  9.,  8.,  9.,  7.,  5.])
```
:::

::: {.cell .code execution_count="98"}
``` python
pair_max = np.vectorize(maxx, otypes=[int])
pair_max(a,b)   
```

::: {.output .execute_result execution_count="98"}
    array([6, 7, 9, 8, 9, 7, 5])
:::
:::

::: {.cell .markdown}
### 16. How to swap two columns in a 2d numpy array? {#16-how-to-swap-two-columns-in-a-2d-numpy-array}

Q. Swap columns 1 and 2 in the array arr.
:::

::: {.cell .code execution_count="102"}
``` python
arr = np.arange(9).reshape(3,3)
arr
```

::: {.output .execute_result execution_count="102"}
    array([[0, 1, 2],
           [3, 4, 5],
           [6, 7, 8]])
:::
:::

::: {.cell .code execution_count="103"}
``` python
arr[:,0], arr[:,1] = arr[:,1], arr[:,0].copy()
arr
```

::: {.output .execute_result execution_count="103"}
    array([[1, 0, 2],
           [4, 3, 5],
           [7, 6, 8]])
:::
:::

::: {.cell .code execution_count="110"}
``` python
np.hstack([arr[:, [1,0]], arr[:, 2:]])
```

::: {.output .execute_result execution_count="110"}
    array([[0, 1, 2],
           [3, 4, 5],
           [6, 7, 8]])
:::
:::

::: {.cell .markdown}
### 17. How to swap two rows in a 2d numpy array? {#17-how-to-swap-two-rows-in-a-2d-numpy-array}

Q. Swap rows 1 and 2 in the array
:::

::: {.cell .code execution_count="111"}
``` python
arr = np.arange(9).reshape(3,3)
arr
```

::: {.output .execute_result execution_count="111"}
    array([[0, 1, 2],
           [3, 4, 5],
           [6, 7, 8]])
:::
:::

::: {.cell .markdown}
Same as above
:::

::: {.cell .markdown}
### 18. How to reverse the rows of a 2D array? {#18-how-to-reverse-the-rows-of-a-2d-array}

Q. Reverse the rows of a 2D array arr.
:::

::: {.cell .code execution_count="112"}
``` python
arr = np.arange(9).reshape(3,3)
arr
```

::: {.output .execute_result execution_count="112"}
    array([[0, 1, 2],
           [3, 4, 5],
           [6, 7, 8]])
:::
:::

::: {.cell .code execution_count="119"}
``` python
arr[::-1]
```

::: {.output .execute_result execution_count="119"}
    array([[6, 7, 8],
           [3, 4, 5],
           [0, 1, 2]])
:::
:::

::: {.cell .markdown}
### 19. How to reverse the columns of a 2D array? {#19-how-to-reverse-the-columns-of-a-2d-array}

Q. Reverse the columns of a 2D array

-   Same as above
:::

::: {.cell .markdown}
### 20. How to create a 2D array containing random floats between 5 and 10? {#20-how-to-create-a-2d-array-containing-random-floats-between-5-and-10}

Q. Create a 2D array of shape 5x3 to contain random decimal numbers
between 5 and 10.
:::

::: {.cell .code execution_count="125"}
``` python
np.random.uniform(low = 5, high = 11, size=[5,3])
```

::: {.output .execute_result execution_count="125"}
    array([[ 9.04464102,  7.85310761, 10.22210207],
           [10.51534226,  9.98687173,  8.74780083],
           [ 5.85817411,  5.78035057,  5.3327691 ],
           [ 6.62389011,  9.07170242, 10.54477797],
           [ 5.47776394,  9.69805198,  8.10444868]])
:::
:::

::: {.cell .markdown}
### 21. How to print only 3 decimal places in python numpy array? {#21-how-to-print-only-3-decimal-places-in-python-numpy-array}

Q. Print or show only 3 decimal places of the numpy array rand_arr.
:::

::: {.cell .code execution_count="133"}
``` python
rand_arr = np.random.random((5,3))
rand_arr
```

::: {.output .execute_result execution_count="133"}
    array([[0.084, 0.239, 0.03 ],
           [0.908, 0.666, 0.121],
           [0.996, 0.372, 0.628],
           [0.307, 0.344, 0.823],
           [0.702, 0.048, 0.711]])
:::
:::

::: {.cell .code execution_count="135"}
``` python
np.around(rand_arr, 3)
```

::: {.output .execute_result execution_count="135"}
    array([[0.084, 0.239, 0.03 ],
           [0.908, 0.666, 0.121],
           [0.996, 0.372, 0.628],
           [0.307, 0.344, 0.823],
           [0.702, 0.048, 0.711]])
:::
:::

::: {.cell .code execution_count="134"}
``` python
# Limit to 3 decimal places
np.set_printoptions(precision=3)
rand_arr
```

::: {.output .execute_result execution_count="134"}
    array([[0.084, 0.239, 0.03 ],
           [0.908, 0.666, 0.121],
           [0.996, 0.372, 0.628],
           [0.307, 0.344, 0.823],
           [0.702, 0.048, 0.711]])
:::
:::

::: {.cell .markdown}
### 22. How to pretty print a numpy array by suppressing the scientific notation (like 1e10)? {#22-how-to-pretty-print-a-numpy-array-by-suppressing-the-scientific-notation-like-1e10}

Q. Pretty print rand_arr by suppressing the scientific notation (like
1e10)
:::

::: {.cell .code execution_count="136"}
``` python
np.random.seed(100)
rand_arr = np.random.random([3,3])/1e3
rand_arr
```

::: {.output .execute_result execution_count="136"}
    array([[5.434e-04, 2.784e-04, 4.245e-04],
           [8.448e-04, 4.719e-06, 1.216e-04],
           [6.707e-04, 8.259e-04, 1.367e-04]])
:::
:::

::: {.cell .code execution_count="138"}
``` python
np.set_printoptions(suppress=True, precision=6)
rand_arr
```

::: {.output .execute_result execution_count="138"}
    array([[0.000543, 0.000278, 0.000425],
           [0.000845, 0.000005, 0.000122],
           [0.000671, 0.000826, 0.000137]])
:::
:::

::: {.cell .markdown}
### 23. How to limit the number of items printed in output of numpy array? {#23-how-to-limit-the-number-of-items-printed-in-output-of-numpy-array}

Q. Limit the number of items printed in python numpy array a to a
maximum of 6 elements.
:::

::: {.cell .code execution_count="140"}
``` python
a = np.arange(15)
#> array([ 0,  1,  2, ..., 12, 13, 14])
```
:::

::: {.cell .code execution_count="141"}
``` python
np.set_printoptions(threshold=6)
a
```

::: {.output .execute_result execution_count="141"}
    array([ 0,  1,  2, ..., 12, 13, 14])
:::
:::

::: {.cell .markdown}
### 24. How to print the full numpy array without truncating {#24-how-to-print-the-full-numpy-array-without-truncating}

Q. Print the full numpy array a without truncating.
:::

::: {.cell .code execution_count="145"}
``` python
a = np.arange(15)
#> array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14])
```
:::

::: {.cell .code execution_count="151"}
``` python
np.set_printoptions(threshold=100)
a
```

::: {.output .execute_result execution_count="151"}
    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14])
:::
:::

::: {.cell .markdown}
### 25. How to import a dataset with numbers and texts keeping the text intact in python numpy? {#25-how-to-import-a-dataset-with-numbers-and-texts-keeping-the-text-intact-in-python-numpy}

Q. Import the iris dataset keeping the text intact.
:::

::: {.cell .code execution_count="161"}
``` python
np.genfromtxt(fname='./iris.data', delimiter=',', dtype='object')
```

::: {.output .execute_result execution_count="161"}
    array([[b'5.1', b'3.5', b'1.4', b'0.2', b'Iris-setosa'],
           [b'4.9', b'3.0', b'1.4', b'0.2', b'Iris-setosa'],
           [b'4.7', b'3.2', b'1.3', b'0.2', b'Iris-setosa'],
           ...,
           [b'6.5', b'3.0', b'5.2', b'2.0', b'Iris-virginica'],
           [b'6.2', b'3.4', b'5.4', b'2.3', b'Iris-virginica'],
           [b'5.9', b'3.0', b'5.1', b'1.8', b'Iris-virginica']], dtype=object)
:::
:::
