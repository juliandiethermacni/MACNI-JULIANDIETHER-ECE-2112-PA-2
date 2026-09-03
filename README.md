# ECE-2112 - Programming Assignment 2
**By: Macni, Julian Diether J. | 2ECE-B**
### Overview
This repository contains the Programming Assignment 2 for ECE 2112 - Advanced Computer Programming and Algorithms. The problems for this assignment covers Module 2, which covers concepts related to the NumPy library such as arrays and how they can be created and edited.

## A. Reproducible Normalization Problem
**Objective:** Create a 5 x 5 array consisting of positive integers and get its normalized form as well as the mean and standard deviation of the normalized array.

The following functions or methods were used in this problem:

• In order to get a random set of numbers for the array, the following code was used:
``` python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
```
which gives a random 5 x 5 array of integers

• The following formula was then used to get the normalized form of the generated array:
```
Z = (X − x) / σ
```
in which x is the mean (using `np.mean(X)`) and σ is the standard deviation (using `np.std(X)`).

With this formula, the normalized array can then be coded using:
``` python
X_normalized = (X - np.mean(X)) / np.std(X)
```

These methods were combined in order to get the normalized array, its mean as well as its standard deviation:
``` python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))

X_normalized = (X - np.mean(X)) / np.std(X)

mean = np.mean(X_normalized)
standard_deviation = np.std(X_normalized)
```

The array was also saved using:
``` python
np.save("X_normalized.npy", X_normalized)
```




## B. Cubes Divisible by 4 Problem
**Objective:** Create a 10 x 10 array of the cubes of the first 100 positive integers and then uses this array to make another one consisting of every cubed value divisible by 4.

The following functions or methods were used in this problem:

• `np.arange(a, b, c)` - generates an array of evenly spaced values from a to b, in which c is the step value

Example: 
``` python
np.arange(1, 12, 2) #starts at 1 and increases every 2 times, and then stops before 10
```
which results to `array([ 1,  3,  5,  7,  9, 11])`

 • `reshape()` - changes the shape of the array
 
 Example:
 ``` python
array = np.arange(1, 12, 2)
array.reshape(3, 2)
```
which results to:
``` python
array([[ 1,  3],
       [ 5,  7],
       [ 9, 11]])
```

• `.shape` - displays the shape of the array

Example:
``` python
array = np.arange(1, 12, 2).reshape(3, 2)
array.shape
```
which displays `(3, 2)`

* `.size` - displays the number of elements in the array

Example:
``` python
array = np.arange(1, 12, 2).reshape(3, 2)
array.size
```
which displays `6`

• **Subsetting** - used to get certain elements from the array or structure

Example:
``` python
array = np.arange(1, 12, 2).reshape(3, 2)
array[array % 3 == 0]
```
which results to `array([3, 9])`

These methods were combined in order to get the array consisting of cubed integers divisible by 4, as well as getting to know the shape of the array and the number of elements:
``` python
C = np.arange(1, 101, 1).reshape(10, 10) ** 3
C.shape
div_by_4 = C[C % 4 == 0]
div_by_4.size
```

The array was also saved using:
``` python
np.save("div_by_4.npy", div_by_4)
```




## C. Above-Mean Sqaures Problem
**Objective:** Create a 6 x 6 array containing squares of the first 36 positive integers, compute its mean, and then use boolean filtering to make an array of integers only above the mean.

The following functions or methods were used in this problem:

• `np.arange(a, b, c)` - generates an array of evenly spaced values from a to b, in which c is the step value

• `reshape()` - changes the shape of the array

• `np.mean()` - gets the mean of the array

• `.size` - displays the number of elements in the array

• **Subsetting** - used to get certain elements from the array or structure

These methods were combined in order to get the array for the squares of the first 36 positive integers, and another array that are above the mean, as well as to know how many elements are in the array:
``` python
S = np.arange(1, 37, 1).reshape(6, 6) ** 2
S_mean = np.mean(S)
above_mean = S[S > S_mean]
above_mean.size
```

The array was also saved using:
``` python
np.save("above_mean.npy", above_mean)
```

Thank you for reading!
