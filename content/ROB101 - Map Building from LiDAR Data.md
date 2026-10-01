---
tags:
  - course
  - projects
---
>[!info]
>Đây là project đầu tiên trong ROB101, yêu cầu đặt ra là sử dụng dữ liệu từ Lidar để xây dựng map xung quanh. Dữ liệu được thu bằng cách gắn Lidar lên đầu robot và cho nó đi xung quanh khuôn viên trường. Từ toạ độ của Lidar, vị trí của 1 vật sẽ thay đổi do robot di chuyển, mặc dù vật đó đứng yên ngoài thực tế. Vậy làm sao để dựa vào dữ liệu của Lidar và chuyển động của robot để vẽ map xung quanh ? 
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
![[Screenshot 2026-09-30 at 22.00.56.png|300]]

