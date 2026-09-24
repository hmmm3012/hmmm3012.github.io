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
## Labs
- Mặc dù là môn toán nhưng có kèm theo các bài labs sử dụng Julia + Jupyter: [Lab Manual](https://grizzle.robotics.umich.edu/files/ROB_101_Julia_Programming_Guide_07August2025.pdf)

> [!warning] Note
> Bài này dùng để lưu các ghi chú của mình trong quá trình tự học, không phải tài liệu tin cậy để tham khảo. Mình sẽ chia các mục theo từng chương trong notebook của môn.

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
