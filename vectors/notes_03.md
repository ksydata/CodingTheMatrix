# 연립일차방정식

## 4.1. Homogeneous Systems (동차 연립방정식)

정의 : 각 방정식의 우변 상수항(constant term)이 모두 **0**인 연립방정식.

$$[A \mid \mathbf{0}]$$

핵심 성질

- 항상 적어도 하나의 해를 가진다 → trivial solution, 즉 좌변의 변수에 모두 0을 대입한다면, 해가 반드시 존재한다. (consistent)

- 그렇다면 언제 무한히 많은 해를 가질까? → non-trivial solution의 존재 조건을 알아본다. 
    > $m$개의 방정식, $n$개의 변수로 이루어진 동차 연립방정식 $[A \mid \mathbf{0}]$이 있다고 가정한다.
    
    > $m < n$이면(방정식 개수보다 변수 개수가 더 많으면), pivot이 없는 자유변수(free variable)가 최소 1개 이상 있기에 이 시스템은 무한히 많은 해를 가진다. 

$$\left(\begin{array}{ccc|c}
1 & 2 & -1 & 0\\
0 & 0 & 0 & 0\\
0 & 0 & 0 & 0\\
\end{array}\right)$$

$$\begin{align}
x_1 &= -2x_2 + x_3 \quad \text{(피봇 컬럼)} \\
x_2 &= x_2 \quad \text{(자유)} \\
x_3 &= x_3 \quad \text{(자유)} \
\end{align}$$

$$\mathbf{x} = \begin{bmatrix} -2x_2 \\ x_2 \\ 0 \end{bmatrix} + \begin{bmatrix} x_3 \\ 0 \\ x_3 \end{bmatrix} = x_2 \begin{bmatrix} -2 \\ 1 \\ 0 \end{bmatrix} + x_3 \begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix}$$

- 다만, 역(converse)은 성립하지 않는다. 즉, 해가 무수히 많다고 해서 반드시 방정식의 개수가 변수보다 더 많은 것은 아니다. 필요충분 조건은 불성립한다. 
- $m \geq n$인 경우는 해가 하나일 수도, 무한히 많을 수도 있다.

$$\begin{align}
x_1 + x_2 &= 0 \quad \\
2x_1 + 2x_2 &= 0 \quad
\end{align}$$


### 4.0. Linear Systems and Geometry (Plane‐plane, Line-line intersection) [PASS]
### 4.2. Linear Systems over Zp [PASS]
### 4.3. Numerical Errors (수치 해석) [PASS]


---


## 5. 선형방정식과 선형결합(Linear Systems and Linear Combinations)

핵심 성질 - Spanning Sets of Vectors 

> 첨가 계수행렬 $[A \mid \mathbf{b}]$로 표현되는 선형방정식이 해를 가지는지(consistent)에 대한 문제

> ↕ 

> 벡터 $\mathbf{b}$가 행렬 $A$의 열벡터들의 선형결합으로 표현되는지 여부

> 벡터들의 집합이 벡터공간 $V$를 span한다는(덮는다는) 것은, $\mathbf{b}$가 $A$의 **열(column)들의 선형결합**이 성립하여 해가 존재한다는 것이다. 

-  $\mathbb{R}^2$를 span하는 집합

$$v_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix}, v_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix},$$

$$\begin{bmatrix} x \\ y \end{bmatrix} = x \cdot \begin{bmatrix} 1 \\ 0 \end{bmatrix} + y \cdot \begin{bmatrix} 0 \\ 1 \end{bmatrix}$$

-  평면을 span하는 집합

$$v_1 = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, v_2 = \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix},$$

$$Span_{v_1, v_2} = {c_1 \cdot \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + c_2 \cdot \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} \mid c_1, c_2 in \mathbb{R}} = \begin{bmatrix} c_1 \\ c_2 \\ 0 \end{bmatrix}$$



---



## 6. Spanning Sets (생성 집합)

정의 : 어떤 공간의 모든 벡터를 만들 수 있는 벡터들의 집합 (향후 배울 기저(basis)와 연결되는 개념이다)


핵심 성질 1.

| 성질 | 설명 |
|------|------|
| $S \subseteq \text{span}(S)$ | $S$는 자신의 span에 포함된다 |
| zero vector($c_i = 0$) 포함 | 임의의 (non-empty) 벡터 집합의 span은 항상 영벡터를 포함한다 |
| 대부분 무한 | $\text{span}(S)$는 대부분 무한히 많은 벡터를 포함 |
| subspace와 연관 | span은 **부분공간(subspace)** 개념과 밀접하게 관련 |


핵심 성질 2. - Spanning Sets of Vectors (cont'd)

$Span_{x, y, z} = x \cdot \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + y \cdot \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} = \begin{bmatrix} x \\ y \\ 0 \end{bmatrix}$(z가 0이면, 선형결합 가능)

$Span_{x, y} = x \cdot \begin{bmatrix} 0 \\ 0 \end{bmatrix} + y \cdot \begin{bmatrix} 0 \\ 1 \end{bmatrix} = \begin{bmatrix} 0 \\ y \end{bmatrix}$ (선형결합 불가)

$Span_{x, y} = x \cdot \begin{bmatrix} 2 \\ -1 \end{bmatrix} + y \cdot \begin{bmatrix} 1 \\ 3 \end{bmatrix}$ (how to find the general equation of the plane? 예저 2.21)
$$​p_1 = ​2x + y p_2 = −x + 3y​​$$


---



## 7. Linear Independence (선형독립성과 선형독립 판별법)

정의 : 벡터 집합 ${v_1, \cdots, v_n}$에 대한 선형 결합 $c_1v_1 + \cdots + c_nv_n = 0$을 만족하는 $c_i$가 오직 $c_1 = \cdots = c_n = 0$으로 자명한 해뿐일 때, 이 벡터들은 선형독립이다. 즉, 어떤 벡터가 다른 벡터들의 선형 결합으로 표현이 가능하다면 선형독립이 성립하지 않는다. (linear dependence)