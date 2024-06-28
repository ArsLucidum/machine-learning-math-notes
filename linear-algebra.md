# Linear algebra

## Matrix representation of a system of equations

Systems of equations can be represented using matrices by creating a coefficient matrix, a variable vector, and a constants vector.

Given a system like:

$$
\begin{equation*}
\begin{cases}
2x + 3y = 5 \\
x - y = 1
\end{cases}
\end{equation*}
$$

The **coefficient matrix** 𝐴 consists of the coefficients of 𝑥 and 𝑦 in each equation:

$$
A = \begin{bmatrix}
2 & 3 \\
1 & -1
\end{bmatrix}
$$

The **variable vector** x contains the variables of the system:

$$
\mathbf{x} = \begin{bmatrix}
x \\
y
\end{bmatrix}
$$

And the **constants vector** b contains the constants from the right-hand side of the equations:
% Constants Vector

$$
\mathbf{b} = \begin{bmatrix}
5 \\
1
\end{bmatrix}
$$

The full matrix equation would then be:

$$
A\mathbf{x} = \mathbf{b}
$$

or, expanded:

$$
\begin{bmatrix}
2 & 3 \\
1 & -1
\end{bmatrix}
\begin{bmatrix}
x \\
y
\end{bmatrix}
= \begin{bmatrix}
5 \\
1
\end{bmatrix}
$$

## Linear independence

Two vectors/rows of a matrix are called linearly independent if they can not be expressed as linear combinations of each other.

in practical terms, independent vectors provide unique directions in space, so they can't be built from each other. Three vectors that are independent exist in 3D space, while three vectors where one is linearly dependent would fit on a plane.

Given a system of linear equations, if the rows of the coefficient matrix are linearly independent, then the system does not have redundant equations.

## Types of systems and singularity

Systems of equations can be classified by several definitions:

A system is called a **Complete system** when the number of independent equations matches the number of variables. This means that in complete systems, the coefficient matrix is a square matrix.

**Non-complete** systems have non-square coefficient matrices. This is either because they too many equations to be square (**Overdetermined systems**), or because they have too few equations to be square (**Underdetermined systems**).

Complete systems are called **Non-singular** when the rows of its coefficient matrix are linearly independent.

Non-singular systems always have one single solution.

In contrast, **Singular systems** are those whose coefficient matrix has some linearly dependent rows.

Singular systems never have a single solution. Either they have infinite solutions (because the system is **Redundant**, with some equations not providing new information) or they have no solution at all (because the system is **Inconsistent**, with some of the equations contradicting each other).

'Singular system' sounds counterintuitive as a name, given that the sytems with a single (singular) solution are the non-singular ones. The reasoning behind this name is in the use of 'singular' as in 'exceptional': Singular matrices are an infinitesimally small subset of matrices - the few ones to meet specific criteria.

Geometrically, Matrices represent transformations of space. Non-singular matrices represent transformations that preserve dimensionality (rotations, scaling, etc), while singular matrices represent collapsing space into a lower dimention (projecting 3D space into a 2D plane for example).

## Determinant

The determinant of a square matrix is a scalar value that provides important information about said matrix. Particularly, a determinant equal to zero lets us know that the matrix is singular.

Singularity is formally defined as having determinant equal to 0. The determinant is only defined for square matrices, which is why singularity, as a concept, only applies to complete systems.

The formula to calculate the determinant of a 2x2 matrix is:

$$
\det\left(\begin{bmatrix} a & b \\
c & d \end{bmatrix}\right) = ad - bc
$$

Which has the geometric meaning of "the area of the parallelogram formed by the column vectors of the matrix".

Higher dimensional determinants have similar meaning in Nth dimensional space.

This means that, geometrically, the determinant quantifies how the matrix transforms space - its scaling factor. A determinant greater than one shows that the matrix stretches volumes, while a determinant lower than 1 compresses them. A negative determinant indicates flipping - a reversal of orientation.

A determinant of 0 then is geometrically interpreted as a transformation that maps higher dimensional objects into a lower-dimensional space - a 3d space into a plame, for example - which fits with the concept of singularity.

An interesting property of the determinant is that the  product of the determinants of two matrices is equal to the determinant of the matrix produced by multiplying the matrices themselves. This is intuitive when thinking of matrices as linear transformations, and of the determinant as the area of the resulting area of the basis vectors.

Through the previous property, it can be seen that the product of a singular and a non singular matrix is singular - the product where one of the determinants is zero will necessarily be zero as well, signifying that the produced matrix is singular.

Another consequence is that the determinant of an inverse matrix is equal to the inverse of the determinant of the original matrix (when the matrix is invertible). This can be deduced this way:

considering that 

$$
det(AB) = det(A)det(B)  
$$

then 

$$
det(A)*det(A^{-1}) = det(AA^{-1})
$$

and since $AA^{-1}$ is the identity matrix, with determinant equal to 1, then:

$$
det(A^{-1}) = \frac{1}{det(A)}
$$


## Rank

The rank of a matrix is its maximum number of linearly independent rows or columns. The number of independent rows is always equal to the number of independent columns. Intuitively, it represents the number of dimensions in which the matrix can spread out vectors - how many directions in space the matrix's transformation affects.

The determinant can help understand the rank of a matrix. When the determinant is non-zero, and therefore the matrix is non-singular, the rank is equal to the matrix size - all its rows/columns are linearly independent. A determinant equal to zero implies the rank is less than the size of the matrix (we don't know exactly what size). The rank can then be calculated by methods such as Gausian elimination.

## Identitity

An identity matrix $𝐼_𝑛$ is a square matrix with ones on the diagonal and zeros elsewhere. For example, the identity matrix of size 3 is:

$$
I_3 = \begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

It is important because multiplying any matrix by it leaves the original unchanged - it represents a transformation that leaves all vectors as they were, just like multiplying any number by 1 results in the original number.

## Inverse

The inverse of a matrix is another matrix that, when multiplied by the original one, results in the identity matrix. That is, given a matrix A, the inverse is the matrix $A^{-1}$, for which:

$$
A A^{-1} =A A^{-1} = I \
$$

Only non-singular matrices have inverses - and all of them have an inverse.

In geometric terms, the inverse of a matrix represents a transformation that reverses the effect of the original transformation. For example, if matrix 𝐴 represents a transformation that scales, rotates, or shears a vector, $A^{-1}$
will undo this transformation.

The lack of an inverse implies that the operation is destructive - by definiton, there is no transformation that undoes the change. Singular matrices don't have an inverse because its transformation projects a higher dimension into a lower one - there is not enough information in the result to go back to the original state, since there are many original states that could have lead to that result.

## Solution space

The solution space of a system of linear equations is the set of all possible solutions that satisfy all equations simultaneously. In other words, it is the set of all vectors $x$ that satisfy $Ax = b$.

The dimension of the solution space (also called _nullity_) of A is equal to $n - rank(A)$, where n is the number of columns of A.

## Row echelon form

The row echelon form of a matrix s a simplified version of the original matrix that satisfies three conditions:

- each first non-zero entry (_leading entry_ or _pivot_) is 1, and its to the right of the previous leading entry.
- the rows made fully of zeros are at the bottom.
- all entries below a leading entry are zeros.

The rank of a matrix is the number of non-zero rows in its row echelon form.

## Reduced row echelon form

the reduced row echelon form is a stricter variation of the row echelon form that satisfies an extra condition:

- each leading 1 is the only non-zero entry in its column.

unlike the row echelon form, the reduced version is unique per matrix.

## Vector recap

### Norms

- The $L1$ norm, also known as taxicab distance, is the sum of the absolute values of all components.

- the $L2$ norm, or euclidean distance, is equal to:

$$
d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2 + (z_2 - z_1)^2 + \cdots + (w_2 - w_1)^2}
$$

### Operations

- sum/difference of vectros are simply the sum/difference of its components (only defined for vectors of equal size).

- multiplication of vectors by a scalar also work by multiplying by coordinate

- the traspose of a vector (or matrix) turns rows into columns.

### Dot product

- the dot product is the sum of all coordinates' products (the l2-norm is the square root of the vector with itself).

$$
\mathbf{a} \cdot \mathbf{b} = \sum_{i=1}^n a_i b_i
$$

- it is related to the angle between the vectors: ortogonal vectors have dot product equal to 0.

### Matrix multiplication by a vector

We can think of matrix multiplication by a vector as a dot product of each of the rows by the vector, returning a column vector with the result of each dot product. The number of columns in the matrix must therefore equal the length of the vector.

#### Linear transformations

A linear transformation is a rule that takes each vector in one space and transforms it to a vector in another space. Linear transformations can be represented by matrices.

We can represent a transformation as a matrix by applying the transformation to the standard basis vectors. The standard basis vectors are those that have one component equal to 1 and all other components equal to 0 - They are trivially linearly independent, and they span the space.

Linear transformations can be visually represented as scaling, shearing, rotation, etc. of the original vector space.

#### Matrix multiplication

matrices can be multiplied, and its result can be thought of as a composition of the linear transformations they represent.

Conditions for multiplication are that the number of columns of the first matrix must match the number of rows of the second, and the resulting matrix has as many rows as the first matrix and as many columns as the second If $A$ is an $m \times n$ matrix and $B$ is an $n \times p$ matrix, their product $C$ will be an $m \times p$ matrix..

The calculation itself can be thought of as a combination of dot products for the rows and colums of the matrices. For example, if $A$ and $B$ are both $2 \times 2$ matrices:


$$
A = \begin{bmatrix} 
a_{11} & a_{12} \\ 
a_{21} & a_{22} 
\end{bmatrix}
$$

$$
B = \begin{bmatrix} 
b_{11} & b_{12} \\ 
b_{21} & b_{22} 
\end{bmatrix}
$$

Then their product $C = A \times B$ is:

$$
 C = \begin{bmatrix} c_{11} & c_{12} \\ c_{21} & c_{22} \end{bmatrix}
$$

Where:

$$ c_{11} = a_{11} b_{11} + a_{12} b_{21} $$

$$ c_{12} = a_{11} b_{12} + a_{12} b_{22} $$

$$ c_{21} = a_{21} b_{11} + a_{22} b_{21} $$

$$ c_{22} = a_{21} b_{12} + a_{22} b_{22} $$

## Eigenvalues and eigenvectors

### Span

The span of a set of vectors is the set of all possible linear combinations of these vectors - the collection of all vectors that can be made by scaling and adding those vectors togeteher. 

Saying that a set of vectors spans a space V means that all vectors in V can be written as a combination of those vectors

### Basis

A basis of a vector space is a set of vectors that satisfy two conditions:

- they are linearly independent
- they span said vector space.

The basis must be minimal, meaning that no vector can be removed from the basis without losing the ability to span the space - this is implied by the linear independence requirement. 

Any basis has the same amount of elements in the set as the dimension they span (so for example, a 2D space has 2 vectors as its basis).

### Eigenvectors 

Given a linear transformation represented by the matrix A, an eigenvector v for it is a non-zero vector that satisfies the equation $Av = \lambda v$. 

In simpler words, an eigenvector is a vector in a direction that is not changed by the transformation, except for being scaled (stretched or shrunk) by a factor $\lambda$, which we call an **eigenvalue**.

Eigenvectors and eigenvalues are interesting because they allow to substitute some complex operations (matrix multiplications) for simple/more performant constant multiplication.

Another interesting property is that the determinant of a matrix is the product of its eigenvalues. The proof is left aside because it is a bit lengthy in the general case, and only immediately intuitive for diagonalizable matrices.

### Eigenbasis

An eigenbasis of a matrix A is a basis formed by eigenvectors that span A's vector space.

### Finding eigenvalues and eigenvectors

Eigenvectors of a matrix behave as those of a diagonal matrix (they only stretch).  Written mathematically, there are infinite (x,y) for which:

$$
A \begin{bmatrix}
x \\
y \\
\end{bmatrix}
=\begin{bmatrix}
\lambda & 0 \\
0 & \lambda  \\
\end{bmatrix}
\begin{bmatrix}
x \\
y \\
\end{bmatrix}
$$


The process of finding eigenvectors and eigenvalues involves two steps:

- Finding for which diagonal matrices ($\lambda I$) our matrix behaves like them in some vectors - those lambdas are  eigenvalues.
- Once we know those diagonal matrices, we find out which vectors are behaving like them in our matrix - those are  eigenvectors.


Starting from the previous equation, if we move that $\lambda I$ matrix to the left side:

$$
(A - 
 \begin{bmatrix}
\lambda & 0 \\
0 & \lambda  \\
\end{bmatrix}
)
 \begin{bmatrix}
   x \\
   y \\ 
\end{bmatrix}
 = 0
$$


which means that $A-\lambda I$ is singular, since it's squashing at least some vector into zero. And given that it is singular:

$$
det(A-\lambda I) = 0
$$

expanding this determinant produces what's known as the **charasteristic polynomial** of A, and its roots when solving for $\lambda$ are the matrix' eigenvalues.

once we have the eigenvalues we can calculate the corresponding eigenvectors by solving, for each one, 

$$
(A - \lambda I)v = 0
$$ 

each v found this way is an eigenvector of A.

### Projections

A matrix can be projected into a lower dimension (a line, for example).

to project A matrix A onto a vector V, we  need to multiply the matrix by the vector, and then divide by its norm:

$$
A_p = A \frac{v}{||v||_2}
$$

since A is an $(m*n)$ matrix, and v is $(n*1)$, the resulting matrix $A_p$ will be $(m*1)$

Projecting to a two-vector matrix would be equivalent to projecting into the plane those vectors form. So in general:

$$
A_p = A \begin{bmatrix} 
\frac{v_1}{||v_1||_2}
\frac{v_2}{||v_2||_2}
...
\frac{v_n}{||v_n||_2}
\end{bmatrix}
$$

### Covariance matrix

A covariance matrix uses the concept of **variance** from statistics, which will not be described here but can be thought of as a measure of how spread out the data is.

**Covariance** is needed as well, which can be described as a measure of how two sets of numbers change together. It tells you whether two variables tend to grow together (positive covariance) or whether one growing reduces the other (negative covariance). 


A covariance matrix is a matrix that describes the covariance between the combinations of the variables. For example, for a datased with x and y values, the covariance matrix would be:

$$
C = \begin{bmatrix} 
Cov(x,x) & Cov(x,y) \\
Cov(y,x) & Cov(y,y) \\
\end{bmatrix}
$$

The covariance of a variable with itself happens to be the variance, so the previous formula turns to be equal to:


$$
C = \begin{bmatrix} 
Var(x) & Cov(x,y) \\
Cov(y,x) & Var(y) \\
\end{bmatrix}
$$


### Principal component analysis (PCA)

PCA is a way to achieve dimensionality reduction while minimizing information loss. It works by combining the concepts of eigenvalues/eigenvectors, projections, and covariance matrices.

The idea is the following: When performing dimensionality reduction, reducing information loss is equal to preserving as much variance as possible. 

Choosing the space to which the information should be projected is then a matter of choosing the projection that preserves the most variance. This turns out to be the space spanned with the largest eigenvalues (of the covariance matrix).

This conection between eigenvectors and variance arises from the fact that eigenvectors point to the directions where the matrix transformation is just scaling - the largest eigenvector is therefore the direction in which data stretches the most, which implices more variance.

Given a table of data with $n$ columns, The process for PCA then becomes:

- calculate the $n*n$ covariance matrix
- find the eigenvalues and eigenvectors of that matrix
- sort those pairs by eigenvalues
- choose the top eigenvector/eigenvalue pairs (as many as the reduced dimension wanted)
- project the original matrix into the chosen vectors

Formulated mathematically:


- Start with the matrix 

$$
\mathbf{X} = \begin{pmatrix}
x_{11} & x_{12} & \cdots & x_{1n} \\
x_{21} & x_{22} & \cdots & x_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
x_{n1} & x_{n2} & \cdots & x_{nn}
\end{pmatrix}
$$

- Center the data around the mean

$$
\mathbf{X} - \boldsymbol{\mu} = \begin{pmatrix}
x_{11} - \mu_1 & x_{12} - \mu_2 & \cdots & x_{1n} - \mu_n \\
x_{21} - \mu_1 & x_{22} - \mu_2 & \cdots & x_{2n} - \mu_n \\
\vdots & \vdots & \ddots & \vdots \\
x_{n1} - \mu_1 & x_{n2} - \mu_2 & \cdots & x_{nn} - \mu_n
\end{pmatrix}
$$

- Calculate the covariance matrix

$$
\mathbf{C} = \frac{1}{n-1}(X-\mu)^T(X -\mu) =\begin{pmatrix}
\mathrm{Var}(X_1) & \mathrm{Cov}(X_1, X_2) & \cdots & \mathrm{Cov}(X_1, X_n) \\
\mathrm{Cov}(X_2, X_1) & \mathrm{Var}(X_2) & \cdots & \mathrm{Cov}(X_2, X_n) \\
\vdots & \vdots & \ddots & \vdots \\
\mathrm{Cov}(X_n, X_1) & \mathrm{Cov}(X_n, X_2) & \cdots & \mathrm{Var}(X_n)
\end{pmatrix}
$$

- Find the eigenvalue/eigenvector pairs and choose the largest ones

$$
\begin{array}{c|c}
\text{Eigenvalue} & \text{Eigenvector} \\
\hline
\lambda_1 & \mathbf{v}_1 = \begin{bmatrix} v_{11} \\ v_{12} \\ \vdots \\ v_{1n} \end{bmatrix} \\
\lambda_2 & \mathbf{v}_2 = \begin{bmatrix} v_{21} \\ v_{22} \\ \vdots \\ v_{2n} \end{bmatrix} \\
\vdots & \vdots \\
\lambda_n & \mathbf{v}_n = \begin{bmatrix} v_{n1} \\ v_{n2} \\ \vdots \\ v_{nn} \end{bmatrix}
\end{array}
$$

- Create the projection matrix with the chosen eigenvectors

$$
\mathbf{V} = \begin{bmatrix}
\frac{\mathbf{v}_1}{\|\mathbf{v}_1\|} & \frac{\mathbf{v}_2}{\|\mathbf{v}_2\|} & \cdots & \frac{\mathbf{v}_k}{\|\mathbf{v}_k\|}
\end{bmatrix}
$$

- Project centered data into the projection matrix:

$$
X_{PCA} = (X - \mu)V
$$

The resulting $X_{PCA}$ will have the reduced form of the original data with minimal information loss.