---
title: "Jekyll Github 블로그에 MathJax로 수학식 표시하기"
tags:
  - Blog
  - MathJax
  - Jekyll
  - LaTeX
use_math: true
classes: wide
---
# 행렬3

실수들의 사각형 배열을 행렬(matrix)이라고 하며 m개의 행(row) n개의 열(column)을 가진 $ m \times n$ 행렬은 다음과 같이 나타낸다


$$
A_{m,n} =
 \begin{pmatrix}
  a_{1,1} & a_{1,2} & \cdots & a_{1,n} \\
  a_{2,1} & a_{2,2} & \cdots & a_{2,n} \\
  \vdots  & \vdots  & \ddots & \vdots  \\
  a_{m,1} & a_{m,2} & \cdots & a_{m,n}
 \end{pmatrix}
$$


일반적으로 2차원 배열의 형태로 나타낸것을 행렬, 1차원 배열의 형태로 나타낸 것을 벡터(vector)라고 한다

행렬과 벡터의 각 원소를 스칼라(scalar)라고 한다



## 행렬의 연산

### 합

$$
예시) \qquad\begin{bmatrix}

2 & 3 & 6 \\

1 & 5 & 3 

\end{bmatrix} +
\begin{bmatrix}

1& 0 & 1 \\

1 & 2 & 0 
\end{bmatrix}=
\begin{bmatrix}

3& 3 & 7 \\

2 & 7 & 3 
\end{bmatrix}
$$



두 행렬의 크기가 다를시 합할수 없다



### 곱

$$
예시1) \qquad

2
\begin{bmatrix}
2 & 3 & 6 \\
1 & 5 & 3 
\end{bmatrix}
=
\begin{bmatrix}
4 & 6 & 12 \\
2 & 10 & 6 
\end{bmatrix}
 \qquad
 
예시2) \qquad
\begin{bmatrix}
2 & 4 & -1 \\
1 & 3 & 0 
\end{bmatrix}
\begin{bmatrix}
-1 & 0  \\
2 & 3  \\
1 &5
\end{bmatrix}
=
\begin{bmatrix}
5 & 7 \\
5 & 9  
\end{bmatrix}
$$



- 스칼라곱은  $$ m \times n $$ 행렬 $$ A = [a_{ij}]  $$ 와 상수 $$k$$를 곱한 것으로 $$ Ak = kA = [ka_{ij}]$$ 이다
- 행렬의 곱은 행렬 A의 열의 개수와 행렬 B의 행의 개수가 같을때만 정의 된다
- 두행렬의 곱 AB와 BA는 같지 않다
- A,B,C가 행렬이고 k가 상수일때 행렬은 다음과 같은 성질을 갖는다

1. $$(AB)C = A(BC)$$
2. $$A(B+C) = AB + AC$$
3. $$(B+C)A=BA+CA$$
4. $$k(AB)=(kA)B=A(kB)$$



예제1) 다음 선형방정식을 $$AX = B$$ 형태로 나타내어라


$$
문제) \qquad
\begin{align}
x_1+3x_2+x_3=1&\\
2x_1-x_2+x_3=4&\\
x_2-x_3=2&
\end{align}
\qquad
답) \qquad
\begin{bmatrix}
1&3&1\\
2&-1&1\\
0&1&-1
\end{bmatrix}
\begin{bmatrix}
x_1\\x_2\\x_3
\end{bmatrix}=
\begin{bmatrix}
1\\4\\2
\end{bmatrix}
$$

## 여러가지 행렬



### 영행렬

모든 스칼라 값이 0인 행렬을 '영행렬(zero matrix)' 이라고 한다


$$
O =
\begin{bmatrix}
0&0&\cdots&0\\
0&0&\cdots&0\\
\vdots&\vdots&\ddots&\vdots\\
0&0&\cdots&0
\end{bmatrix}
$$




### 정방행렬

- $$m \times n $$ 행렬 $$A=[a_{ij}]$$ 가 있을때 $$m=n$$ 인 행렬을 '정방행렬'(square matrix)이라고 하며 $$n\times n$$ 행렬로 나타낸다

- $$n$$개의 행과 $$n$$개의 열로 구성된 정방행렬을 '$$n$$차 정방행렬'이라고 하며 $$n$$ 의값을 행렬의'차수'(order)라고 한다

  또한 대각선상 원소를 '대각원소'(diagonal element)라고 하며, 대각원소 이외의 모든 원소가 0인 다음과 같은 행렬을 '대각행렬'(diagonal matrix)라고 한다

  
  $$
  A=
  \begin{bmatrix}
  a_{1,1}&0&0\\
  0&a_{2,2}&0\\
  0&0&a_{3,3}
  \end{bmatrix}\\
  $$



### 단위행렬

대각행렬이면서 대각원소가 모두1인 행렬을 '단위행렬'(unit matrix)이라고 하며 $$I$$ 로 나타낸다


$$
I=
\begin{bmatrix}
1&0&0&0\\
0&1&0&0\\
0&0&1&0\\
0&0&0&1
\end{bmatrix}\\
$$


위 $$I$$ 는 4차 단위행렬이다



이러한 단위행렬 $$I$$는 정방행렬$$A$$에 대해 다음과 같은 성질을 갖는다

$$IA=A=AI$$
$$
예시)\qquad
\begin{bmatrix}
1&3\\2&4
\end{bmatrix}
\begin{bmatrix}
1&0\\0&1
\end{bmatrix}=
\begin{bmatrix}
1&3\\2&4
\end{bmatrix}
$$

### 전치행렬

$$m\times n $$ 인 행렬 $$A$$ 의 행과 열을 바꾼 $$n\times m$$ 행렬을 '전치행렬'(transpose matrix)이라고 하며 $$A^T$$ 로 나타낸다

$$A^T=A$$인 행렬을 '대칭행렬'(synmetric matrix)이라고 한다


$$
\begin{align}
&예제) \qquad
A=
\begin{bmatrix}
7&6&3\\1&-2&5
\end{bmatrix} 일때 \quad A^T는? \\ \\
\quad &답)\quad
A^T=\begin{bmatrix}7&1\\6&-2\\3&5\end{bmatrix}\\
\end{align}
$$


전치행렬은 행렬$$A, B$$에 대해 다음과 같은 성질을 갖는다

- $$(A^T)^T=A$$

- $$(A+B)^T=A^T+B^T$$

- $$(kA)^T=kA^T$$

- $$(AB)^T+B^TA^T$$

  



  



  

