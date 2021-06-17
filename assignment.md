# Numpy

## Part 1: Array Slicing and Indexing

1. Given a 2D numpy array `X`, write the syntax used to select the first 3 rows and the last 3 columns of `X`.

1. Given a 1D numpy array `x`, write the syntax used to return only the odd-indexed entries (return every other entry) of `x`.
   There is more than one solution!

1.  Given an integer numpy array of 0's and 1's, write a function that creates a new array where 0's are replaced with the word `"red"` and 1's are replaced with the word `"blue"`.

    ```python
    x = np.array([0, 0, 1, 0, 1]) 
    color_replace(x)
    >>> array(["red", "red", "blue", "red", "blue"])
    ```

1. Given a square numpy array `X`, write a function that replaces the diagonal elements with a given constant. Hint: you can use ONE for loop in this function!

    ```python
    X = np.random.randint(1, 11, size=(6, 6))
    X
    >>> array([[ 7, 10,  4,  1, 10,  5],
               [ 3, 10,  4,  1,  3, 10],
               [ 2,  7,  4,  8,  8,  1],
               [ 6,  4,  2, 10,  8,  3],
               [10,  9,  6,  6,  5,  2],
               [ 1,  7,  2,  9,  7,  6]])
    diagonal_replace(X, 0)
    >>> array([[ 0, 10,  4,  1, 10,  5],
               [ 3,  0,  4,  1,  3, 10],
               [ 2,  7,  0,  8,  8,  1],
               [ 6,  4,  2,  0,  8,  3],
               [10,  9,  6,  6,  0,  2],
               [ 1,  7,  2,  9,  7,  0]])
    ```
1. Given two equal length arrays, `x` with some general numeric data, and `b` an array of booleans, write a function that computes the sum of the data in `x` at the same positions where `b` is True, and the sum of the values in `x` at the positions where `b` is False.

    ```python
    x = np.array([0,    1,    2,     3,    4,     5])
    b = np.array([True, True, False, True, False, False])
    compute_true_false_sums(x, b)
    >>> {True: 4, False: 11}
    ```

1.  Given a two-dimensional array `M`, create a new two-dimensional array containing only the *columns* of `M` where at least one of the entries is negative.

    ```python
    M = np.array([[ 0.5,  0.2, -0.3,  0. ],
                  [ 0.4,  0.3,  0.3,  0.4],
                  [-0.2, -0.4,  0.1,  0.4]])
    select_negative_columns(M)
    >>> array([[ 0.5,  0.2, -0.3],
               [ 0.4,  0.3,  0.3],
               [-0.2, -0.4,  0.1]])
    ```

## Part 2: Applying Operations

Start with array `a = np.arange(10)`. 

1. Take the natural log of the entire array a.

1. Compute the cumulative sum of array a.

1. Write a function that consumes a two-dimensional numpy array (so, a matrix), and a label which is either "row" or "column".  The function should return a one-dimensional numpy array (vector) with either the row or column averages.

    ```python
    X = np.array([[0, 1], [2, 1]])
    row_or_column_means(X, label="row")
    >>> array([0.5, 1.5])
    row_or_column_means(X, label="column")
    >>> array([1.0, 1.0])
    ```

1. Subtract the row mean from each row of a two-dimensional array (element by element).

    ```python
    x = np.array([
        [0, 1, 0, 1],
        [1, 1, 1, 1],
        [1, 2, 3, 4]])
    subtract_row_means(x)
    >>> array([
      [-0.5,  0.5, -0.5,  0.5],
      [ 0. ,  0. ,  0. ,  0. ],
      [-1.5, -0.5,  0.5,  1.5]])
   ```

1. Given an array and a number, find the index of the number in the array that is closest to the input number. 
(Hint: check out the functions/methods that start with `arg`!)

    ```python
    x = np.random.randint(100, size=10)
    x
    >>> array([89, 55, 76,  4, 12, 86, 18, 18, 30, 88])
    get_closest_idx(x, 11)
    >>> 4
    ```
   
## Part 3: Broadcasting

1. Same size broadcasting: start with arrays `x` and `y`:
    ```python
    x = np.array([1, 2, 3, 4, 5, 6])
    y = np.array([2, 4, 6, 8, 10, 12])
    ```
   Compute the element-wise: sum, difference, product, division, and modular division of `x` and `y`.

1. Single digit broadcasting: continue using array `y` defined above. 
   Compute the element-wise: sum, difference, product, division, and modular division of `y` and 2.

1. Broadcasting conditionals: Continue using arrays `x` and `y` defined above. Use conditional statements to get an elementwise boolean array for:
    * elements of `y` that are greater than 5
    * elements of `x` that are divisible by 2 (hint: modular division by 2 leaves 0 remainder)

1. Broadcasting in multiple dimensions: Let's start with a new array `x`, 
    ```python
    x = np.ones((5, 4))
    ```
   Try a broadcasting operation (e.g. multiplication) with `x` and array `a = np.array([1, 2, 3, 4])`.
   
   What happens if you try to broadcast `x` with array `b = np.array([1, 2, 3, 4, 5])`? Can you reshape `b` to make this work?
   
   What other shapes of arrays can be broadcast with `x`?


