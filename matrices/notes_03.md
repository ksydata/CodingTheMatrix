## 행렬(matrices): 벡터를 한 차원 더 끌어올린 객체, 숫자들의 직사각형 배열

### 0. 선형대수의 응용 : edge & node [AS-IS]

### 4. 부분 공간과 생성 집합(Subspace Spanning sets)

정의 : $\mathbf{R^n}$의 부분공간은 다음을 만족하는 $\mathbf{R^n}$ 안 벡터의 모임 $\mathbf{S}$이다. 
> 1. zero vector ${0}$은 $\mathbf{S}$에 속한다.
> 2. $u$, $v$가 $\mathbf{S}$에 속하면 $u+v$도 $\mathbf{S}$에 속한다. 
> 3. $u$가 $\mathbf{S}$에 속하고 $c$가 스칼라이면, $cu$도 $\mathbf{S}$에 속한다. 즉, $\mathbf{S}$는 스칼라에 대해 닫혀 있다. 즉, 2,3.에 따라 $\mathbf{S}$는 일차선형결합(linear combination)에 관하여 닫혀있음을 알 수 있다. 
> 만약 $u_1, u_2, \cdots, u_k$가 $\mathbf{S}$에 속하고 $c_1, c_2, \cdots, c_k$가 스칼라이면 $c_1 u_1, c_2 u_2, \cdots, c_k u_k$도 $\mathbf{S}$에 속한다.

> 예제 3.38 : $z_1​ = 3y_1​, z_2 = −2y_2$를 만족하는 모든 벡터의 집합이 $\mathbf{R^3}$의 부분 공간임을 보여라.


> 예제 3.39 : $z_1 ​= 3y_1​+1, z_2​ = −2y_2​$를 만족하는 모든 벡터의 집합이 부분 공간인지 판정하라.


> 예제 3.40 : $z = x^2$를 만족하는 모든 벡터의 집합이 $\mathbf{R^3}$의 부분 공간임을 보여라.