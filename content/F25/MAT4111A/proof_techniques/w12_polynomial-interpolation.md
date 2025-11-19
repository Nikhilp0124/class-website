---
title: Polynomial interpolation
layout: layouts/base
courseNumber: MAT4111A
term: F25
type: problems
week: 12
---
# Polynomial interpolation

## Faulhaber's formula
<p>The function \(\displaystyle f(n) = \sum_{k=1}^n k^d\) is a degree-${(d+1)}$ polynomial.</p>

#### Problem 1
<p>Prove that if $p(k)$ is any degree-$d$ polynomial, then \(\displaystyle g(n) = \sum_{k=1}^n p(k)\) is a degree-${(d+1)}$ polynomial.</p>

## Lagrange interpolation
<p>Given $(x_1, y_1), \dots, (x_n,y_n) \in \mathbb{R}^2$ where $x_i \neq x_j$ for $i \neq j$, there exists a unique polynomial $p(x)$ with degree less than $n$ such that $p(x_i) = y_i$ for $1 \leq i \leq n$.<p>

#### Problem 2
<ol>
  <li>
    We'll construct such a polynomial given the points $(1, 9)$, $(2,6)$, $(3,-3)$:
    <ol>
      <li>Find a polynomial $p_1(x)$ such that $p_1(1) = 9$ and $p(2) = p(3) = 0$.</li>
      <li>Find a polynomial $p_2(x)$ such that $p_2(2) = 6$ and $p(1) = p(3) = 0$.</li>
      <li>Find a polynomial $p_3(x)$ such that $p_3(3) = -3$ and $p(1) = p(2) = 0$.</li>
    </ol>
  </li>
</ol>
<ol>

#### Problem 3
{% include 'content/F25/MAT4111A/problems/contest-problems/usamo/1975_3.html' %}
<details>
  <summary>Proof sketch</summary>
  <p>
    We use Lagrange interpolation and note that \[
      P(n+1) = \sum_{k=0}^{n} \frac{k}{k+1}\prod_{\substack{0 \le j \le n \\ j \neq k}}^k \frac{n+1-j}{k-j}.
    \] We can rewrite this product as
    \[\begin{align*}
      &\prod_{\substack{0 \le j \le n \\ j \neq k}}^k \frac{n+1-j}{k-j}
      =
      \frac{(n+1)\cdots(n+2-k)(n-k)\cdots(1)}{(k)(k-1)\cdots(1)\cdot(-1)(-2)\cdots(-(n-k))} \\
      &\qquad= \frac{\displaystyle\left(\frac{(n+1)!}{n+1-k}\right)}{k!(-1)^{n-k}(n-k)!} \\
      &\qquad= (-1)^{n-k}\frac{(n+1)!}{(n+1-k)!k!} \\
      &\qquad= (-1)^{n-k}\binom{n+1}{k} \\
    \end{align*}\]
    Now, in our sum, we rewrite $\frac{k}{k+1} = \frac{k+1}{k+1}-\frac{1}{k+1} = 1-\frac{1}{k+1}$, and so \[
      P(n+1) = \sum_{k=0}^{n} (-1)^{n-k}\binom{n+1}{k} - \sum_{k=0}^{n} \frac{(-1)^{n-k}}{k+1}\binom{n+1}{k}
    \]
    Now we observe that each of these sums are both <i>almost</i> the binomial expansion of $(1+x)^{n+1}$ where $x = -1$. We start with the first sum, noting that we use the fact that $(-1)^{n-k} = (-1)^{n+k}$:
    \[
      \sum_{k=0}^{n} (-1)^{n-k}\binom{n+1}{k} = (-1)^n\left(\underbrace{\sum_{k=0}^{n+1} (-1)^{k} \binom{n+1}{k}}_{=0} - (-1)^{n+1}\binom{n+1}{n+1}\right) = 1.
    \]
  </p>
  <p>
    For the second sum, we start by re-writing
    \[
      \frac{1}{k+1}\binom{n+1}{k} = \frac{(n+1)!}{(n+1-k)!(k+1)!} = \frac{1}{n+2}\frac{(n+2)!}{(n+1-k)!(k+1)!} = \frac{1}{n+2}\binom{n+2}{k+1}.
    \] and therefore \[\begin{align}
      &- \sum_{k=0}^{n} \frac{(-1)^{n-k}}{k+1}\binom{n+1}{k} =
      \frac{(-1)^n}{n+2}\sum_{k=0}^{n} (-1)^k\binom{n+2}{k+1}
      \\
      &=
      \frac{(-1)^n}{n+2}\Bigg(\underbrace{\sum_{k=-1}^{n+1} (-1)^k\binom{n+2}{k+1}}_{=0} + \binom{n+2}{0} - (-1)^{n+1}\binom{n+2}{n+2} \Bigg)
      \\
      &= \frac{(-1)^n}{n+2} (1 + (-1)^n)
    \end{align}\]
  </p>
  <p>
    So now putting the two sums together yields \[
      p(n+1) = 1 + \frac{1 + (-1)^n}{n+2}.
    \]
  </p>
</details>

## Problem 4 (Newton interpolation)
Suppose that you have $(x_1, y_1), \dots, (x_n,y_n) \in \mathbb{R}^2$, and you have a polynomial $p_{n-1}$ that interpolates $(x_1, y_1), \dots (x_{n-1}, y_{n-1})$. Can you describe a polynomial $p_n$ in terms of $p_{n-1}$ that interpolates all $n$ points?


## System of equations
Another way that we can find an interpolating polynomial is by solving a system of equations.

Suppose $p(1) = 9$, $p(2) = 6$ and $p(3) = -3$, and write a system of equations to solve for $a_2$, $a_1$, and $a_0$ in the polynomial $p(x) = a_2x^2 + a_1x + a_0$.
