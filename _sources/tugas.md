# **Tranformasi Matriks**

## **Representasi Titik dalam Koordinat Homogen**

Setiap titik pada bidang Kartesius:

$$
(x, y)
$$

diubah menjadi bentuk homogen:

$$
\begin{bmatrix}
x \\
y \\
1
\end{bmatrix}
$$

Tujuan:
- agar translasi bisa direpresentasikan dalam bentuk perkalian matriks

## **Matriks Translasi**

Translasi sejauh $(a, b)$ dinyatakan sebagai:

$$
T(a,b) =
\begin{bmatrix}
1 & 0 & a \\
0 & 1 & b \\
0 & 0 & 1
\end{bmatrix}
$$

Jika dikalikan pada titik:

$$
T(a,b)
\begin{bmatrix}
x \\
y \\
1
\end{bmatrix}
=
\begin{bmatrix}
x + a \\
y + b \\
1
\end{bmatrix}
$$

## **Translasi pada Kasus Animasi**

Dalam animasi:
- hanya terjadi pergeseran horizontal
- sehingga:

$$
a = t,\quad b = 0
$$

Maka:

$$
T(t,0) =
\begin{bmatrix}
1 & 0 & t \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

Hasil translasi:

$$
(x, y) \rightarrow (x + t, y)
$$

## **Matriks Refleksi terhadap Sumbu-Y**

Refleksi terhadap sumbu-Y dalam bentuk homogen:

$$
R_y =
\begin{bmatrix}
-1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

Efeknya:

$$
(x, y) \rightarrow (-x, y)
$$

## **Komposisi Transformasi**

Urutan transformasi:
- Translasi
- Refleksi

Secara matriks:

$$
M = R_y \cdot T(t,0)
$$

## **Perkalian Matriks**

$$
M =
\begin{bmatrix}
-1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
\begin{bmatrix}
1 & 0 & t \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

Hitung elemen per elemen:

Baris 1:

$(−1)(1)+(0)(0)+(0)(0)=−1 $

$(−1)(0)+(0)(1)+(0)(0)=0$

$(−1)(t)+(0)(0)+(0)(1)=−t$

Baris 2:

$0⋅1+1⋅0+0⋅0=0$

$0⋅0+1⋅1+0⋅0=1$

$0⋅t+1⋅0+0⋅1=0$

Baris 3:

$0~0~1$

Hasil:

$$
M =
\begin{bmatrix}
-1 & 0 & -t \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

## **Transformasi Akhir**

Terapkan ke titik:

$$
M
\begin{bmatrix}
x \\
y \\
1
\end{bmatrix}
=
\begin{bmatrix}
-(x + t) \\
y \\
1
\end{bmatrix}
$$

Sehingga:

$$
(x, y) \rightarrow (-(x+t), y)
$$

## **Ketergantungan terhadap Waktu**

parameter $t$ berubah setiap waktu:

$$t = 0,~1,~2,~3,...$$

Sehingga posisi menjadi fungsi waktu:

$$
x'(t) = -(x + t)
$$

$$
y'(t) = y
$$

## **Pembatasan Domain (Constraint)**

Agar objek tetap dalam batas koordinat:

$$
t_{min} \leq t \leq t_{max}
$$

Dengan:

$$
t_{max} = x_{kanan} - x_{maks}
$$

$$
t_{min} = x_{kiri} - x_{min}
$$

Tujuan:

$$
x'(t) \in [x_{\text{kiri}}, x_{\text{kanan}}]
$$

## **Kesimpulan**

Transformasi keseluruhan dinyatakan dengan matriks:

$$
M =
\begin{bmatrix}
-1 & 0 & -t \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

yang merupakan hasil komposisi:

- translasi sejauh $t$ pada sumbu-X

- refleksi terhadap sumbu-Y

dan menghasilkan:

$$
(x, y) \rightarrow (-(x+t), y)
$$

#### **Implementasi Di Colab: https://colab.research.google.com/drive/1C2bOEoPZ66XCb5f2ckI7jeoinAnZ8rDT?usp=sharing**