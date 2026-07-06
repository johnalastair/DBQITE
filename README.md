# Tutorial using an annotated jupyter notebook for `Double-bracket quantum algorithms for quantum imaginary-time evolution`

### View paper at

https://arxiv.org/abs/2412.04554

### Contact 
https://mathstodon.xyz/@Marekgluza/113621100092525571


DEFINITIONS

Vectors: 
- A column vector is denoted by a ket
- A row vector is denoted by a bra

Vector Spaces:

General Matrix Definitions:
- Transpose: Rows become columns, columns become rows.
- Complex conjugate: All imaginary components are replaced by their conjugates
- Dagger/Conjugate transpose: Transpose + replace with conjugates
- Hermitian Matrices: Matrices that are equal to their conjugate transposes
  - Hamiltonians are always Hermitian
- Determinants are denoted by det() and given by the equation:


$$
\det \begin{bmatrix}
a & b \\
c & d
\end{bmatrix} = \begin{vmatrix}
a & b \\
c & d
\end{vmatrix} = ad - bc
$$

Matrices with no inverses have a det of 0.

  
- Unitary Matrices: Inverse is equal to the dagger
- Inverse Matrices:

  
$$
A^{-1} = \frac{1}{ad-bc}
\begin{pmatrix}
d & -b \\
-c & a
\end{pmatrix}
$$

Bases:
The 'coordinate system' in which the matrix exists. It determines the physical manifestation of the matrix.
In 2D space, the base is x and y axis, or i and j directions
For qubits, the computational basis is used, connoting that (1,0) represents 'spin up' while (0,1) represents 'spin down'




Matrix multipication:

Matrix-Matrix:

$$
\begin{pmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{pmatrix}
\begin{pmatrix}
b_{11} & b_{12} \\
b_{21} & b_{22}
\end{pmatrix} = \begin{pmatrix}
a_{11}b_{11} + a_{12}b_{21} & a_{11}b_{12} + a_{12}b_{22} \\
a_{21}b_{11} + a_{22}b_{21} & a_{21}b_{12} + a_{22}b_{22}
\end{pmatrix}
$$

Matrix-Vector:

$$
\begin{pmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{pmatrix}
\begin{pmatrix}
x_1 \\
x_2
\end{pmatrix} = \begin{pmatrix}
a_{11}x_1 + a_{12}x_2 \\
a_{21}x_1 + a_{22}x_2
\end{pmatrix}
$$

Eigenvectors: An eigenvector of a matrix is a vector that does not change direction when multiplied by said matrix. It is only scaled by a factor lambda, the corresponding eigenvalue of that eigenvector. 


$A\mathbf{v} = \lambda\mathbf{v}$


Matrix exponentials:


Using the Maclaurin expansion of an exponential, the exponential of a diagonal matrix is simply:

For non-diagonal matrices, 







