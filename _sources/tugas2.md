# **Dekomposisi QR dan QR Iteration**

---

## Matriks A

Diberikan matriks:

$$
A=
\begin{bmatrix}
2 & 1\\
1 & 2
\end{bmatrix}
$$

```python
from sympy import Matrix

A = Matrix([
    [2, 1],
    [1, 2]
])

print(A)
```

Output:

```python
Matrix([[2, 1], [1, 2]])
```

---

## Tahap 1 — Membentuk Vektor q₁

Kolom pertama matriks A:

$$
a_1=
\begin{bmatrix}
2\\
1
\end{bmatrix}
$$

---

### Menghitung Panjang Vektor a₁

Rumus norma vektor:

$$
\|a_1\|
=
\sqrt{2^2+1^2}
=
\sqrt{5}
$$

```python
from sympy import Matrix, sqrt

a1 = Matrix([
    [2],
    [1]
])

norma_a1 = sqrt(2**2 + 1**2)

print("Norma a1 =", norma_a1)
```

Output:

```python
Norma a1 = sqrt(5)
```

---

### Menghitung q₁

Rumus:

$$
q_1=\frac{a_1}{\|a_1\|}
$$

Maka:

$$
q_1=
\frac{1}{\sqrt5}
\begin{bmatrix}
2\\
1
\end{bmatrix}
=
\begin{bmatrix}
\dfrac{2}{\sqrt5}\\
\dfrac{1}{\sqrt5}
\end{bmatrix}
$$

```python
from sympy import Matrix, sqrt

a1 = Matrix([
    [2],
    [1]
])

q1 = a1 / sqrt(5)

print(q1)
```

Output:

```python
Matrix([
[2/sqrt(5)],
[1/sqrt(5)]
])
```

---

## Tahap 2 — Menghitung Dot Product q₁ · a₂

Kolom kedua matriks A:

$$
a_2=
\begin{bmatrix}
1\\
2
\end{bmatrix}
$$

Rumus dot product:

$$
q_1 \cdot a_2
=
\left(\frac{2}{\sqrt5}\times1\right)
+
\left(\frac{1}{\sqrt5}\times2\right)
$$

Hasil:

$$
q_1 \cdot a_2
=
\frac{4}{\sqrt5}
$$

```python
from sympy import Matrix, sqrt

a1 = Matrix([
    [2],
    [1]
])

a2 = Matrix([
    [1],
    [2]
])

q1 = a1 / sqrt(5)

dot = q1.dot(a2)

print(dot)
```

Output:

```python
4/sqrt(5)
```

---

## Tahap 3 — Menghitung v₂

Rumus Gram-Schmidt:

$$
v_2
=
a_2-(q_1\cdot a_2)q_1
$$

Substitusi:

$$
v_2
=
\begin{bmatrix}
1\\
2
\end{bmatrix}
-
\frac{4}{\sqrt5}
\begin{bmatrix}
\dfrac{2}{\sqrt5}\\
\dfrac{1}{\sqrt5}
\end{bmatrix}
$$

Hasil proyeksi:

$$
(q_1\cdot a_2)q_1
=
\begin{bmatrix}
\dfrac85\\
\dfrac45
\end{bmatrix}
$$

Maka:

$$
v_2
=
\begin{bmatrix}
1\\
2
\end{bmatrix}
-
\begin{bmatrix}
\dfrac85\\
\dfrac45
\end{bmatrix}
=
\begin{bmatrix}
-\dfrac35\\
\dfrac65
\end{bmatrix}
$$

```python
from sympy import Matrix, sqrt

a1 = Matrix([
    [2],
    [1]
])

a2 = Matrix([
    [1],
    [2]
])

q1 = a1 / sqrt(5)

proj = q1.dot(a2) * q1

v2 = a2 - proj

print(v2)
```

Output:

```python
Matrix([
[-3/5],
[ 6/5]
])
```

---

## Tahap 4 — Normalisasi v₂ Menjadi q₂

Norma v₂:

$$
\|v_2\|
=
\sqrt{
\left(-\frac35\right)^2
+
\left(\frac65\right)^2
}
$$

$$
=
\sqrt{
\frac9{25}
+
\frac{36}{25}
}
$$

$$
=
\sqrt{\frac{45}{25}}
=
\frac3{\sqrt5}
$$

---

### Menghitung q₂

Rumus:

$$
q_2
=
\frac{v_2}{\|v_2\|}
$$

Maka:

$$
q_2
=
\begin{bmatrix}
-\dfrac1{\sqrt5}\\
\dfrac2{\sqrt5}
\end{bmatrix}
$$

```python
from sympy import Matrix, sqrt

v2 = Matrix([
    [-3/5],
    [ 6/5]
])

norma_v2 = sqrt(v2.dot(v2))

q2 = v2 / norma_v2

print(q2)
```

Output:

```python
Matrix([
[-1/sqrt(5)],
[ 2/sqrt(5)]
])
```

---

## Tahap 5 — Membentuk Matriks Q

Matriks Q dibentuk dari q₁ dan q₂:

$$
Q=
\begin{bmatrix}
\dfrac2{\sqrt5} & -\dfrac1{\sqrt5}\\
\dfrac1{\sqrt5} & \dfrac2{\sqrt5}
\end{bmatrix}
$$

```python
from sympy import Matrix, sqrt

q1 = Matrix([
    [2/sqrt(5)],
    [1/sqrt(5)]
])

q2 = Matrix([
    [-1/sqrt(5)],
    [ 2/sqrt(5)]
])

Q = Matrix.hstack(q1, q2)

print(Q)
```

Output:

```python
Matrix([
[2/sqrt(5), -1/sqrt(5)],
[1/sqrt(5),  2/sqrt(5)]
])
```

---

## Tahap 6 — Menghitung Matriks R

Rumus:

$$
R=Q^TA
$$

Hasil:

$$
R=
\begin{bmatrix}
\sqrt5 & \dfrac4{\sqrt5}\\
0 & \dfrac3{\sqrt5}
\end{bmatrix}
$$

```python
from sympy import Matrix, sqrt

A = Matrix([
    [2, 1],
    [1, 2]
])

Q = Matrix([
    [2/sqrt(5), -1/sqrt(5)],
    [1/sqrt(5),  2/sqrt(5)]
])

R = Q.T * A

print(R)
```

Output:

```python
Matrix([
[sqrt(5), 4/sqrt(5)],
[      0, 3/sqrt(5)]
])
```

---

## Tahap 7 — Verifikasi QR = A

Kalikan:

$$
QR
$$

$$
=
\begin{bmatrix}
\dfrac2{\sqrt5} & -\dfrac1{\sqrt5}\\
\dfrac1{\sqrt5} & \dfrac2{\sqrt5}
\end{bmatrix}
\begin{bmatrix}
\sqrt5 & \dfrac4{\sqrt5}\\
0 & \dfrac3{\sqrt5}
\end{bmatrix}
$$

Hasil:

$$
QR=
\begin{bmatrix}
2 & 1\\
1 & 2
\end{bmatrix}
=A
$$

```python
from sympy import Matrix, sqrt

Q = Matrix([
    [2/sqrt(5), -1/sqrt(5)],
    [1/sqrt(5),  2/sqrt(5)]
])

R = Matrix([
    [sqrt(5), 4/sqrt(5)],
    [0,       3/sqrt(5)]
])

print(Q * R)
```

Output:

```python
Matrix([
[2, 1],
[1, 2]
])
```

---

## Tahap 8 — Iterasi QR Pertama

Rumus iterasi:

$$
A_{k+1}=R_kQ_k
$$

Iterasi pertama:

$$
A_1
=
RQ
$$

$$
=
\begin{bmatrix}
2.8 & 0.6\\
0.6 & 1.2
\end{bmatrix}
$$

```python
from sympy import Matrix, sqrt

Q = Matrix([
    [2/sqrt(5), -1/sqrt(5)],
    [1/sqrt(5),  2/sqrt(5)]
])

R = Matrix([
    [sqrt(5), 4/sqrt(5)],
    [0,       3/sqrt(5)]
])

A1 = R * Q

print(A1)
```

Output:

```python
Matrix([
[14/5, 3/5],
[ 3/5, 6/5]
])
```

---

## Tahap 9 — QR Iteration 10 Kali

```python
from sympy import Matrix, sqrt, N, pprint

A = Matrix([
    [2, 1],
    [1, 2]
])

print("A0 =")
pprint(A)

for k in range(1, 11):

    a1 = A[:, 0]
    a2 = A[:, 1]

    # Gram-Schmidt
    q1 = a1 / sqrt(a1.dot(a1))

    proj = q1.dot(a2) * q1

    v2 = a2 - proj

    q2 = v2 / sqrt(v2.dot(v2))

    # Susun Q dan R
    Q = Matrix.hstack(q1, q2)

    R = Q.T * A

    # Update matriks
    A = R * Q

    print(f"\nA{k} =")
    pprint(N(A, 6))
```

---

## Hasil Iterasi

$$
A_1=
\begin{bmatrix}
2.8 & 0.6\\
0.6 & 1.2
\end{bmatrix}
$$

$$
A_2=
\begin{bmatrix}
2.96 & 0.28\\
0.28 & 1.04
\end{bmatrix}
$$

$$
A_3=
\begin{bmatrix}
2.9918 & 0.1233\\
0.1233 & 1.0082
\end{bmatrix}
$$

$$
A_4=
\begin{bmatrix}
2.9986 & 0.0549\\
0.0549 & 1.0014
\end{bmatrix}
$$

$$
A_5=
\begin{bmatrix}
2.9997 & 0.0244\\
0.0244 & 1.0003
\end{bmatrix}
$$

$$
A_{10}
\approx
\begin{bmatrix}
3 & 0\\
0 & 1
\end{bmatrix}
$$

---

## Kesimpulan

Metode QR Iteration berhasil menemukan nilai eigen matriks:

$$
A=
\begin{bmatrix}
2 & 1\\
1 & 2
\end{bmatrix}
$$

Nilai diagonal matriks hasil iterasi mendekati:

$$
\lambda_1=3
$$

$$
\lambda_2=1
$$

Jadi nilai eigen matriks A adalah:

$$
\lambda_1=3
$$

$$
\lambda_2=1
$$

---

### clik link ini untuk mengarah ke colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/10Vt-lW4kQfUDR9UvyDifsQwe1P9mNy9Y?usp=sharing)