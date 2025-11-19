---
title: Linear algebra
layout: layouts/base
courseNumber: MAT4111A
term: F25
type: problems
week: 13
---
# Linear algebra
See <a href="https://www.math.utoronto.ca/barbeau/putnamla.pdf">Putnam problems: matrices, determinants and linear algebra</a>

### Determinants by cofactor expansion
<p>
  Let $A$ be an $n \times n$ matrix and let $A_{ij}$ be the matrix <i>minor</i> that results from deleting the $i$th row and $j$th column. Then if $r$ is a row index, the determinant of $A$ is given by \[
  \det(A) = \sum_{j = 1}^n (-1)^{r + j} \det(A_{rj}),
\] and if $c$ is a column index then \[
  \det(A) = \sum_{i = 1}^n (-1)^{i + c} \det(A_{ic}).
\]
</p>

### Determinants are multiplicative
<p>
  Let $A$ and $B$ be an $n \times n$ matrices, then \[
  \det(AB) = \det(A)\det(B).
\]
</p>

#### Problem 0
<p>
  Let $I_n$ be the $n \times n$ identity matrix, \[
    I_n = \begin{bmatrix}
      1 & 0 & 0 & \dots & 0\\
      0 & 1 & 0 & \dots & 0\\
      0 & 0 & 1 & \dots & 0\\
      \vdots & \vdots & \vdots & \ddots & \vdots\\
      0 & 0 & 0 & \dots & 1\\
    \end{bmatrix}
  \] and let $A^{(ij)}$ be an $n \times n$ matrix that has a $1$ in the $i$th row and $j$th column, and zeroes elsewhere.
</p><p>
  Compute $\det(I_n + rA^{(ij)})$ for all integers $n$, real numbers $r$ and indices $i, j \in \{1, 2, \dots n\}$, and explain what $B(I_n + rA^{(ij)})$ and $(I_n + rA^{(ij)})B$ do in terms of row/column operations on $B$.
</p>

#### Problem 1
{% include 'content/F25/MAT4111A/problems/contest-problems/putnam/2014_A2.html' %}

#### Problem 2
{% include 'content/F25/MAT4111A/problems/contest-problems/putnam/2018_B1.html' %}
