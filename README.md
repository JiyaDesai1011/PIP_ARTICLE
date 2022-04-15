Basics Of NumPy
Loading…
NumPy (short for Numerical Python) is “The fundamental package for scientific computing with Python.”
Typical Python lists are slower in execution and NumPy array objects (aka. ndarray) are 50 times faster as compared to the Python lists. The reason for that is that the ndarray objects are stored at a continuous place in memory. So, the access and manipulation of data is much more efficient and faster. Also, NumPy provides number of functions for working in domain of linear algebra, matrices, Fourier transform, data science, etc. The different libraries like Pandas, Matplotlib etc. are built on top of NumPy.
History
NumPy was created in 2005 by Travis Oliphant. Partially, the NumPy library was written in Python but most of the part of it which includes faster computations was written in C / C++. For the source code of NumPy click here.
Installation
If your system already contains Python and pip then you can simply run the following command in cmd and get NumPy installed on your system.
pip install numpy
To import NumPy you need to write the following code:
>>>import numpy as np
Creating NumPy Arrays, Loading and Saving Files
In NumPy we work with multi-dimensional arrays. They’re known as ndarrays, which is short for n-dimensional arrays. Rather than working with lists of lists, any datasets are usually built as matrices which is much easier to open with NumPy.
Turning a list to a NumPy array is pretty simple:
arr = np.arrays(list)
And printing the array would look something like this:
       [[  1  ,   2  ,   3  ],
        [  4  ,   5  ,   6  ],
        [  7  ,   8  ,   9  ]]
Another option is to open a CSV file using the np.genfromtxt() function:
arr = np.genfromtxt("file.csv", delimiter=",")
You can also save NumPy arrays to files by using np.savetxt(). For example;
Following line will save the array to a text file:
np.savetxt('file.txt', arr, delimiter=' ')
And the next line will save the array to a CSV file:
np.savetxt('file.csv', arr, delimiter=',')
The ndarray objects contains various types of attributes. Some of them are described below:
ndarray.ndim
Returns the number of axes (dimensions) of the array.
ndarray.shape
Returns the dimensions of the array. This is a tuple of integers indicating the size of the array in each dimension. For a matrix with n rows and m columns, shape will be (n,m). The length of the shape tuple is therefore the number of axes.
ndarray.size
Returns the total number of elements of the array. This is equal to the product of the elements of shape.
ndarray.dtype
An object describing the type of the elements in the array. Also, NumPy provides types of its own. numpy.int32, numpy.int16, and numpy.float64 are some examples.
ndarray.data
Returns the buffer containing the actual elements of the array.
Universal Functions
NumPy provides basic mathematical functions such as sin, cos, and exp. In NumPy, these are called “universal functions” (ufunc). In NumPy, these functions operate one by one each element of an array, and returns an array as output.
all, any, apply_along_axis, argmax, argmin, argsort, average, bincount, ceil, clip, conj, corrcoef, cov, cross, cumprod, cumsum, diff, dot, floor, inner, invert, lexsort, max, maximum, mean, median, min, minimum, nonzero, outer, prod, re, round, sort, std, sum, trace, transpose, var, vdot, vectorize, where.
Indexing, Slicing and Iterating
One-dimensional arrays can be indexed, sliced and iterated , just like lists and other array-like structures of Python.
import numpy as np
arr = np.array([1,2,3,4,5,6,10,84,99])
########################## INDEXING ##########################
print(arr) #OUTPUT: [1 2 3 4 5 6 10 84 99]
print(arr[5]) #OUTPUT: 6
print(arr[-1]) #OUTPUT: 99
print(arr[-5]) #OUTPUT: 5
########################## SLICING ###########################
print(arr[2:5]) #OUTPUT: [3 4 5]
print(arr[:3]) #OUTPUT: [1 2 3]
print(arr[7:]) #OUTPUT: [84 99]
print(arr[-3:-1]) #OUTPUT: [10 84]
print(arr[-3:]) #OUTPUT: [10 84 99]
########################## ITERATING #########################
for i in range(len(arr)):
print(arr[i])
#OUTPUT: PRINTS EACH ELEMENT OF ARRAY IN A NEW LINE
Multidimensional arrays can have one index per axis. These indices are given in a tuple separated by commas:
import numpy as np
arr = np.array([[1,2,3],[4,5,6],[10,84,99],[100,110,129]])
########################## INDEXING ##########################
print(arr)
#OUTPUT: [[  1   2   3]
#         [  4   5   6]
#         [  7   8   9]
#         [100 110 129]]
print(arr[0,1]) #OUTPUT: 2
print(arr[2,2]) #OUTPUT: 99
print(arr[-1,0]) #OUTPUT: 100
print(arr[-1,-1]) #OUTPUT: 129
print(arr[-3,-1]) #OUTPUT: 6
########################## SLICING ###########################
print(arr[1:4,2]) #OUTPUT: [6 99 129]
print(arr[2,1:3]) #OUTPUT: [84 99]
print(arr[1:4,1:3])
#OUTPUT: [[  5   6]
#         [ 84  99]
#         [110 129]]
########################## ITERATING #########################
for i in arr:
for j in i:
print(j)
#OUTPUT: PRINTS EACH ELEMENT OF ARRAY IN A NEW LINE.
#THIS METHOD CAN BE VERY TEDIOUS IF THE ARRAY IS OF HIGHER
#DIMENSION (FOR EXAMPLE 7) SO, THERE'S ANOTHER WAY TO DO SO:
for i in np.nditer(arr):
print(i)
#OUTPUT: PRINTS EACH ELEMENT OF ARRAY IN A NEW LINE.
See also
Indexing on ndarrays, Indexing routines (reference), newaxis, ndenumerate, indices
Shape Manipulation
An array has a shape given by the number of elements along each axis:
import numpy as np
arr1 = np.array([1,2,3,4,5,6,10,84,99])
print(arr1)
print(arr1.shape)
#OUTPUT:
# [1 2 3 4 5 6 10 84 99]
# (9,)
The shape of an array can be changed with various commands. But the following command will return a modified array, but do not change the original array:
import numpy as np
arr1 = np.array([1,2,3,4,5,6,10,84,99])
print(arr1)
print(arr1.shape)
#OUTPUT:
# [1 2 3 4 5 6 10 84 99]
# (9,)
arr2 = arr1.reshape(3,3)
print(arr2)
print(arr2.shape)
#OUTPUT:
# [[ 1  2  3]
#  [ 4  5  6]
#  [10 84 99]]
# (3,3)
# arr2 = arr1.reshape(3,2)
# print(arr2)
# print(arr2.shape)
# OUTPUT: THROWS ERROR AS 3*2=6 NOT 9
arr1 = np.array([1,2,3,4,5,6,10,84])
arr3 = arr1.reshape(2,2,2)
print(arr3)
print(arr3.shape)
#OUTPUT:
# [[[ 1  2]
#   [ 3  4]]
#
#   [ 5  6]
#   [10 84]]
# (2,2,2)
Functions and Methods Overview
Here is a list of some useful NumPy functions and methods names ordered in categories. See Routines for the full list.
Array Creation
arange, array, copy, empty, empty_like, eye, fromfile, fromfunction, identity, linspace, logspace, mgrid, ogrid, ones, ones_like, r_, zeros, zeros_like
Conversions
ndarray.astype, atleast_1d, atleast_2d, atleast_3d, mat
Manipulations
array_split, column_stack, concatenate, diagonal, dsplit, dstack, hsplit, hstack, ndarray.item, newaxis, ravel, repeat, reshape, resize, squeeze, swapaxes, take, transpose, vsplit, vstack
Questions
all, any, nonzero, where
Ordering
argmax, argmin, argsort, max, min, ptp, searchsorted, sort
Operations
choose, compress, cumprod, cumsum, inner, ndarray.fill, imag, prod, put, putmask, real, sum
Basic Statistics
cov, mean, std, var
Basic Linear Algebra
cross, dot, outer, linalg.svd, vdot
By:
20CE021 JIYA DESAI
20CE022 KALASH DESAI
20CE023 KAVIRAJ DESAI
