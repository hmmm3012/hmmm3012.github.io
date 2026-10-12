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
- Nhưng khi đó model phải phụ thuộc vào hình dạng của các đơ