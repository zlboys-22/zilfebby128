# **Tugas Sistem Persamaan 5 Variabel**
**Contoh Sistem persamaan yang di pakai:**

$$
\begin{bmatrix}
x_1 + x_2 + x_3 + x_4 + x_5 = 15 \\
2x_1 + x_2 + x_3 + x_4 + x_5 = 16 \\
2x_1 + 3x_2 + x_3 + x_4 + x_5 = 20 \\
2x_1 + 3x_2 + 4x_3 + x_4 + x_5 = 29 \\
2x_1 + 3x_2 + 4x_3 + 5x_4 + x_5 = 45
\end{bmatrix}
$$

**Ubah ke dalam bentuk Matrix augmented:**

$$
\begin{bmatrix}
1 & 1 & 1 & 1 & 1 & 15 \\
2 & 1 & 1 & 1 & 1 & 16\\
2 & 3 & 1 & 1 & 1 & 20\\
2 & 3 & 4 & 1 & 1 & 29\\
2 & 3 & 4 & 5 & 1 & 45
\end{bmatrix}
$$

## **Eliminasi Gussian**
###**Langkah 1:**

**Operasi baris:**

$$ R_2 = R_2 - 2R_1 \\
R_3 = R_3 - 2R_1 \\
R_4 = R_4 - 2R_1 \\
R_5 = R_5 - 2R_1
$$

**Hasil:**
$$
\begin{bmatrix}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & -1 & -1 & -1 & -1 & -14\\
0 & 1 & -1 & -1 & -1 & 10\\
0 & 1 & 2 & -1 & -1 & -1\\
0 & 1 & 2 & 3 & -1 & 15
\end{bmatrix}
$$

### **Langkah 2:**

**Operasi baris:**
$$
R_3 = R_3 + 2R_2 \\
R_4 = R_4 + 2R_2 \\
R_5 = R_5 + 2R_2
$$

**Hasil:**
$$
\begin{bmatrix}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & -1 & -1 & -1 & -1 & -14\\
0 & 0 & -2 & -2 & -2 & -24\\
0 & 0 & 1 & -2 & -2 & -15\\
0 & 0 & 1 & 2 & -2 & 1
\end{bmatrix}
$$

### **Langkah 3:**

**Operasi baris:**
$$
R_4 = R_4 + \frac{1}{2}R_3 \\
R_5 = R_5 + \frac{1}{2}R_3
$$

**Hasil:**
$$
\begin{bmatrix}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & -1 & -1 & -1 & -1 & -14\\
0 & 0 & -2 & -2 & -2 & -24\\
0 & 0 & 0 & -3 & -3 & -27\\
0 & 0 & 0 & 1 & -3 & -11
\end{bmatrix}
$$

### **Langkah 4:**

**Operasi baris:**
$$
R_5 = R_5 + \frac{1}{3}R_4
$$

**Hasil:**
$$
\begin{bmatrix}
1 & 1 & 1 & 1 & 1 & 15 \\
0 & -1 & -1 & -1 & -1 & -14\\
0 & 0 & -2 & -2 & -2 & -24\\
0 & 0 & 0 & -3 & -3 & -27\\
0 & 0 & 0 & 0 & -4 & -20
\end{bmatrix}
$$
Ini disebut **matriks segita atas**

### **Langkah 5:**

**Eliminasi Gauss-Jordan:**

Bagi setiap baris dengan koefisien utamanya
Substitusikan Dari baris terakhir:
$$
-4x_5 = -20 ⇒ x_5 = 5 \\
-3x_4 - 3(5) = -27 ⇒ x_4 = 4 \\
-2x_3 - 2(4) - 2(5) = -24 ⇒ x_3 = 3 \\
-x_2 ​− 3 − 4 − 5 = −14 ⇒ x_2 = 2 \\
x_1 ​+ 2 + 3 + 4 + 5 = 15 ⇒ x_1 = 1
$$


**Hasil Akhir:**
$$
\begin{bmatrix}
1 & 0 & 0 & 0 & 0 & 1 \\
0 & 1 & 0 & 0 & 0 & 2 \\
0 & 0 & 1 & 0 & 0 & 3 \\
0 & 0 & 0 & 1 & 0 & 4 \\
0 & 0 & 0 & 0 & 1 & 5
\end{bmatrix}
$$
**Artinta:**

$
x_1 = 1\\
x_2 = 2\\
x_3 = 3\\
x_4 = 4\\
x_5 = 5
$