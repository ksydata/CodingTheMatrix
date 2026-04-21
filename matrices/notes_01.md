## 행렬과 전치(Transpose)

* $A = a_{ij} \leftrightarrow A^T = A_{ji}$

$$A = \left(\begin{matrix}
1 & 2 & 3\\
4 & 5 & 6\\
7 & 8 & 9\\
\end{matrix}\right)$$

* off-diagonal elements: {4,7,8}, {2,3,6}이며, 대각선 기준으로 전치 시 동일하면 symmetrix matrix라 한다. 

$$A^T = \left(\begin{matrix}
1 & 4 & 7\\
2 & 5 & 8\\
3 & 6 & 9\\
\end{matrix}\right)$$

* $(A*)^T = A^{Hermitian} = A$, 1+j에다가 켤레복소수를 구해 전치를 취한다.

$$A = \left(\begin{matrix}
1 & 1+j\\
1-j & 2\\
\end{matrix}\right)$$

* **${AB}^T = B^T \cdot A^T$**

$(A^T \cdot A)^T$와 $(A \cdot A^T)^T$는 자기 자신이 나오는데 이걸 symmetrix matrix라 한다. (행렬곱을 위한 전치)

그밖에 전치에 관한 정리에는 $det(A^T) = det(A)$와 $(A^T)^{-1} = (A^{-1})^T$ 등이 있다.


## 행렬의 곱셉과 네 가지 관점 [열 공간(column space) 등]

notes_02.markdown

## span과 column space(column space)

notes_02.markdown