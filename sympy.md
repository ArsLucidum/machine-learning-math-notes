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


## Symbolic Diferentiation

sypmy can be used to find derivatives:

`diff(x**3,x)` => $3x^2$

it applies the sum, product and chain rules automatically.

sometimes there are limitations about differentiation with symbolic expressions. For example, evaluating derivatives of functions with jumps fail to evaluate expressions producing complicated functions - something called function swell.

## Numerical Differentiation

This is a method that does not take into account the function expression, but rather just approximates the derivative by using the values for the points at $x$ and $x + dx$.

`np.gradient` is one of the functions that can be used for this method.

Different implementations of this idea have different performance, but they all produce only aproximate results. 

Besides lack of precision - which is not usually a problem, since it can be accurate enough for ML applications - some downsides of numerical differentiation are inaccuracy at jumps in the function (just like symbolic differentiation), and most importantly, slow speed - performing function evaluation for hundreds of derivatives can be a problem in ML uses.

## Automatic Differentiation

This third method, which is the most commonly used, is based on breaking down a function in common function ($sin$, $cos$, $log$, etc) to build a computational graph, so that the derivative can be computed later using the chain rule. 

The ability to 'compile' the graph function at the time of building the network, saving computational time later, makes it interesting for ML.

The main disadvantage is difficulty of implementation, but there are some libraries available that provide this functionality, like JAX:

Given a previously defined function f, `grad(f)(3.0)` will return the derivative at 3 (integers cannot be used). Broadcasting can be used to find derivatives for a whole function, by using vmap: `vmap(grad(f))(x_array_jnp)`.



