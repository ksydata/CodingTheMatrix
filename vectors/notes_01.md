## 내적 (Dot Product, 스칼라곱)

두 벡터 사이의 관계(유사성, 매핑의 척도)를 **하나의 스칼라**로 나타낸다.
즉, 두 벡터가 얼마나 같은 방향을 보고 있는 정도(코사인 각도)를 숫자 하나(실수, R)로 표현한 것이다. v가 w 방향으로 얼마나 향하는지

### 대수적 정의
$$\mathbf{v} \cdot \mathbf{w} = \sum_{i=1}^{n} v_i w_i$$

**예시**
$$\begin{bmatrix}1\\2\\3\\4\end{bmatrix} \cdot \begin{bmatrix}5\\6\\7\\8\end{bmatrix} = 1\times5 + 2\times6 + 3\times7 + 4\times8 = 70$$

### 기하학적 정의
두 벡터 사이의 크기(norm)를 곱한 뒤, 곱하고 두 벡터 사이의 각도에서 코사인 값만큼 크기를 늘린 값.

$$\mathbf{v} \cdot \mathbf{w} = \|\mathbf{v}\| \|\mathbf{w}\| \cos\theta$$

$$\cos0 = 1, \cos90 = 0, \cos180 = -1$$

$$\cos\theta = \frac{\mathbf{v} \cdot \mathbf{w}}{\|\mathbf{v}\| \|\mathbf{w}\|}$$


## 외적 (Outer Product)

열벡터와 행벡터를 이용해 **행렬**을 만든다.

$$\mathbf{v} \otimes \mathbf{w} = \mathbf{v}\mathbf{w}^T = 
\begin{bmatrix}v_1\\v_2\\\vdots\\v_m\end{bmatrix}
\begin{bmatrix}w_1 & w_2 & \cdots & w_n\end{bmatrix} =
\begin{bmatrix}
v_1 w_1 & v_1 w_2 & \cdots & v_1 w_n \\
v_2 w_1 & v_2 w_2 & \cdots & v_2 w_n \\
\vdots  & \vdots  & \ddots & \vdots  \\
v_m w_1 & v_m w_2 & \cdots & v_m w_n
\end{bmatrix}$$

- 각 **행**: 행벡터 $w_i$에 열벡터 원소 $v_i$를 곱한 것
- 각 **열**: 열벡터 $v_j$에 행벡터 원소 $w_j$를 곱한 것


## 직교벡터 분해 (Orthogonal Decomposition)

벡터를 두 개의 방향으로 쪼개는 것이 직교분해이다. 

v∥  =  기준 방향과 평행한 성분  (정사영(Projection)을 내적으로 계산)
v⊥  =  기준 방향과 수직인 성분

$$\mathbf{v} = \mathbf{v}_{\parallel} + \mathbf{v}_{\perp}$$


활용:
- 숨겨진 정보 추출
- 행렬을 다루기 쉬운 형태로 변환
- 데이터 압축 (ex. SVD, PCA)


## 선형 가중 결합 (Linear Combination)

벡터 덧셈 + 스칼라 곱, 둘을 합친 것


## 내적(닮은 정도)과 정사영 (inner product & projection)

$${a}^T{b} = \|a\| \cdot \|{b}\| \cos\theta = \|{a}\| \cos\theta \cdot \|{b}\| = \|{b}\| \cos\theta \cdot \|{a}\|$$

a를 b방향으로 정사영한 길이(∥a∥cosθ)와 b를 a방향으로 정사영한 길이(∥b∥cosθ), 내적은 이 둘 중 어느 쪽으로 해석해도 같은 값이 나온다.

$\frac{a}{\sqrt{a^T \cdot a}}$는 a와 방향은 같고 크기가 1인 단위벡터(unit vector)다. (normalize 가능) 

$\|a\| \cdot \cos\theta = \frac{a^T{b}}{b}$에서 b의 크기(방향 제외)를 나눠줌으로써 normalize한다. 

$\|a\| \cdot \cos\theta = \frac{a^T{b}}{\sqrt{b^Tb}} \cdot \frac{b}{\sqrt{b^T \cdot b}}$

$\frac{a^T{b}}{b^T{b}} \cdot b$


## 벡터의 norm

2-norm(L2 norm)으로 두 벡터 사이의 거리(길이)를 구하는데 쓴다.

$$a = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}, \quad \|a\|_2 = \sqrt{a^T a} = \sqrt{|1|^2 + |2|^2 + |3|^2} = (1^2 + 2^2 + 3^2)^{\frac{1}{2}}$$

1-norm(L1 norm)

$$b = \begin{bmatrix} 1 \\ 2 \\ -3 \end{bmatrix}, \quad \|b\|_1 = 1 + 2 + 3 = 6$$

