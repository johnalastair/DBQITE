# Tutorial using an annotated jupyter notebook for `Double-bracket quantum algorithms for quantum imaginary-time evolution`

### View paper at

https://arxiv.org/abs/2412.04554

### Contact 
https://mathstodon.xyz/@Marekgluza/113621100092525571



## Vectors: 
- A column vector is denoted by a ket
- A row vector is denoted by a bra

## General Matrix Definitions:
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




## Matrix multipication:

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

where v is the eigenvector, A is the matrix and $$\lambda$$ is the eigenvalue

## Matrix exponentials:


Using the Maclaurin expansion of an exponential, the exponential of a diagonal matrix is simply:

$$e^A = \sum_{n=0}^{\infty} \frac{A^n}{n!} = I + A + \frac{A^2}{2!} + \frac{A^3}{3!} + \dots$$

$$A^n = \begin{pmatrix}
\lambda_1^n & 0 & 0 & \dots & 0 \\
0 & \lambda_2^n & 0 & \dots & 0 \\
0 & 0 & \lambda_3^n & \dots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \dots & \lambda_k^n
\end{pmatrix}$$



However, for non-diagonal matrices, $$A^n$$ is less simple to evaluate since the elements cannot simply be raised to the nth power. Hence, diagonalisation is used to isolate a diagonal matrix. 

$$A = PDP^{-1}$$

$$A^2 = (PDP^{-1})(PDP^{-1})$$

$$= PD^2P^{-1}$$

Similarly, 

$$A^3 = PD^3P^{-1}$$

Hence, the general formula $A^n = PD^nP^{-1}$ and $e^A = Pe^DP^{-1}$ can be derived.

Here, P contains the eigenvectors while D contains the eigenvalues. 

Assuming A is a 2x2 matrix with 2 sets of eigenvalues and eigenvectors:

$$A\vec{v}_1 = \lambda_1\vec{v}_1$$
$$A\vec{v}_2 = \lambda_2\vec{v}_2$$

where $$\vec{v}_1$$ and $$\vec{v}_2$$ are the 2 eigenvectors and $$\lambda_1$$ and $$\lambda_2$$ are the 2 eigenvalues. 

$$P = \begin{pmatrix} \vec{v}_1 & \vec{v}_2 \end{pmatrix}$$
$$AP = A \begin{pmatrix} \vec{v}_1 & \vec{v}_2 \end{pmatrix} = \begin{pmatrix} A\vec{v}_1 & A\vec{v}_2 \end{pmatrix}$$
$$AP = \begin{pmatrix} \lambda_1\vec{v}_1 & \lambda_2\vec{v}_2 \end{pmatrix}$$
$$
(\lambda_1\vec{v}_1 \quad \lambda_2\vec{v}_2) = (\vec{v}_1 \quad \vec{v}_2) 
\begin{pmatrix}
\lambda_1 & 0 \\
0 & \lambda_2
\end{pmatrix} = PD
$$

Here, it can be seen that the isolated diagonal matrix D contains the 2 eigenvalues. 

To find it, we rewrite the eigenvector equation to get:

$$(A - \lambda I)\vec{v} = \vec{0}$$

Since the LHS must be irreversible to find eigenvectors (didn't fully understand gemini's explanations for why), we set the determinant to 0:

$$\det(A - \lambda I) = 0$$

From here, we solve for the eigenvalues $$\lambda$$. A 2x2 matrix would have 2 possible values for $$\lambda$$, giving the diagonal matrix D. 

Then, for each eigenvalue we solve the equation $$(A - \lambda I)\vec{v} = 0$$ to get the eigenvectors that make up P.


With D and P solved, the exponential $$e^A = P e^D P^{-1}$$ can be solved as $$e^D$$ can now be easily expressed as a taylor series.


## Matrix Transformations

Active vs Passive transformations:

Active involves the object moving to a different space
- Eg Applying a matrix to a vector to attain a different vector is a active transformation 

Passive involves the coordinate system moving/changing while the object remains unchanged
- Eg ct' and x' axes in spacetime diagrams
- Mathematically, the basis vectors and transformed by a transformation matrix P and the components of the position vector representing an object are tranformed by the $P^-1$, the inverse matrix of P.
- 




## QM notes (from the Euler slides):

Quantum superposition notation:
$$|v\rangle = a|0\rangle + b|1\rangle$$

where a and b are probability amplitudes, denoting the probability of each ket being the case. 

Quantum evolution as a function of time:

$$U = e^{itY} = \sum_{n=0}^{\infty} \frac{1}{n!} (it)^n Y^n$$

U is used to demonstrate how a state evolves over time. 

Using the matrix $Y^2 = I$, the expression for the evolution of a bit of initial state 0 simplifies to 
$$e^{itY} |0\rangle = \cos(t) |0\rangle + \sin(t) |1\rangle$$

The 2 coefficients will be equal at  $$t=\pi/4$$, indicating a state of superposition where the probability of each state is equal.












