
knowledge base
machine learning
naive bayes
logistic regression
representaion
feature
representation learning
autoencoder
factors of variation
multilayer percenptron
  visible layer
  hidden layer
neural networks
  ANN
  RNN
  CNN
activation functions
distributied representation



Scalar
Vector- 1D
Matrix- 2D
Tensor- More than 2 dimensions

Transpose of $A: A^T = A_ji$
Property of transpose: $(AB)^T = B^TA^T$

Matrix addition: $C = A + B$

Matrix and scalar operations: $D = aB + c$, D_ij = aBij + c$

Matrix and vector addiotion (broadcasting): $C = A + b, C_ij = A_ij + Bj$

Matrix production: $C = AB$ where $A_mxn, B_nxp and C_mxp$

Matrxi element wise product (Hadamard product): $C = AoB, C_ij = A_ij * B_ij$

Vector dot product: $z = x^Ty$

Matrix multiplication and addition properties:
Distributive: $A(B + C) = AB + AC$
Associative: $A(BC) = (AB)C$
Not commutative: $ AB \neq BA$

Vector dot product in commutative: $X^Ty = y^Tx$
$(x^Ty)^T = y^Tx$
a vector
System of linear equations:
$Ax = b, where A \in \mathbb{R}^{mxn}, x \in \mathhbb{R}^n and b \in \mathhbb{R}^m$
can be written as, $A_1x = b_1, A_2x = b_2, ... A_mx = b_m$ where $A_i$ is a row of $A$
can also be written as linear combination of columns of A, $A_1x_1 + A_2x_2 + ... + A_nx_n$ where $A_i$ is a column of $A$


Identity matrix: Matrix that does not change any vector when applied on vector, that is
$I_n \in \mathhbb{R}^{nxn} \forall x \in  \mathhbb{R}^n, I_nx = x$

Matrix inverse $A^{-1}$
\[
A^{-1}A = I_n
Ax = b
A^{-1}Ax = A^{-1}b
I_nx = A^{-1}b
x = A^{-1}b
\]
$A^{-1}$ is not always possible. If it exist, we can find it using various mathematical algorithms.
But it is useful in theories only and not used in software applications because computer cannot represent precision of numbers accurately.

$A^{-1}$ if $Ax=b$ has exactly one solution for any $b$.
System can have no or infinitely many solutions of some values of $b$.
But system cannot have more than one and less than infinitely many solutions, becasue
if $x$ and $y$ and two different solutions then any linear combination of them is also a solution.
$z = \alpha x + (1 - \alpha)y$ for any real number $\alpha$ in $(0, 1)$ inclusive


Interpretaion of $Ax = b$
Columns of $A$ are different directions in the space we can travel from origin.
$x_i$ specifies how long should we travel in the direction of column $A_i$.
Then solution is how many different ways are there to reach point $b$ in the space from origin.
$Ax$ is a linear combination: $Ax = \sum_i A_ix_i$

Span of set of vectors:
If set of vectors is $\{ v^1, v^2, ..., v^r\}$ then 
linear span of this set is all points obtained by linear combination of these vectors $\sum_i v^ic_i$ for $c in \mathhbb{R}$

Span of columns of $A$ is called column space or range of $A$
Hence, $Ax = b$ has a solution if $b$ is in column space of $A$.





