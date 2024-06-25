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
A = \begin{pmatrix}
2 & 3 \\
1 & -1
\end{pmatrix}
$$

The **variable vector** x contains the variables of the system:

$$
\mathbf{x} = \begin{pmatrix}
x \\
y
\end{pmatrix}
$$

And the **constants vector** b contains the constants from the right-hand side of the equations:
% Constants Vector

$$
\mathbf{b} = \begin{pmatrix}
5 \\
1
\end{pmatrix}
$$

The full matrix equation would then be:

$$
A\mathbf{x} = \mathbf{b}
$$

or, expanded:

$$
\begin{pmatrix}
2 & 3 \\
1 & -1
\end{pmatrix}
\begin{pmatrix}
x \\
y
\end{pmatrix}
= \begin{pmatrix}
5 \\
1
\end{pmatrix}
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

## Rank

The rank of a matrix is its maximum number of linearly independent rows or columns. The number of independent rows is always equal to the number of independent columns. Intuitively, it represents the number of dimensions in which the matrix can spread out vectors - how many directions in space the matrix's transformation affects.

The determinant can help understand the rank of a matrix. When the determinant is non-zero, and therefore the matrix is non-singular, the rank is equal to the matrix size - all its rows/columns are linearly independent. A determinant equal to zero implies the rank is less than the size of the matrix (we don't know exactly what size). The rank can then be calculated by methods such as Gausian elimination.

## Identitity

An identity matrix $𝐼_𝑛$ is a square matrix with ones on the diagonal and zeros elsewhere. For example, the identity matrix of size 3 is:

$$
I_3 = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
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

- the $L2$ norm, or euclidean distance, is the square root of all suared components of the vector.

### Operations

- sum/difference of vectros are simply the sum/difference of its components (only defined for vectors of equal size).

- multiplication of vectors by a scalar also work by multiplying by coordinate

- the traspose of a vector (or matrix) turns rows into columns.

### Dot product

- the dot product is the sum of all coordinates' products (the l2-norm is the square root of the vector with itself).

- it is related to the angle between the vectors: ortogonal vectors have dot product equal to 0.

### Matrix multiplication by a vector

We can think of matrix multiplication by a vector as a dot product of each of the rows by the vector, returning a column vector with the result of each dot product. The number of columns in the matrix must therefore equal the length of the vector.

#### Linear transformations

A linear transformation is a rule that takes each vector in one space and transforms it to a vector in another space. Linear transformations can be represented by matrices.

We can represent a transformation as a matrix by applying the transformation to the standard basis vectors. The standard basis vectors are those that have one component equal to 1 and all other components equal to 0 - They are trivially linearly independent, and they span the space.

Linear transformations can be visually represented as scaling, shearing, rotation, etc. of the original vector space.

#### Matrix multiplication

matrices can be multiplied, and its result can be thought of as a composition of the linear transformations they represent.

Conditions for multiplication are that the number of columns of the first matrix must match the number of rows of the second, and the resulting matrix has as many rows as the first matrix and as many columns as the second.

The calculation itself can be thought of as a combination of dot products for the rows and colums of the matrices.
