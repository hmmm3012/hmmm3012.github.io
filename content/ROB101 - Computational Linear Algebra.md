---
tags:
  - course
  - math
title: ROB101 - Computational Linear Algebra
---
> [!info] Intro
> Đây là môn học dành cho sinh viên năm 1 ở U-M, tập trung vào các khái niệm cơ bản của đại số tuyến tính.  Nhánh toán này là xương sống của các hệ thống máy tính, robot hiện đại. Không tập trung sa đà vào lý thuyết, ROB101 sẽ dạy sinh viên cách sử dụng đại số tuyến tính vào quá trình phân tích bài toán thực tế nhiều hơn. 

# Các tài liệu liên quan
- Toàn bộ labs, lecture notes và videos giảng dạy nằm trong [này](https://github.com/michiganrobotics/rob101/).
- Ngoài ra, có thể tham khảo thêm các khoá về đại số tuyến tính rất nổi tiếng như [18.06](https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011) của thầy Gilbert Strang.
- Coi thêm series đại số tuyến tính của [3blue1brown](https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) để có cái nhìn trực quan hơn.
# Projects
- Sẽ có 3 project trong môn này:
	1. [[ROB101 - Map Building from LiDAR Data|Map Building from LiDAR Data]]
	2. [[ROB101 - Regression. Precipitation in Alaska|Regression: Precipitation in Alaska]]
	3. Segway
## Labs
- Mặc dù là môn toán nhưng có kèm theo các bài labs sử dụng Julia + Jupyter: [Lab Manual](https://grizzle.robotics.umich.edu/files/ROB_101_Julia_Programming_Guide_07August2025.pdf)

> [!warning] Note
> Bài này dùng để lưu các ghi chú của mình trong quá trình tự học, không phải tài liệu tin cậy để tham khảo. Mình sẽ chia các mục theo từng chương trong notebook.

# 1- Introduction to system of linear equations 
- Phương trình tuyến tính là phương trình bật 1 có dạng : $$ y = ax + b $$
- Hệ pt tuyến tính bao gồm nhiều pttt: 
$$ 
\begin{aligned}
y = a_1x + b_1 \\ 
y = a_2x + b_2  
\end{aligned}
$$
- Dựa vào số phương trình và số ẩn trong 1 hệ, nghiệm có thể :
	1. 1 nghiệm duy nhất 
	2. Vô số nghiệm 
	3. Vô nghiệm 
- Mình có thể giải tay 1 hệ có 2 hoặc 3 phương trình dễ dàng bằng phương pháp thế, ... Nhưng khi hệ có 100 pt, việc giải tay là không khả thi. Đó là lúc mình cần phải dùng sức mạnh tính toán của máy tính. Và cũng là lý do môn này có tên là ***Computational Linear Algebra***.
# 2- Vectors, Matrices and Determinants
- Không nhắc lại dài dòng về định nghĩa và ký hiệu vector và ma trận nữa.
- Ma trận vuông là ma trận có số hàng = số cột
- Định thức (determinants) của 1 ma trận có 5 ý như sau:![[Screenshot 2026-09-24 at 02.25.46.png|700]]
- Đường chéo (hay đường chéo chính) (matrix diagonal) của ma trận vuông như sau:
<div align="center">
  <img src="imgs/Screenshot 2026-09-24 at 14.46.54.png" width="400">
</div>

# 3- Triangular systems of equations: Forward and backward substitution
- Một ma trận chéo là ma trận mà tất cả các phần tử nằm ngoài đường chéo chính **bằng 0**:
<div align="center">
  <img src="imgs/Screenshot 2026-09-24 at 15.15.21.png" width="300">
</div>

- Phương pháp để tìm ra nghiệm của hệ phương trình là đưa ma trận hệ số về dạng **tam giác trên** hoặc **tam giác dưới**. Sau đó dùng phương pháp thế để tìm ra các nghiệm lần lượt. 
# 4- Matrix Multiplication
- Một trong những cách để hình dung phép nhân 2 ma trận **A x B** là xem nó như **phép biển đổi của ma trận B theo ma trận A**. 
- Xem video này của kênh [3b1b](http://youtube.com/watch?v=XkY2DOUCWMU&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=4) để dễ hiểu hơn.
- Một vài đặc trưng của phép nhân cần lưu ý:
	1. A.B != B.A (không có tính giao hoán)
	2. Kích thước của 2 ma trận phải có dạng $A_{nm} \cdot B_{mk}$
# 5- LU factorization
- Question: Cho ma trận vuông M, có cách nào tìm ra 2 ma trận sao cho $M=L \cdot U$. Trong đó, L và U lần lượt là 2 ma trận tam dưới trên và trên.
- Answer: Có cách tìm ra 2 ma trận L và U. Và việc phân tách này còn giúp mình tìm nghiệm của phương trình $A \cdot x = b$ một cách tổng quát hơn. 
- Cách giải phương trình sử dụng 2 ma trận LU:
![[Screenshot 2026-09-28 at 14.45.46.png|center]]
- Ở phần này, mình không đi chi tiết vào cách tìm 2 ma trận L và U.
# 6- Determinant of a Matrix Product, Matrix Inverses, Matrix Transposes, and Permutation Matrices
- Có 2 ma trận vuông cũng kích thước A và B, ta có : $$det(A \cdot B) = det(A) \cdot det(B)$$
- Kết hợp định lý trên với cách phân tách LU, mình có thể tính định thức của 1 ma trận kích thước bất kỳ bằng cách: $$det(A) = det(L \cdot U) = det(L) \cdot det(U)$$
- Trong đó định thức của 2 ma trận tam giác được tính dễ dàng bằng cách nhân các phần tử nằm trên đường chéo chính.
- Ma trận hoán vị P (permutation matrix) là ma trận vuông mà mỗi hàng và mỗi cột chứa đúng 1 phần tử bằng 1, các phần tử còn lại bằng 0. 
- Ma trận nghich đảo của A viết là $A^{-1}$ và để nghịch đảo được, thì $det(A) \neq 0$ .
- Sử dụng ma trận nghịch đảo, mình có thể giải 1 hệ phương trình tuyến tính bằng cách: $$x = A^{-1}b$$
- Ma trận chuyển vị của A viết là $A^T$ . Hình dung việc chuyển vị 1 ma trận là biến cột thành hàng và hàng thành cột. Có 1 vài đặc trưng sau: 
$$
\begin{gather}
(A^T)^T = A \\
det(A^T) = det(A), \text{if A is square} \\
(A \cdot B)^T= B^T \cdot A^T
\end{gather}
$$
- Nếu ma trận P là ma trận hoán vị thì 
$$
\begin{gather}
P^T \cdot P = P \cdot P^T \\
P^{-1} = P^T
\end{gather}
$$
# 7- The Vector Space Rn: Part 1
- Một điểm trong $\mathbb{R}^n$ cũng là vectors, đều là 1 danh sách có thứ tự của số. 
- Cho 1 ma trận $A_{nm}$ , các cột của nó sẽ là các vector trong $\mathbb{R}^n$. Ngược lại, cho m vector trong $\mathbb{R}^n$, có thể gộp lại thành 1 ma trận $A_{nm}$.
- Tổ hợp tuyến tính (Linear combination) là tổng các vector, trong đó mỗi vector được nhân với một hệ số vô hướng: ![[Screenshot 2026-10-05 at 09.50.20.png|250]]
-  Cho phương trình $A\alpha = b$, khi viết ngược lại sẽ thành $b=\alpha A$. Khi đó mình có thể biểu diễn b là tổ hợp tuyến tính của các cột trong ma trận A:
<div align="center">
  <img src="imgs/Screenshot 2026-10-05 at 09.46.58.png" width="350">
</div>
- Và các vector $\alpha \in \mathbb{R}^m$ là nghiệm của hệ phương trình.
- Độc lập tuyến tính (Linear Independence) và Phụ thuộc tuyến tính (Linear dependence) được hiểu như sau:
	- Cho 1 tổ hợp tuyến tính có tổng bằng 0 như sau ![[Screenshot 2026-10-06 at 10.08.18.png|250]].
	- Nếu tồn tại 1 nghiệm vector $\alpha \neq 0$ , các vector v là phụ thuộc tuyến tính
	- Nếu chỉ có duy nhất nghiệm $\alpha = 0$, các vector v gọi là độc lập tuyến tính 
- Nếu phương trình $Ax = b$ có 1 nghiệm duy nhất, thì A độc lập tuyến tính.  
- Ý nghĩa của độc lập tuyến tính:
	- 
# 8- Euclidean Norm, Least Squared Error Solutions to Linear Equations, and Linear Regression

Objective: hầu hết các bài toán kỹ thuật trong thực tế sẽ không có 1 đáp án, 1 nghiệm chính xác, nhất quán. Vì thế, mình sẽ chuyển sang tìm kết quả sao cho sai số là ít nhất.

- Chuẩn của một vector (Norm of vector) là hàm số dùng để đo kích thước, chiều dài của một vector, ký hiệu là $\|v\|$. Được tính là ![[Screenshot 2026-10-07 at 09.27.01.png|250]]
- Xét hệ tuyến tính $Ax = b$ , khi đó vector $e(x) := Ax-b$ là sai số của nghiệm $x$. Chiều dài của vector e lớn hay bé sẽ phụ thuộc vào nghiệm x. Để không phải làm việc với dấu căn bậc 2, mình đơn giản là bình phương chiều dài của vector. Khi đó, vector sai số $e(x)$ sẽ được viết:
<div align="center">
  <img src="imgs/Screenshot 2026-10-09 at 11.23.10.png" width="500">
</div>

- Như vậy, tìm nghiệm có sai số nhỏ nhất trở thành bài toán tối ưu:
<div align="center">
  <img src="imgs/Screenshot 2026-10-09 at 11.25.27.png" width="300">
</div>

- 
