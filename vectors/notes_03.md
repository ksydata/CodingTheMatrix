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

$\begin{align}
x_1 &= -2x_2 + x_3 \quad \text{(피봇 컬럼)} \\
x_2 &= x_2 \quad \text{(자유)} \\
x_3 &= x_3 \quad \text{(자유)} \
\end{align}$

$\mathbf{x} = \begin{bmatrix} -2x_2 \\ x_2 \\ 0 \end{bmatrix} + \begin{bmatrix} x_3 \\ 0 \\ x_3 \end{bmatrix} = x_2 \begin{bmatrix} -2 \\ 1 \\ 0 \end{bmatrix} + x_3 \begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix}$

- 다만, 역(converse)은 성립하지 않는다. 즉, 해가 무수히 많다고 해서 반드시 방정식의 개수가 변수보다 더 많은 것은 아니다. 필요충분 조건은 불성립한다. 
- $m \geq n$인 경우는 해가 하나일 수도, 무한히 많을 수도 있다.

$\begin{align}
x_1 + x_2 &= 0 \quad \\
2x_1 + 2x_2 &= 0 \quad
\end{align}$


## 4.0. Linear Systems and Geometry (Plane‐plane, Line-line intersection) [PASS]
## 4.2. Linear Systems over Zp [PASS]
## 4.3. Numerical Errors (수치 해석) [PASS]


---


## 5. 선형방정식과 선형결합(Linear Systems and Linear Combinations)



---



## 6. Spanning Sets (생성 집합)



---



## 7. Linear Independence (선형독립성)


