# Linear algebra

## Linear independence

Two vectors/equations are called linearly independent if they can not be expressed as linear combinations of each other.

Intuitively, independent vectors provide unique directions in space, so they can't be built from each other. Three vectors that are independent exist in 3D space, while three vectors where one is linearly dependent would fit on a plane.

## Types of systems and singularity

- Complete system: System where the number of independent equations matches the number of variables. It can be singular or non singular.
  - Singular system: A system in which the rows (or columns) are linearly dependent. In practical terms, this means that it does not have a unique solution. They can be either redundant or contradictory.
    - Redundant system: A system in which some of its equations do not provide new information. Some equations are linear combinations of others, trivial, etc.
    - Inconsistent system: A system in which some of the equations can not be simultaneously true. The equations contradict each other.
  - Non-singular system: A system in which there is one single solution. Its equations are linearly independent.
- Non-complete system: A system in which the number of equations does not match the number of variables. Either there are more equations than variables (overdetermined) or there are more variables than equations (underdetermined). Singularity, as a concept, does not apply to non-complete systems, because it only applies to square matrices.

Geometrically, Matrices represent transformations of space. Non-singular matrices represent transformations that preserve dimensionality (rotations, scaling, etc), while singular matrices represent collapsing space into a lower dimention (projecting 3D space into a 2D plane for example).

'Singular system' sounds counter intuitive as a name, given that sytems with a single (singular) solution are the non-singular ones. The reasoning behind this name is in the use of 'singular' as in 'exceptional': Singular matrices are an infinitesimally small subset of matrices, since they are the only ones to meet some specific criteria. This can be seen intuitively by considering the previous paragraph.

## Determinant

The determinant of a square matrix is a scalar value that gives important information about said matrix. Particularly, a determinant equal to zero lets us know that the matrix is singular.

Geometrically, the determinant quantifies how the matrix transforms space - its scaling factor. A determinant greater than one shows that the matrix stretches volumes, while a determinant lower than 1 compresses them. A negative determinant indicates flipping - a reversal of orientation.

A determinant of 0 then is geometrically interpreted as a transformation that maps higher dimensional objects into a lower-dimensional space, which fits with the concept of singularity.

## Rank and inverse of a matrix

[TBD]
