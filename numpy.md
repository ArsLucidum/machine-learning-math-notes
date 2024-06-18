# Arrays

Numpy uses its own version of arrays, called `ndarray` - more internally performant and with many built in functions.

## One dimensional

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

#### `ones` returns a new array setting values to one.

- `np.ones(3)` => `[1. 1. 1.]`

#### `zeros` returns a new array setting values to zero.

- `np.zeros(3)` => `[0. 0. 0.]`

#### `empty` returns a new uninitialized array.

- `np.empty(3)` => `[0. 0. 0.]`

#### `random.rand` returns a new array with values chosen at random.

- `np.random.rand(3)` => `[0.70889123 0.60222273 0.4257288]`
