---
tags:
  - course
  - projects
---
> [!info] Intro
> Đây là project thứ 2 trong ROB101, áp dụng Linear Regression vào bài toán dự đoán lượng mưa ở khu vựa Alaska dưa vào data lấy từ *National Oceanic and Atmospheric Administration (NOAA)*.

# Bài toán đặt ra
- Yêu cầu là phải vẽ được bản đồ lượng mưa ở Alaska với mật độ là 5km theo kinh độ và vĩ độ. Tất nhiên, không có trạm thời tiết để đo lượng mưa ở mọi điểm cách nhau 5 km. Thực tế, các trạm báo cáo lượng mưa nằm rải rác, không cách nhau đều, khác độ cao, ... Vì vậy, nhiệm vụ là sử dụng 1 phần dữ liệu từ các trạm thời tiết và xây 1 model để ước lượng được lượng mưa ở bất kỳ toạ độ nào ở trong Alaska.
# Monomials vs Radial basis functions
- Trong bài toán hồi quy tuyến tính (linear regression), việc chọn hàm cơ bản để ước lượng trong bài toán này rất quan trọng. Sẽ có 2 hướng, đầu tiên là sử dụng các đơn thức (Monomials), ví dụ như $x^2, x^3 ,...$  
- Nhưng khi đó model phải phụ thuộc vào hình dạng của hàm đơn thức. Ví dụ, nếu xài hàm bậc 2 có dạng $y = ax^2 + bx +c$. Khi đó, hình dáng các điểm data biết trước phải có dạng "hình cong chiếc bát" để model dự đoán tốt nhất.
<div align= "center">  
	<img src="imgs/Screenshot 2026-10-12 at 08.57.53.png" width="500">  
</div>

- Để giải quyết vấn đề trên, mình sẽ dùng dạng hàm cơ bản số 2 : Radial basis function (RBF). Phương trình RBF như sau: $$f(x; x_c, s) = exp(\frac{-|x-x_c|^2}{2s^2})$$
<div align= "center">  
<img src="imgs/Screenshot 2026-10-12 at 09.01.41.png" width="450">  
</div>

- RBF sẽ có dạng hình cong như hình trên, trong đó $x_c$ quyết định vị trí trung tâm của hàm, biến $s$ càng lớn thì độ rộng từ điểm trung tâm qua 2 bên càng lớn.
