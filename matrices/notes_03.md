## 행렬(matrices): 벡터를 한 차원 더 끌어올린 객체, 숫자들의 직사각형 배열

### 0. 선형대수의 응용 : edge & node [AS-IS]

### 4. 부분 공간과 생성 집합(Subspace Spanning sets)

좋은 벡터들을 가지고 있어야(벡터들 간 선형독립이어야) 더 넓은 영역을 span할 수 있다.

정의 : $\mathbf{R^n}$의 부분공간은 다음을 만족하는 $\mathbf{R^n}$ 안 벡터의 모임 $\mathbf{S}$이다. 
> 1. zero vector ${0}$은 $\mathbf{S}$에 속한다.

> 2. $u$, $v$가 $\mathbf{S}$에 속하면 $u+v$도 $\mathbf{S}$에 속한다. [덧셈에 닫힘]

> 3. $u$가 $\mathbf{S}$에 속하고 $c$가 스칼라이면, $cu$도 $\mathbf{S}$에 속한다. 즉, $\mathbf{S}$는 스칼라에 대해 닫혀 있다. 즉, 2,3.에 따라 $\mathbf{S}$는 일차선형결합(linear combination)에 관하여 닫혀있음을 알 수 있다. 

> 만약 $u_1, u_2, \cdots, u_k$가 $\mathbf{S}$에 속하고 $c_1, c_2, \cdots, c_k$가 스칼라이면 $c_1 u_1, c_2 u_2, \cdots, c_k u_k$도 $\mathbf{S}$에 속한다.


> 예제 3.38 : $x​ = 3y​, z = −2y$를 만족하는 모든 벡터의 집합 $\begin{pmatrix} x \\ y \\ z \\ \end{pmatrix}$이 $\mathbf{R^3}$의 부분 공간임을 보여라.
> $\left(\begin{matrix} 3y \\ y \\ -2y \\ \end{matrix}\right) = \left(\begin{matrix} 3 \\ 1 \\ -2 \\ \end{matrix}\right) \cdot y$
> y는 임의의 벡터로 주어진 벡터 집합은 span $\left(\begin{matrix} 3 \\ 1 \\ -2 \\ \end{matrix}\right)$을 갖는 3차원 실수 부분공간의 원점을 지나는 직선을 의미한다. 


> 예제 3.39 : $x​ = 3y​+1, z = −2y$를 만족하는 모든 벡터의 집합 $\begin{pmatrix} x \\ y \\ z \\ \end{pmatrix}$이 $\mathbf{R^3}$의 부분 공간임을 보여라.
> $\left(\begin{matrix} 3y+1 \\ y \\ -2y \\ \end{matrix}\right)$
> 영벡터는 이러한 형태가 아니며(x때문에 0이 될 수 없음), 부분공간의 성질 중 1번째 조건이 성립하지 않으므로 3차원 실수 부분공간이 될 수 없다. 


> 예제 3.40 : $y = x^2$를 만족하는 모든 벡터의 집합 $\begin{pmatrix} x \\ y \\ \end{pmatrix}$이 $\mathbf{R^2}$의 부분 공간임을 보여라.
> $\left(\begin{matrix} x \\ x^2 \\ \end{matrix}\right)$ 형태의 벡터로 이루어진 집합 $\mathbf{S}$에 zero vector $\left(\begin{matrix} 0 \\ 0 \\ \end{matrix}\right)$에 속한다. (1번째 조건 성립)
> 다만, $u = \left(\begin{matrix} x_1 \\ {x_1}^2 \\ \end{matrix}\right)$, $v = \left(\begin{matrix} x_2 \\ {x_2}^2 \\ \end{matrix}\right)$가 S의 임의의 원소라고 할 때,  
> $u + v = \begin{pmatrix} x_1 + x_2 \\ x_1^2 + x_2^2 \end{pmatrix}$, $u + v$가 $S$에 속하려면 $x_1^2 + x_2^2 = (x_1 + x_2)^2$이어야 하는데, 이는 $2x_1 x_2 = 0$일 때만 성립한다. 일반적으로는 2번째 조건은 성립하지 않는다. (2번째 성분이 1번째 성분의 제곱이 성립하지 않는다.)
> > **반례** : $u = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$, $v = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$이면 $u + v = \begin{pmatrix} 2 \\ 2 \end{pmatrix}$인데, $2 \neq 2^2 = 4$이므로 $u + v \notin S$.


---


### 5.1. 행렬 관련 부분공간(Row space, Column space)

행렬의 영공간이 부분 공간이라는 사실은, 예제들에서 보았던 연립일차방정식의 해에 관해 이해해야 할 것들을 증명하도록 한다. 이들은 해가 존재하지 않거나, 유일한 해를 갖거나, 무수히 많은 해를 갖는다. 

행공간 row(A)과 열공간 col(A)의 차원을 행렬 $A$의 계수(rank)라고 하고 rank(A)로 표기한다. 참고로 $A_1 = \left(\begin{matrix} 1 & 1 \\ 1 & 1 \\ \end{matrix}\right)$, $A_2 = \left(\begin{matrix} 1 & 1 \\ 0 & 0 \\ \end{matrix}\right)$의 $col(A_n)$은 달라진다. 

> 샘플(수업) : 
> 1. $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$ [X]
> 2. $\begin{pmatrix} 1 \\ 0 \end{pmatrix} \ \begin{pmatrix} 0 \\ 1 \end{pmatrix}$ [O]
> 3. $\begin{pmatrix} 1 \\ 0 \end{pmatrix} \ \begin{pmatrix} 0 \\ 1 \end{pmatrix} \ \begin{pmatrix} 1 \\ 1 \end{pmatrix}$ [X]
> 4. $x_1\begin{pmatrix} 1 & -1 \end{pmatrix} + x_2\begin{pmatrix} 0 & 1 \end{pmatrix} + x_3\begin{pmatrix} 3 & -3 \end{pmatrix} = \begin{pmatrix} 4 & 5 \end{pmatrix}$
> $\begin{pmatrix} x_1 & x_2 & x_3 \end{pmatrix} \begin{pmatrix} 1 & -1 \\ 0 & 1 \\ 3 & -3 \end{pmatrix} = \begin{pmatrix} 4 & 5 \end{pmatrix} \\$
> $x^T \cdot A = w \implies (x^T \cdot A)^T = w^T \implies A^T x = w^T \\$
> $\begin{pmatrix} 1 & 0 & 3 \\ -1 & 1 & -3 \end{pmatrix} x = \begin{pmatrix} 4 \\ 5 \end{pmatrix} \\$
> 즉, 4.에서 해가 무수히 많은 건 $x_1, x_2, x_3$​의 조합이 여러 개인 걸로 증명되며, w (4,5)가 row(A)의 원소로 판정된다. 


---


### 5.2. 영공간(Null space)

null(A) 영공간(행공간과 수직)은 $Ax = 0$인(즉, colums의 linear combination이 0이 되도록 하는 그 계수) x들의 해집합을 말한다. 

> 샘플 :
> 1. $A = \begin{pmatrix} 1 & 0 & 1 \\ 0 & 1 & 1 \end{pmatrix} (rank = 2, null space의 dimension = 1) \\$
> $Ax = \begin{pmatrix} 1 \\ 0 \end{pmatrix}x_1 + \begin{pmatrix} 0 \\ 1 \end{pmatrix}x_2 + \begin{pmatrix} 1 \\ 1 \end{pmatrix}x_3 = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \\$
> $x = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$, $\begin{pmatrix} 1 \\ 1 \\ -1 \end{pmatrix}$, $\begin{pmatrix} 2 \\ 2 \\ -2 \end{pmatrix}$ \
> $c \cdot Ax = 0 \cdot c, x_n = c \cdot \begin{pmatrix} 1 \\ 1 \\ -1 \end{pmatrix}$
> 2. $A = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & 0 \end{pmatrix} (rank = 1, null space의 dimension = 2) \\$
> $A(c_1 x_1) = 0, A(c_2 x_2) = 0, A(c_1 x_1 + c_2 x_2) = 0 \\$
> 즉, 3차원 공간 안에서 선형결합 벡터 $c_1 x_1 + c_2 x_2$는 평면을 span한다.

* $A$가 $m \times n$일 때, $dim(N(A)) = n - r$이다.
* null space는 row space와 수직한 space다. 
* left null space란 $x^T A = 0^T$, $dim(N_L(A)) = m - r$이다. (r은 곧, col(A)의 dim)


---


### 6.1. 기저(Finding a Basis for row(A) or col(A)) + Fundamental Theorem of invertible matrices

기저란 주어진 벡터 공간/부분공간 $S$에서 그 공간을 span하는 선형독립인 벡터들을 말한다. 
즉, 어떤 공간을 이루는 기반이 되는 필수적인 구성 요소다.

> 계수 정리(Rank Theorem) : rank(A) + nullity(A) = n(nullity(A) = 0, n(leading variable)), 
> "The rank of matrix A is the dimension of its row and column spaces and is denoted by rank(A)"

> 차원 정리(Basic Theorem) : dim( row(A) ) = dim( col(A) ) = rank(A), rank(A^T) = rank(A), 
> "The n by n matrix A^TA is invertible iff rank(A) = n

> **예제 3.45. ~ 3.47. ~ 3.48.** $A = \begin{pmatrix} 1 & 1 & 3 & 1 & 6 \\ 2 & -1 & 0 & 1 & -1 \\ -3 & 2 & 1 & -2 & 1 \\ 4 & 1 & 6 & 1 & 3 \end{pmatrix}$
> 1. A의 RREF(가우스-조르단 소거법) $R = \begin{pmatrix} 1 & 0 & 1 & 0 & -1 \\ 0 & 1 & 2 & 0 & 3 \\ 0 & 0 & 0 & 1 & 4 \\ 0 & 0 & 0 & 0 & 0 \end{pmatrix}$ (피벗 열(위치) : 열 1,2,4 / 자유변수 : 열 3,5)

> 2. rank(A) = 3, nullity(A) = 2, 3 + 2 = 5(n)

> 3. row(A)의 기저 : dim( row(A) ) = 3 ( = row(A) )
> $Basis_{row} = \begin{pmatrix} \begin{pmatrix} 1 \\ 0 \\ 1 \\ 0 \\ -1 \end{pmatrix}, \begin{pmatrix} 0 \\ 1 \\ 2 \\ 0 \\ 3 \end{pmatrix}, \begin{pmatrix} 0 \\ 0 \\ 0 \\ 1 \\ 4 \end{pmatrix} \end{pmatrix}$

> 4. col(A)의 기저 : A의 pivot column(leading entry)
> $Basis_{col} = \begin{pmatrix} \begin{pmatrix} 1 \\ 2 \\ -3 \\ 4 \end{pmatrix}, \begin{pmatrix} 1 \\ -1 \\ 2 \\ 1 \end{pmatrix}, \begin{pmatrix} 1 \\ 1 \\ -2 \\ 1 \end{pmatrix} \end{pmatrix}$

> 5. null(A)의 기저 : dim( null(A) ) = 2 = nullity(A)
> $Rx = 0$에서 선행변수 ${x_1, x_2, x_4}$를 자유변수 ${x_3, x_5}$로 표현, 
> $x = s \cdot u + t \cdot v (x_3 = s, x_5= t)$
> [AS-IS]
> 
> 
> $Basis_{null} = \begin{pmatrix} \begin{pmatrix} -1 \\ -2 \\ 1 \\ 0 \\ 0 \end{pmatrix}, \begin{pmatrix} 1 \\ -3 \\ 0 \\ -4 \\ 1 \end{pmatrix}$


> **예제 3.52.** $\begin{pmatrix} \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}, \begin{pmatrix} -1 \\ 0 \\ 1 \end{pmatrix}, \begin{pmatrix} 4 \\ 9 \\ 7 \end{pmatrix} \end{pmatrix}$
> [AS-IS]



### 6.2. 행공간의 기저(Baisis for row space(A))

row(A)는 행렬 A의 행들이 생성하는 $mathbf{R}^n$의 부분공간이다.

> row(A)의 기저 수 : rank(A)
> A의 RRF(reduced row echelon form, 기약행사다리꼴)인 R의 영 아닌 행벡터들,


### 6.3. 영공간(Baisis for Null space)

영공간 null(A)는 $Ax = 0$의 해집합 $in mathbf{R}^n$으로 행공간과 수직(orthogonal)이며, 좌영공간 $null(A^T)은 $ATx = 0$의 해집합 $in mathbf{R}^m$으로 열공간과 수직이다. 

> null(A)의 기저 수 : nullity(A)
> $mathbf{R}x = 0$에서 자유변수를 매개변수로 하는 → f개 벡터


### 6.4. 열공간의 기저(Baisis for column space(A))

col(A)는 행렬 A의 열들이 생성하는 $mathbf{R}^m$의 부분공간으로 $Ax = b$가 해를 가질 조건에 해당한다. 

> col(A)의 기저 수 : col(A) ≠ col(R) (행변환은 열공간을 바꾼다.)
> A의 RRF인 R의 피벗열에 대응하는 원본 행렬 A의 열벡터 (≠ 행렬 R의 열벡터)


---


* 출처 : https://m.blog.naver.com/csmathlab/223307665196?recommendTrackingCode=2
