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

행렬식(determinant, det A)이 $ad - bc \neq 0$일 때 역행렬이 존재하며 이를 가역행렬(invertible matrix)라고 한다. 역행렬이 존재할 때, $A = \left(\begin{matrix} a & b\\ c & d \\ \end{matrix}\right)$의 역행렬은 **대각성분의 위치를 바꾸고 다른 두 개의 성분은 부호를 바꾼 행렬에 **대각성분의 위치를 바꾸고 다른 두 개의 성분은 부호를 바꾼 행렬에 $\frac{1}{det A}$를 곱한 것이다.**

> $\left(\begin{matrix} a & b \\ c & d \\ \end{matrix}\right) \left(\begin{matrix} d & -b \\ -c & a \\ \end{matrix}\right) = \left(\begin{matrix} ad-bc & -ab+ba(0) \\ cd-dc(0) & -cb+da \\ \end{matrix}\right) = detA(ad-bc) \left(\begin{matrix} 1 & 0 \\ 0 & 1 \\ \end{matrix}\right)$

> detA($ad-bc = 0$)가 0인 경우, $a = 0$이면, $bc = 0$이고 $b = 0$(첫 번째 행이 영벡터)이든 $c = 0$(첫 번째 열이 영벡터)이든 역행렬 불가하다. 

> 그렇다면 detA($ad-bc = 0$)가 0인 경우, $a \neq 0$이면, 해가 존재하지 않는다. 
> - $d = \frac{bc}{a}$이므로, $A = \left(\begin{matrix} a & b \\ c & \frac{bc}{a} \\ \end{matrix}\right) = \left(\begin{matrix} a & b \\ k \cdot a & k \cdot b \\ \end{matrix}\right)$ (단, $k = \frac{c}{a}$)
> - 즉, A의 두 번째 행이 첫 번째 행의 k배다. 
> $A^{-1} = \left(\begin{matrix} w & x \\ y & z \\ \end{matrix}\right)$, 만약 A가 역행렬을 갖는다면, 대응되는 연립 일차방정식은 해가 있는지 증명한다. 
> - $AA^{-1} = I$(단위 행렬)에서 연립방정식 $\begin{cases} aw + by = 1 \\ ax + bz = 0 \\ kaw + kby = 0 \\ kax + kbz = 1 \end{cases}$, $k = 0$은 모순으로 해가 존재하지 않는다. 

* 기본 행렬(elementary matrix) : 단위행렬 $\mathbf{I}$에 기본행 연산(row operation)을 1회 적용하여 얻은 행렬이다. 행렬 $\mathbf{A}$에 왼쪽에 기본 행렬 $\mathbf{E}$를 곱하는 연산을 말한다. 수학적으로 $E₃E₂E₁A = I$ 이면 $E₃E₂E₁I = A⁻¹$이다.

> 예제 3.24 적용
> $A = \left(\begin{matrix} 1 & 2 \\ 3 & 4 \\ \end{matrix}\right)$와 $B = \left(\begin{matrix} 12 & -15 \\ 4 & -5 \\ \end{matrix}\right)$의 역행렬이 존재하면, 역행렬을 구하라.
>
> - A : $detA = 1 * 4 - 2 * 3 = -2(ad - bc = \neq 0)$이므로 A는 가역행렬이다. 
> - B : $detB = 12 * (-5) - (-15) * 4 = 0$이므로 B는 가역행렬이 아니다. 

* Gauss-Jordan 소거법 : 역행렬을 구하는 가장 표준적인 알고리즘으로, $[A \mid I]$ 형태의 첨가행렬을 만들고, A를 I로 만드는 행 연산을 I에도 적용 $[I \mid A^{-1}]$을 얻을 수 있다. 

> 예제 3.25 : 역행렬을 이용한 연립방정식 풀이
> 계수행렬의 역행렬을 이용하여 연립일차방정식 $\begin{cases} x + 2y = 1 \\ 3x + 4y = -3 \end{cases}$를 풀어라.
> $\mathbf{A}x = b$는 유일한 해 $x = \mathbf{A}^{-1}b$를 가지는 정리를 풀이에 이용하라. 
> 
> - **방법 1 : 공식 활용**
> - 계수행렬 : $A = \left(\begin{matrix} 1 & 2 \\ 3 & 4 \\ \end{matrix}\right)$
> - $Ax = b$ 형태로 쓰면 : $\left(\begin{matrix} 1 & 2 \\ 3 & 4 \\ \end{matrix}\right) \left(\begin{matrix} x \\ y \\ \end{matrix}\right) = \left(\begin{matrix} 1 \\ -3 \\ \end{matrix}\right)$
> - 정리에 의해 : $x = A^{-1}b = \left(\begin{matrix} -2 & 1 \\ 3/2 & -1/2 \\ \end{matrix}\right) \left(\begin{matrix} 1 \\ -3 \\ \end{matrix}\right) = \left(\begin{matrix} -5 \\ 3 \\ \end{matrix}\right)$
> - $A^{-1} = \frac{1}{-2}\left(\begin{matrix} 4 & -2 \\ -3 & 1 \\ \end{matrix}\right) = \left(\begin{matrix} \frac{4}{-2} & \frac{-2}{-2} \\ \frac{-3}{-2} & \frac{1}{-2} \\ \end{matrix}\right) = \left(\begin{matrix} -2 & 1 \\ \frac{3}{2} & -\frac{1}{2} \\ \end{matrix}\right)$ (단, 단위행렬 $I$를 얻기 위해 $k = \frac{1}{detA} = \frac{1}{-2}$(스케일 조정 인자)를 곱한다.)
> - 따라서 $x = -5, y = 3$

> - **방법 2 : 가우스 조르단 활용**
> - 첨가행렬 $[A \mid I] = \left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 3 & 4 & 0 & 1\\ \end{array}\right)$
> - 단계 1($R_2 - 3R_1 \rightarrow R_2$) : 첫 번째 열 아래를 0으로 변환
> $\left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & -2 & -3 & 1\\ \end{array}\right)$
> - 단계 2($\frac{-1}{2}R_2 \rightarrow R_2$) : 두 번째 행의 선행 성분(leading entry)를 1로 변환
> $\left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & 1 & \frac{3}{2} & \frac{-1}{2} \\ \end{array}\right)$
> - 단계 3($R_1 - 2R_2 \rightarrow R_1$) : 두 번째 열 위를 0으로 변환
> $\left(\begin{array}{cc|cc} 1 & 0 & -2 & 1 \\ 0 & 1 & \frac{3}{2} & \frac{-1}{2} \\ \end{array}\right)$
> - 왼쪽 행렬을 단위 행렬 $I$로 변환하여 오른쪽 역행렬 계산, $A^{-1} = \left(\begin{matrix} -2 & 1 \\ \frac{3}{2} & -\frac{1}{2} \\ \end{matrix}\right)$ 

---

### 3.1. LU분해(Lower-Upper Factorization)

$\mathbf{L}$, 하삼각행렬과 $\mathbf{R}$ 상삼각행렬의 곱으로 나누는 기법, 이는 연립방정식(linear system)을 효율적으로 풀거나 행렬의 구조를 파악하는데 도움이 된다. 가우스 소거법을 통해 $A$를 $U$로 변환하는 과정에서 사용되는 행 연산의 역연산을 L에 기록한다. 

행 교환이 필요한 경우 치환 행렬(permutation matrix) $\mathbf{P}$를 $\mathbf{A} = \mathbf{P}^T \cdot LU$로 분해한다. [Q] 

연립방정식 $Ax = b$를 $Ly = b$, $Ux = y$의 2단계로 나누어 효율적으로 풀 수 있다. 


> 예제 3.33 : Revisiting Gaussian Elimination
> - 계수행렬 : $A = \left(\begin{matrix} 2 & 1 & 3 \\ 4 & -1 & 3 \\ -2 & 5 & 5 \\ \end{matrix}\right)$
> - $R_2 \leftarrow R_2 - 2R_1$ : $A = \left(\begin{matrix} 2 & 1 & 3 \\ *0 & -3 & -3* \\ -2 & 5 & 5 \\ \end{matrix}\right)$ $E_1 = \left(\begin{matrix} 1 & 0 & 0 \\ *-2* & 1 & 0 \\ 0 & 0 & 1 \\ \end{matrix}\right)$
> - $R_3 \leftarrow R_3 + R_1$ : $A = \left(\begin{matrix} 2 & 1 & 3 \\ 0 & -3 & -3 \\ *0 & 6 & 8* \\ \end{matrix}\right)$ $E_2 = \left(\begin{matrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ *1* & 0 & 1 \\ \end{matrix}\right)$

> - $R_3 \leftarrow R_3 + 2R_2$ : $A = \left(\begin{matrix} 2 & 1 & 3 \\ 0 & -3 & -3 \\ *0 & 0 & 2* \\ \end{matrix}\right)$ $E_3 = \left(\begin{matrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & *2* & 1 \\ \end{matrix}\right)$
> - $E_3E_2E_1A = U$
> - $A = E_1^{-1}E_2^{-1}E_3^{-1}U = \left(\begin{matrix} 1 & 0 & 0 \\ *2* & 1 & 0 \\ 0 & 0 & 1 \\ \end{matrix}\right) \cdot \left(\begin{matrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ *-1* & 0 & 1 \\ \end{matrix}\right) \cdot  \left(\begin{matrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & *-2* & 1 \\ \end{matrix}\right) \cdot U$
> - $A = \left(\begin{matrix} 1 & 0 & 0 \\ *2* & 1 & 0 \\ *-1* & *-2* & 1 \\ \end{matrix}\right) \cdot U$ 

L은 단위 하삼각행렬로, 대각성분이 1이고 위의 성분이 모두 0인 행렬을 말한다. 또한, 행렬 A가 어떤 행교환도 하지 않고 행사다리꼴로 변형될 수 있는 정사각행렬(square matrix)이면, A는 LU분해 가능하다.

> 예제 3.34 : A의 LU분해를 이용하여 연립방정식의 해를 구하는 방법
> - 전진대입법 $Ly = b$를 y에 대하여 푼다, $b = \left(\begin{matrix} 1 \\ -4 \\ 9 \\ \end{matrix}\right)$
> - $A = LU = \left(\begin{matrix} 1 & 0 & 0 \\ *2* & 1 & 0 \\ *-1* & *-2* & 1 \\ \end{matrix}\right) \cdot \left(\begin{matrix} 2 & 1 & 3 \\ 4 & -1 & 3 \\ -2 & 5 & 5 \\ \end{matrix}\right)$
> - $\begin{cases} y_1 = 1 \\ 2y_1 + y_2 = -4 \\ -y_1 -2y_2 + y_3 = 9 \end{cases}$, $y = \left(\begin{matrix} 1 \\ -6 \\ -2 \\ \end{matrix}\right)$

> - 후진대입법 $Ux = y$를 x에 대하여 푼다, $Ux = \left(\begin{matrix} 2 & 1 & 3 \\ 4 & -1 & 3 \\ -2 & 5 & 5 \\ \end{matrix}\right) \cdot x = \left(\begin{matrix} 1 \\ -6 \\ -2 \\ \end{matrix}\right)$
> - $\begin{cases} 2x_1 + x_2 + 3x_3 = 1 \\ -3x_2 -3x_3 = -6 \\ 2x_3 = -2 \end{cases}$, $x = \left(\begin{matrix} \frac{1}{2} \\ 3 \\ -1 \\ \end{matrix}\right)$

A가 LU 분해가 가능한 가역행렬(역행렬이 있으면)이면, L과 U는 유일하다.

### 3.2. P^TLU분해(Permutation matrix, Lower-Upper Factorization)

P가 치환행렬이면, $P^{-1} = P^T$다. 일반적으로 행렬 $A = P^{-1}LU = P^TLU$로 분해할 수 있다. 모든 정사각행렬은 P^TLU분해 가능하다.

> 예제 3.36 : A의 P^TLU분해를 구하여라.
> - 계수행렬 : $A = \left(\begin{matrix} 0 & 0 & 6 \\ 1 & 2 & 3 \\ 2 & 1 & 4 \\ \end{matrix}\right)$


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