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