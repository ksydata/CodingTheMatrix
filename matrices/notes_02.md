## 행렬(matrices): 벡터를 한 차원 더 끌어올린 객체, 숫자들의 직사각형 배열

### 1. 행렬곱(matrix multiplication)의 4가지 관점

**행렬이 벡터나 다른 행렬을 어떻게 변환하는지 이해하는게 핵심**

* 내적 확장(inner product expansion) : C의 각 원소 $c_{ij}$는 A의 i번째 행과 B의 j번째 열의 내적 $\sum_{i, j=1}^{n} \mathbf{A}_i \mathbf{B}_j$

* 외적 확장(outer product expansion) : AB는 A의 열 벡터들과 B의 행 벡터들의 외적 합으로 표현 $\mathbf{A}\mathbf{B}^T$

* A의 열들의 선형 결합 : AB의 각 열은 A의 열 벡터를 B의 원소들을 가중치로 하여 선형결합한 것

* B의 행들의 선형 결합 : AB의 각 행은 B의 행 벡터를 A의 원소들을 가중치로 하여 선형결합한 것

---

### 2. 역행렬과 기본 행렬(inverse and elementary matrix)

**역행렬이 있는지 없는지(가역성), 어떻게 찾을지 아는게 핵심**

* 정방 행렬(square matrix) A에 대해 $AA^{-1} = I$(identity matrix, 단위행렬)를 만족하는 $A^{-1}$을 역행렬(inverse matrix)이라 한다. 

행렬식(determinant)이 $ad - bc != 0$일 때 역행렬이 존재하며 이를 가역행렬(invertible matrix)라고 한다. [Q]

$A = \left(\begin{matrix}
a & b\\
c & d \\
\end{matrix}\right)$


* 기본 행렬(elementary matrix) : 단위행렬 $\mathbf{I}$에 기본행 연산(row operation)을 1회 적용하여 얻은 행렬이다. 행렬 $\mathbf{A}$에 왼쪽에 기본 행렬 $\mathbf{E}$를 곱하는 연산을 말한다. 

* Gauss-Jordan 소거법 : 역행렬을 구하는 가장 표준적인 알고리즘으로, $[A \mid I]$ 형태의 첨가행렬을 만들고, A를 I로 만드는 행 연산을 I에도 적용 $[I \mid A^{-1}]$을 얻을 수 있다. [Q]

---

### 3. LU분해(Lower-Upper Factorization)

$\mathbf{L}$, 하삼각행렬과 $\mathbf{R}$ 상삼각행렬의 곱으로 나누는 기법, 이는 연립방정식(linear system)을 효율적으로 풀거나 행렬의 구조를 파악하는데 도움이 된다. 가우스 소거법을 통해 $A$를 $U$로 변환하는 과정에서 사용되는 행 연산의 역연산을 L에 기록한다. 

행 교환이 필요한 경우 치환 행렬(permutation matrix) $\mathbf{P}$를 $\mathbf{A} = \mathbf{P}^T \cdot LU$로 분해한다. [Q] 

연립방정식 $Ax = b$를 $Ly = b$, $Ux = y$의 2단계로 나누어 효율적으로 풀 수 있다. 

---

### 4. 4가지 주요 부분 공간(four fundamental subspace)

* 열 공간, 행 공간(column space, row space)

* 영 공간(null space) : $Ax = 0$

* 좌영 공간(left null space) $A^Tx = 0$

* 기저(basis) : 선행 성분(leading variables)에 해당하는 열들이 열 공간의 기저가 되고, 0이 아닌 행들이 행 공간의 기저가 된다. [Q]

* 차원 정리(rank theorem)

---

### 5. 선형 변환(linear transformation)

행렬은 $\mathbf{R}^n$ 실수 공간의 벡터를 $\mathbf{R}^m$ 공간으로 옮기는 함수. 예를 들어, 반사(reflection), 회전(roatation), 투영(projection)이 있다. 