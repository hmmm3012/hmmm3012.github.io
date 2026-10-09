---
tags:
  - course
  - projects
---
>[!info]
>Đây là project đầu tiên trong ROB101, yêu cầu đặt ra là sử dụng dữ liệu từ Lidar để xây dựng map xung quanh. Dữ liệu được thu bằng cách gắn Lidar lên đầu robot và cho nó đi xung quanh khuôn viên trường. Từ toạ độ của Lidar, vị trí của 1 vật sẽ thay đổi do robot di chuyển, mặc dù vật đó đứng yên ngoài thực tế. Vậy làm sao để dựa vào dữ liệu của Lidar và chuyển động của robot để vẽ map xung quanh ? 

Project chỉ tập trung vào việc biến đổi sử dụng các phép nhân ma trận. Vì vậy dữ liệu được cung cấp đã có sẵn góc quay và độ dời của robot theo thời gian. Mình không cần quan tâm cách tính các dữ liệu này (thực tế dùng EKF và data của IMU để estimate).
# Matrix multiplications as linear transformation
- Phép nhân 1 ma trận với 1 vector: $A \cdot v$ có thể được hình dung là phép biến đổi tuyến tính của vector v theo ma trận A.
- Một vài phép biến đổi thường gặp:
	1. Scaling
	2. Reflection
	3. Projection
	4. Shear
	5. Rotation
- Phép dời (translation) không phải là 1 biến đổi tuyến tính, vì điểm gốc toạ độ O đã bị thay đổi.
- Khi kết hợp phép dời và biến đổi tuyến tính, gọi là **affine transformation**. Được viết dưới phương trình $y= Ax+t$. Trong đó, A là ma trận biến đổi và t là vector dời. 
- Khi thực hiện phép biến đổi affine mà "vật thể" không bị cắt, làm méo, ... vẫn giữa nguyên hình dạng. Được gọi là **rigid body transformation**.
- **Ma trận xoay trong toạ độ 2D**: 
<div align="center">
  <img src="imgs/Screenshot 2026-09-30 at 22.00.56.png" width="300">
</div>

- Mỗi 1 phép biến đổi có 1 format khác nhau, có cách nào đưa cả 3 phép biến đổi: xoay, tịnh tiến và scale về cùng 1 dạng không ? Có 1 trick, gọi là : *homogeneous coordinates* (tạm dịch: hệ toạ độ đồng nhất)
	- Đầu tiên, mình đưa vector về hệ động nhất bằng cách thêm hàng bằng 1 $$\begin{bmatrix} x \\ y \end{bmatrix} \xrightarrow{} \begin{bmatrix} x \\ y \\ 1 \end{bmatrix}$$
	- Trong hệ toạ độ này, phép tịnh tiến có thể dùng phép nhân thay vì cộng, ma trận tịnh tiến có dạng sau: $$T = \begin{bmatrix} 1 & 0 & T_x \\ 0 & 1 & T_y \\ 0 & 0 & 1 \end{bmatrix}$$
	- Tương tự, ma trận xoay trong hệ đồng nhất có dạng: $$R = \begin{bmatrix} cos(\theta) & -sin(\theta) & 0 \\ sin(\theta) & cos(\theta) & 0 \\ 0 & 0 & 1 \end{bmatrix}$$
	- Cuối cùng, ma trận để scale có dạng: $$S = \begin{bmatrix} S_x & 0 & 0 \\ 0 & S_y & 0 \\ 0 & 0 & 1 \end{bmatrix}$$
# Thực hành 
- Sử dụng các ma trận biến đổi trên để biến ô vuông xanh lá sang các ô còn lại
<div style="display: flex; align-items: center; justify-content: center; gap: 15px;">
  <img src="imgs/Screenshot 2026-10-09 at 10.42.26.png" width="300">
  <span style="font-size: 30px; font-weight: bold;">➔</span>
  <img src="imgs/Screenshot 2026-10-09 at 10.34.37.png" width="300">
</div>

- Áp dụng vào chỉnh ảnh, sử dụng phép nhân ma trận để biến đổi ảnh ở dưới
<div style="display: flex; align-items: center; justify-content: center; gap: 15px;">
  <img src="imgs/Screenshot 2026-10-09 at 10.36.02.png" width="300">
  <span style="font-size: 30px; font-weight: bold;">➔</span>
  <img src="imgs/Screenshot 2026-10-09 at 10.38.05.png" width="300">
</div>

- Dữ liệu từ Lidar khi chưa được biến đổi về global frame sẽ có dạng như này: 
<div style="display: flex; align-items: center; justify-content: center; gap: 15px;">  
<img src="Screenshot 2026-10-09 at 10.45.34.png " width="300">  
</div>
- Sau khi kết hợp với dữ liệu về rotation và translation của robot, mình biến đổi dữ liệu của Lidar về như sau: (mũi tên trắng là vị trí và hướng của robot)
<div style="display: flex; align-items: center; justify-content: center; gap: 15px;">  
<img src="Screenshot 2026-10-09 at 10.57.19.png " width="350">  
</div>

- Kết quả cuối cùng là robot di chuyển (điểm trắng), nhưng bản đồ vẫn cố định và được update theo thời gian.

![/Users/hmmmm/Documents/Learning/rob101/Fall 2022 & Winter 2023/Projects/Project01/stairs_walking_five_seconds_zoomed_thirty.gif](file:///Users/hmmmm/Documents/Learning/rob101/Fall%202022%20%26%20Winter%202023/Projects/Project01/stairs_walking_five_seconds_zoomed_thirty.gif)
