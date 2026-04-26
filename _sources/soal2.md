# **Soal Determinan Matriks dan Adjoin**

**A. Hitunglah determinan matrik berikut dengan menggunakan rumus expansi baris**

$$\sum_{k=1}^{n} (-1)^{i+k} a_{ik} M_{ik}$$

dengan $M_{ij}$ adalah minior dari matrik A dan

$$M_{ij} = \det A_{ij}.$$

$A_{ij}$ adalah submatrik dengan menghapus baris i dan kolom kolom j dari matrix $A_{mxn}$ dengan $1 \le i, j \le n$ 

1. 
$$
A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}
$$

2. 
$$
A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}
$$

3. 
$$
A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}.
$$

**B. Gunakan rumus matriks adjoin untuk menghitung invers dari matriks berikut dengan rumus**

$$
(\operatorname{adj} A)_{ij} = (-1)^{i+j} M_{ji}
$$

dan

$$
A^{-1} = \frac{1}{\det A} \operatorname{adj} A
$$

4. 
$$
A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}
$$

5. 
$$
A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}
$$

6. 
$$
A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}.
$$

**Jawaban A**

1.

$$A= \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$$

Rumus:

$$det(A)=ad−bc$$

$$=(−7)(4)−(−5)(1)=−28+5=−23$$

$$det(A)=−23$$

2. 

$$A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$$

Gunakan ekspansi baris pertama:

$$
det(A)=0 ⋅ M_{11} − 2 ⋅ M_{12} + (−3) ⋅ M_{13}
$$​

Hitung minor:

1. Minor $M_{12}$ :

$$
\begin{vmatrix}1 & −1 \\ 0 & 1\end{vmatrix} = (1)(1)−(−1)(0)=1
$$​

2. Minor $M_{13}$ :

$$
\begin{vmatrix}1 & −2 \\ 0 & 0\end{vmatrix} =(1)(0)−(−2)(0)=0
$$

Substitusi:

$det(A)=0−2(1)+(−3)(0)=−2$

$det(A)=−2$


3. 

$$A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$$

Gunakan ekspansi baris pertama:

$$det(A)=\sum_{k=1}^n (-1)^{i+k} a_{ik} M_{ik}$$

$$det(A) = 1 ⋅ M_{11} − (−3) ⋅ M_{12} + 1 ⋅ M_{13} − 1 ⋅ M_{14}$$

1. Hitung Minor $M_{11}$

Hapus baris 1 kolom 1:

$$M_{11} = \begin{vmatrix} 1 & 1 & 1 \\ 1 & -3 & 1 \\ 1 & 1 & -3 \end{vmatrix} $$

Ekspansi baris pertama:

$$=1 \begin{vmatrix} −3 & 1 \\ 1 & −3 \end{vmatrix} -1 \begin{vmatrix} 1 & 1 \\ 1 & -3 \\ \end{vmatrix} +1 \begin{vmatrix} 1 & 1 \\ -3 & 1 \\ \end{vmatrix}$$

Hitung:

$=1[(9−1)]−1[(−3−1)]+1[(1+3)]$

$=8+4+4=16$

$M_{11} = 16$

2. Hitung Minor $M_{12}$

Hapus baris 1 kolom 2:

$$M_{12} = \begin{vmatrix} -3 & 1 & 1 \\ 1 & -3 & 1 \\ 1 & 1 & -3 \end{vmatrix}$$

Ekspansi baris pertama:

$$=(-3) \begin{vmatrix} −3 & 1 \\ 1 & −3 \end{vmatrix} -1 \begin{vmatrix} 1 & 1 \\ 1 & -3 \\ \end{vmatrix} +1 \begin{vmatrix} 1 & -3 \\ 1 & 1 \\ \end{vmatrix}$$

$$=(−3)(8)−(−4)+4=−24+4+4=−16$$

$$M_{12}=−16$$

3. Hitung Minor $M_{13}$

Hapus baris 1 kolom 3:

$$M_{13} = \begin{vmatrix} -3 & 1 & 1 \\ 1 & 1 & 1 \\ 1 & 1 & -3 \end{vmatrix}$$

Ekspansi:

$$=(-3) \begin{vmatrix} 1 & 1 \\ 1 & −3 \end{vmatrix} -1 \begin{vmatrix} 1 & 1 \\ 1 & -3 \\ \end{vmatrix} +1 \begin{vmatrix} 1 & 1 \\ 1 & 1 \\ \end{vmatrix}$$

$$=(−3)(−4)−(−4)+0=12+4=16$$

$$M_{13}=16$$

4. Hitung Minor $M_{14}$

Hapus baris 1 kolom 4:

$$M_{14} = \begin{vmatrix} -3 & 1 & 1 \\ 1 & 1 & -3 \\ 1 & 1 & 1 \end{vmatrix}$$

Ekspansi:

$$=(-3) \begin{vmatrix} 1 & -3 \\ 1 & 1 \end{vmatrix} -1 \begin{vmatrix} 1 & -3 \\ 1 & 1 \\ \end{vmatrix} +1 \begin{vmatrix} 1 & 1 \\ 1 & 1 \\ \end{vmatrix}$$

$$​=(−3)(4)−(4)+0=−12−4=−16$$

$$
M_{14}=−16
$$

5. Substitusi ke determinan

$det(A)=1(16)−(−3)(−16)+1(16)−1(−16)$

$=16−48+16+16=0$

$det(A)=0$

**Jawaban B**

4. 

$$A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$$

Determinan:

$det(A)=(−7)(4)−(−5)(1)=−28+5=−23$

Adjoin:

$$adj(A)\begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix}$$

Invers:

$$A^{-1} = \frac{1}{-23} \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix} = \begin{bmatrix} -\frac{4}{23} & -\frac{5}{23} \\ \frac{1}{23} & \frac{7}{23} \end{bmatrix}$$

5. 

$$A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$$

**Determinan:**

$det(A)=−2$

**Matriks kofaktor**

Hitung minor + tanda:

$$C = \begin{bmatrix} -2 & -1 & 0 \\ -2 & 0 & 0 \\ -8 & -3 & -2 \end{bmatrix}$$

**Adjoin (transpose kofaktor)**

$$Adj(A) = \begin{bmatrix} -2 & -2 & -8 \\ -1 & 0 & -3 \\ 0 & 0 & -2 \end{bmatrix}$$

**Invers**

$$A^{-1} = \frac{1}{-2} Adj(A)$$

$$A^{-1} = \begin{bmatrix} 1 & 1 & 4 \\ \frac{1}{2} & 0 & \frac{3}{2} \\ 0 & 0 & 1 \end{bmatrix}$$

6. 

$$A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$$

**Determinan**

Dari hasil sebelumnya:

$$det(A)=0$$

Kesimpulan penting

Karena:

$$det(A)=0$$

maka:

$A^{−1}$ **tidak ada (tidak invertible)**