# Understanding ```np.dot()``` and Matrix Multiplication

This post teaches you the functionality of numpy's "np.dot()" function and what parameters you must take into consideration while using it.

In starting my journey to understand the complexity of deep neural networks I came across a function that must be used in order to multiply the the inputs and weights, ```np.dot()```. The purpose of ```np.dot()``` is to multiply two matrices (plural for an array that is a dimension of two or more).

```python
import numpy as np

x = [[1, 2], 
     [3, 4]]

y = [[1, 3], 
     [2, 4]]

print(np.dot(x, y)) 

'''
output:
  [[5, 11],
  [11, 25]]
'''

```
The ```np.dot()``` function takes in two arguments which are matrices, ```np.dot(x, y)``` and multiplys each row in matrix ```x``` by each column in matrix ```y```.
```
[row_1_x * column_1_y, row_2_x * column_1_y] = [1 * 1 + 2 * 2, 3 * 1 + 4 * 2] = [5, 11]
[row_1_x * column_2_y, row_2_x * column_2_y] = [1 * 3 + 2 * 4, 3 * 3 + 4 * 4] = [11, 25]
```

## User's Guide
When using the ```np.dot()``` function make sure that you are multiplying two matrices with combatible shapes. "What are matrix shapes?" you might be asking, matrix shapes are ways to describe the dimensions of a matrix using a notation of ```(height, width)``` or ```(# of rows, # of columns)```. You can check the shape of any matrix using ```np.shape(matrix)```. When using ```np.dot(shape_x, shape_y)``` the number of ```shape_x```'s columns should always equal the number of ```shape_y```'s rows or else numpy will return an error. Another thing to keep in mind when using ```np.dot()``` is that the height of your shape will be the height of ```shape_x``` and the width will be the width of ```shape_y```.

Example:
```python
import numpy as np

def npDot(size_a, size_b):
    a, b = np.random.uniform(size=size_a), np.random.uniform(size=size_b)
    c = np.dot(a, b)
    
    print(str(np.shape(a)) + " * " + str(np.shape(b) + " = " + str(np.shape(c))


npDot((3, 2), (2, 20))

'''
output:
    (3, 2) * (2, 20) = (3, 20)
'''
```
