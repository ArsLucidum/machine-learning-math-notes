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

#### Slicing is also available:

- The syntax is `array[start:end:step]`
- defaults are `[0, endOfArray, 1]`
- it works multidimensionally. For example, this uses slice notation to get every row, and then pulls the second column:
  - `two_dim[:,1]`
    (`:` takes all in the first dimension (whole row), `1`take that index in the column)
