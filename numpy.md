# Arrays

Numpy uses its own version of arrays, called `ndarray` - more internally performant and with many built in functions.

## One dimensional arrays

#### `array` creates one dimensional arrays:

- `np.array([10, 12]) ` => `[10 12]`

#### `arrange` creates arrays from ranges, of integer values by default.

- Simple ranges:

  - `b = np.arange(3)` => `[0 1 2]`

- Complex ranges (start stop step):

  - `np.arange(1, 20, 3)` => `[ 1  4  7 10 13 16 19]`

#### `linspace` creates evenly spaced ranges of the form (start, stop, number of elements). Defaults to float values:

- `np.linspace(0, 100, 5)` => `[  0.  25.  50.  75. 100.]`

#### The optional parameter dtype changes the array elements' default type:

- `np.linspace(0, 100, 5, dtype=int)` => `[0  25  50  75 100]`

- `np.arange(3, dtype=float) ` => `[0. 1. 2.]`

#### `ones` returns a new array setting values to one:

- `np.ones(3)` => `[1. 1. 1.]`

#### `zeros` returns a new array setting values to zero:

- `np.zeros(3)` => `[0. 0. 0.]`

#### `empty` returns a new uninitialized array:

- `np.empty(3)` => `[0. 0. 0.]`

#### `random.rand` returns a new array with values chosen at random:

- `np.random.rand(3)` => `[0.70889123 0.60222273 0.4257288]`

## Multidimensional arrays

#### `array` works with higher dimensions (just add more params):

- `np.array([[1,2,3], [4,5,6]])` => `[[1 2 3]
[4 5 6]]`

#### a different option is to reshape a 1D array with `reshape`:

- `np.reshape(np.array([1,2,3,4,5,6]), (2,3))` => `[[1 2 3]
[4 5 6]]`

## Operations

#### the following attributes can be used to understand an `ndarray`:

- `ndarray.ndim`: - Number dimensions of the array (2 for 2D for example)
- `ndarray.shape` - Shape of the array. Each number in the tuple denotes the lengths of each corresponding dimension. For example, (2, 4) denotes 2 rows and 4 columns.

- `ndarray.size` - Total number of elements in the array.

#### basic math operations use intuitive operators:

- addition: `arr1 + arr2`
- substraction: `arr1 - arr2`
- multiplication: `arr1 * arr2`

#### broadcasting - multiplying vectors with a scalar - is supported:

- `np.array([1,2]) * 1.6`

#### slicing is also available:

- The syntax is `array[start:end:step]`
- defaults are `[0, endOfArray, 1]`
- it works multidimensionally. For example, this uses slice notation to get every row, and then pulls the second column:
  - `two_dim[:,1]` takes the column of index 1 (the second).
  - a good way to think about it is that the dimensions you don't want to touch get just `:` (which means 'taking the whole dimension)

#### stacking and splitting

- arrays can be stacked vertically or horizontally:

  - vertical stacking:

    ```
    np.vstack((
    [[1,1], [2,2]],
    [[3,3], [4,4]]
    ))
    ```

    => `[[1 1] [2 2] [3 3] [4 4]]`

  - horizontal stacking:

    ```
    np.hstack((
    [[1,1], [2,2]],
    [[3,3], [4,4]]
    ))
    ```

    => `[[1 1 3 3] [2 2 4 4]]`

- splitting is the opposite operation - dividing arrays

  - dividing horizontally in 2 parts of equal size:

    `np.hsplit([[1 1 3 3] [2 2 4 4]], 2)` => `[array([[1, 1], [2, 2]]), array([[3, 3], [4, 4]])]`

  - is an exact division is not possible a valueError would be raised.
  - splitting at an index is also possible, at one or several indexes:

    ```
    array = np.array([
        [1, 2, 3, 4],
        [5, 6, 7, 8],
        [9, 10, 11, 12],
        [13, 14, 15, 16]
        ])

        split_array = np.hsplit(array, [1, 3])
    ```

    =>

    ```
    [
        array([[ 1], [ 5], [ 9], [13]]),
        array([[ 2,  3], [ 6,  7], [10, 11], [14, 15]]),
        array([[ 4], [ 8], [12], [16]]
    )]`
    ```

  - the previous technique is equivalent to slicing, but more convenient when splitting on several place.

#### solving systems of equations:

- Given a matrix of coefficients A, and a vector of the free (right side) coefficients b, `np.linalg.solve(A, b)` would return a solution to the system return a solution to the system.
- the function will throw LinAlgError if a is singular or not square.

#### determinant

- `np.linalg.det(A)` will return the determinant of a (square) matrix.

### plotting lines: matplotlib

- previous import of the package is required:
  `import matplotlib.pyplot as plt `
- each linear equation can be represented by a line in a plane. Given a system:

  - we stack the coefficient matrix and vector:

    `A_system = np.hstack((A, b.reshape((2, 1))))`

  - then we plot:

    `plot_lines(A_system)`

### vectors

#### scalar multiplication

- simply multiply the vector by a number: `4*v`

#### sum of vectors

- regular operator works: `v + w`

#### norm of a vector

`np.lingalg.norm(v)`

#### dot product

- `np.dot(x,y)` works with numpy arrays and regular lists
- the equivalent form `x @ y` works only with numpy arrays
- both versions are far more performant than a regular loop

#### matrix multiplication

- `np.matmul(A, B)` will multiply the two matrices
- `A @ B` also works as an alternative nomenclature
- for dimensions that aren't compatible with multiplication, a ValueError will be raised
- an exception is vector multiplication - when done with `.matmul`, it will work (meaning that the second vector will be automatically transposed)