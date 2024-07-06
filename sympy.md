## Introduction
Sympy is a python library used for symbolic mathematics.

It can represent mathematical objects exactly and not in approximate numerical form. For example, it can manipulate $\sqrt{2}$ rather than $1.41421356237$.

symbolic objects are created:

`a = sqrt(18)` => $\sqrt(18)$

but numerical evaluation can be requested to an optional degree of precision:

`N(sqrt(18),8)` => $4.2426407$

Variables are defined using **symbols**, which need to be predefined:

```
x, y = symbols('x y')
expr = 2 * x**2 - x * y
```
=> $2𝑥^2−𝑥𝑦$

then the expression can be further manipulated: 

`expr_manip = x * (expr + x * y + x**3)` 

=> $𝑥(𝑥^3+2𝑥^2)$

some of the available features are:

- expanding expressions: 

`expand(expr)`

- factorising expressions:

`factor(expr)`

- evaluating expressions for specific variable values: 

```
f_symb = x ** 2
f_symb.evalf(subs={x:3})
```
## Interaction with numpy

Sympy does not understand numpy objects like arrays. Given a numpy array, and a sympy expression:

```
x = sp.symbols('x')
f_symb = x**2

x_array = np.array([1, 2, 3, 4])
```
By default those objects would be compatible. However, using helper functions they can interact:

```
from sympy.utilities.lambdify import lambdify

# Create a NumPy-compatible function from the SymPy expression
f_symb_numpy = lambdify(x, f_symb, 'numpy')

print(df_symb_numpy(x_array))

```
=> $[1,  4, 9]
$


## Diferentiation

sypmy can be used to find derivatives:

`diff(x**3,x)` => $3x^2$

it applies the sum, product and chain rules automatically.

