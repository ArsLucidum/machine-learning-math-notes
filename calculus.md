### Derivatives

A derivative is the instantaneous rate of change of a function.

A derivative equal of 0 means zero rate of change.

Lagrange's notation for the derivative is as follows:

given a function $y = f(x)$, the derivative can be either expressed as:

- Lagrange's notation:  $f'(x)$   
- Leibniz's notation:  $\frac{dy}{dx} = \frac{d}{dx}f(x)$ 

#### Common derivatives:

##### derivative of a constant:
  
$$
f(x) = k  \\
f'(x) = 0
$$

##### derivative of a line:
$$
f(x) = ax + b \\
f'(x) = a
$$

##### derivative of quadratic functions:

$$
f(x) = x^2 \\
f'(x) = 2x
$$

##### derivatives of power functions in general:

$$
f(x) = x^n \\
f'(x) = n x^{n-1} 
$$

It also works for negative $n$: 

given $f(x)= \frac{1}{x} = x^{-1}$, 

then  $f'(x) = (-1)x^{-2} = - \frac{1}{x^2}$

##### inverse function and its derivative:

The inverse function $f^{-1}(x)$ is a function that undoes what the original function does, so that $f^{-1}(f(x)) = x$.

If $g$ is the inverse of $f$, the derivative of the inverse function follows the following formula:

$$
g'(x) = \frac{1}{f'(x)}
$$

#### derivatives for trigonometric functions:
$$
f(x) = \sin(x) \\
f'(x) = \cos(x)
$$

$$
f(x) = \cos(x) \\
f'(x) = -\sin(x)
$$

$$
f(x) = \tan(x) \\
f'(x) = \sec^2(x)
$$

#### $e$ and its derivative

The number $e$ is a mathematical constant defined as:

$$
e = \lim_{n \to \infty} (1 + \frac{1}{n})^n
$$

One of it's interesting properties is present in the function $f(x)= e^x$, which is it's own derivative: $f'(x) = e^x$.

#### logarithms 

(here using $log$ always refers to the natural log, $ln$)

A logarithm is the inverse of the exponential of e, because:

- $e^{log(x)} = x$
- $log(e^y) = y$

for the log function, its derivative is:

$f(x) = log(x)$

$f'(x) = \frac{1}{x}$

#### Existence of the derivative

Not all functions have a derivative in all points.

Non differentiable points exist wherever tangents can not be well defined - corners, discontinuities, vertical tangents, etc. A function is called differentiable in an interval if it is differentiable in all points of the interval.

#### Properties of the derivative

##### multiplication by scalars

given $f = cg$, then $f' = cg'$

##### sum rule

given $f = g+ h$, then $f' = g' + h'$

##### product rule

given $f = gh$, then $f' = g'h + gh'$

##### chain rule

given $f = g(h(t))$, then $f' = g'(h(t)) h'(t)$

or, perhaps clearer with Leibniz's notation:

$\frac{dy}{dx}= \frac{dy}{du} \frac{du}{dx}$


### Square loss (Mean Squared Error, MSE)


This is a function commonly used in machine learning as a loss function.

The idea is to calculate the difference between the actual value and the predicted value. Then the difference is squared, to both ensure all errors are positive and to penalize larger errors more:

$(y−\hat{y}​)^2$

For many predictions, the formula is the average:

MSE = $\frac{1}{n}\sum\limits_{i=1}^{n}(y_i−\hat{y_i}​)^2$


### Partial derivatives

A partial derivative of a function of several variables is its derivative with respect to one of those variables, with the others held constant.

they are denoted by the symbol $\partial$, read as 'partial' or 'del'.

Given a function $f(x,y)$ its two partial derivatives are defined as:

$\frac{\partial f}{\partial x} = \lim_{\Delta x \to 0} \frac{f(x + \Delta x, y) - f(x, y)}{\Delta x}$

$\frac{\partial f}{\partial y} = \lim_{\Delta y \to 0} \frac{f(x, y + \Delta y) - f(x, y)}{\Delta y}$

### Gradients

Given a function of several variables $f(x_1,x_2, \dots  x_n)$, the gradient is a vector that contains all its partial derivatives.

it is denoted using the gradiant operator (pronounced 'grad'), with the symbol  $\nabla$ (nabla):

$\nabla f(x,y) = [\frac{\partial f}{\partial x},\frac{\partial f}{\partial y}]$

The gradient points in the direction of the steepest ascent of the function - given a point on a hill described by $f$, the gradient would point in the direction that gets you uphill the fastest. 

The magnitude of the gradient represents the rate of increase in that direciton (larger magnitude implies steeper ascent).

The gradient vector is normal to the tangent plane (or more generally, the tangent n-1 dimensional space) of the function. In a way, the vector defines this tangent plane, since it provides by itself enough information to construct the plane's equation.

Just like finding local minimums and maximums in single variable functions involves finding the places where $f'(x) = 0$, in multivariable calculus those points can be found by solving for each partial derivative equal 0.

### Gradient descent

Gradient Descent is an optimization algorithm used to find the minimum of a differentiable function in a performant way. It involves iteratively moving towards the steepest descent.

Given a function $f(\mathbf{x})$, where $\mathbf{x}$ is a parameter vector, the idea is: 

- start with an initial guess
- calculate the gradient $\nabla f(x)$ at the current point
- update the parameters according to the update rule
- repeat the system until reaching a threshold or maximum number of iterations.

The update rule is as follows:


$\mathbf{x}_{k+1} = \mathbf{x}_k - \alpha \nabla f(\mathbf{x}_k)$

where:

-  $\mathbf{x}_k$ is the current value of the parameter vector 
- $\alpha$ (alpha) is the learning rate, sometimes also expressed as $\eta$ (eta), a small positive number that controls the size of the steps towards the minimum - choosing a good value for it is a complex problem in itself. 

There are several drawbacks to gradient descent: learning rates too large risk jumping over the minimum, while rates too small can take forever to optimize; there's also a posibility of getting stuck in a local minimum, which is usually adressed by running the algorithm many times with different starting points and learning rates.


### Newton's method

Newton's method can be used as an alternative method to gradient descent for optimization.

Newton's method, in its original form, is used to quickly find iteratively the intercept of a function with 0. 

The idea is to start at a point $f(x_1)$, calculate its tangent line, and then find the point where that tangent intercepts the 0 axis. taking that point as $x_2$, one then takes the tangent line to $f(x_2)$, and so on.

The formula for an update in its original form is:

$x_{k+1} = x_{k} - \frac{f(x_k)}{f'(x_k)}$

In our case, given a function $g$ to minimize, we want to find zeros of its derivative $g'$, so the formula becomes:

$x_{k+1} = x_{k} - \frac{g'(x_k)}{(g'(x_k))'}$

### Second derivative

The second derivative of a function is the derivative of its derivative.

A second derivative indicates curvature: 

- $\frac{d^2x}{dt^2} > 0$ means the function is convex (concave up). If the first derivative is 0, it's a local minimum
- $\frac{d^2x}{dt^2} < 0$ means the function is concave (concave down).If the first derivative is 0, it's a local maximum

- $\frac{d^2x}{dt^2} = 0$ is inconclusive information.

### The Hessian

In multivariable calculus, just like a first derivative becomes the $\nabla f$ gradient vector, the second derivative becomes a matrix:

$$
H(x,y) = \begin{bmatrix}
f_{xx}(xy) && f_{xy}(x,y) \\
f_{yx}(xy) && f_{yy}(x,y) \\
\end{bmatrix}
$$

Concavity works with the hessian in a similar way as it does with the second derivative for single variable calculus.

In this case, to know if a matrix is concave, we look at the eigenvalues: 

- If both are positive, then the matrix is positive definite and the function is concave up. 
- If both are negative, then the matrix is negative definite and the function is concave down.
- otherwise, we cannot conclude anything.

### Newton's method - multivariable calculus

For multivariable functions, Newton's method substitute the first derivative for the gradient and the second for the hessian:

$
\begin{bmatrix}
x_{k+1} \\
y_{k+1} \\
\end{bmatrix} = \begin{bmatrix}
x_{k} \\
y_{k}
\end{bmatrix} - H^{-1}(x_k,y_k) \nabla f (x_k,y_k)
$

(The order of multiplication is not interchangeable due to its dimension)