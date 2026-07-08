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
- Trace: Sum of diagonal components. Tr(AB)=Tr(BA)
- Hermitian Matrices: Matrices that are equal to their conjugate transposes
  - Hamiltonians are always Hermitian
- Determinants are denoted by det() and given by the equation:


$$
\det \begin{pmatrix}
a & b \\
c & d
\end{pmatrix} = \begin{vmatrix}
a & b \\
c & d
\end{vmatrix} = ad - bc
$$

  Matrices with no inverses have a det of 0.
  For a 3x3 matrix, each element in the top row is multiplied by the 2x2 matrix formed by the elements not in the same column. Then, the resulting number formed by the middle element is subtracted while the other 2 are summed. 
  If 2 rows of a matrix are swapped, the determinant is multiplied by -1
  If any row is multiplied by $\lambda$, the determinant is multiplied by $\lambda$
  

- Minor: The determinant of the matrix that is obtained by removing the column and row of a selected element
- Unitary Matrices: Inverse is equal to the dagger
- Orthogonal Matrices: Transpose is equal to the inverse
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

$$D^n = \begin{bmatrix} \lambda_1^n & 0 & 0 \\ 0 & \lambda_2^n & 0 \\ 0 & 0 & \lambda_3^n \end{bmatrix}$$

However, for non-diagonal matrices, $$A^n$$ is less simple to evaluate since the elements cannot simply be raised to the nth power. Hence, diagonalisation is used to isolate a diagonal matrix. 


QM notation:

Quantum superposition notation:
[INSERT EQUATION]

a and b are probability amplitudes, denoting the probability of each ket being the case. 

Quantum evolution as a function of time:
U is used to demonstrate how a state evolves over time. 










