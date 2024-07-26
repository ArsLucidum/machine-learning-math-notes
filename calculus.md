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



