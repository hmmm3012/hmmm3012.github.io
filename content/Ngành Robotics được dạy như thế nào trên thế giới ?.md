---
title: Ngành Robotics được dạy như thế nào trên thế giới ?
tags:
  - blogs
---
> [!info] Trong quá trình tìm hiểu và tự học robotics, mình tham khảo khá nhiều các khoá học và chương trình giảng dạy khác nhau từ những trường đại học top đầu về Robotics. Bài này chia sẽ 1 vài đúc kết của cá nhân mình, sẽ có ích cho những ai đang muốn xây roadmap tự học robotics.

>[!note] Mình tham khảo rất nhiều về chương trình dạy của đại học Michigan vì họ công khai danh sách môn và thậm chí là tài liệu, clip giảng dạy của 1 vài môn. Ngoài ra, Michigan cũng có 1 khoa riêng cho Robotics, nên nội dung đào tạo và yêu cầu đầu ra rất sát với ngành. Các lập luận dưới đây hoàn toàn dựa trên sự tìm hiểu và ý kiến cá nhân. Sẽ cập nhật liên tục nếu có thay đổi sau này.
# Điểm chung
Đa số các trường hiện tại vẫn xem Robotics là 1 ngách từ các ngành máy tính khác như Computer Science, Computer Engineering, Mechanical Engineering, Electrical Engineering. Riêng một số trường như CMU, U-M, có khoa riêng (department) cho ngành robotics. Nhìn chung, họ xem robotics là tổ hợp của nhiều ngành riêng lẻ và sẽ trang bị cho sinh viên các nhóm kiến thức sau:
1. **Toán học**
2. **Vật lý**
3. **Khoa học/kỹ thuật máy tính**
4. **Robotics** 
# Các trường kỳ vọng sinh viên phải có nền tảng gì ?
1. **Phải có nền toán khá rộng**
- Mức độ sâu rộng mỗi trường mỗi khác, nhưng tất cả đều dạy 3 phần sau: Đại số tuyến tính, Giải tích, Xác suất thống kê. Bài toán robot cần phải giải quyết thường hoạt động trong môi trường thực tế, kết hợp nhiều sensor và actuator. Đó là lúc các khái niệm toán học xuất hiện
	- Đại số tuyến tính: đại diện trạng thái, phép biến đổi, hệ toạ độ, ...
	- Giải tích: biểu diễn các phương trình chuyển động
	- Xác suất: ước lượng độ chính xác trạng thái của robot, dự đoán, ...
- Ngoài ra, để nghiên cứu sâu hơn về điều khiển hoặc mô hình động học. Sinh viên phải học thêm toán nâng cao hơn như toán tối ưu và phương trình vi phân.
2. **Phải có kiến thức về khoa học máy tính**
- Việc biết lập trình C/C++ hoặc Python gần như là bắt buộc với sinh viên ngành này. Ngoài ra, các khái niệm về hệ điều hành, kiến trúc máy tính và thiết kế thuật toán cũng nằm trong yêu cầu đầu ra của các trường. Hiện tại, sinh viên có thể dùng AI agent để hỗ trợ coding khá nhiều. Nhưng trong quá trình học tập, việc code "chay" sẽ giúp mình chủ động gợi nhớ và có phản xạ tư duy tốt hơn trong lập trình. 
3. **Phải có kiến thức vật lý**
- Sinh viên không cần phải học sâu quá nhiều về lý thuyết vật lý như chuyên ngành chính. Nhưng phải nắm được các kiến thức cơ bản liên quan đến cơ học, cụ thể là động lực học. Ngoài ra, một số hiểu biết nhất định về lý thuyết điện tử cũng rất có ích để làm việc với cảm biến, mạch điện, ...
4. **Phải nắm được các kiến thức trọng tâm của robot**
- Phần này sẽ kết hợp các kiến thức lõi của 3 lĩnh vực trên và áp dụng vào hệ thống robot. Sinh viên phải biết cách mô hình hoá động lực học của robot và dựa vào đó để thiết kế bộ điều khiển.
Ngoài ra, sinh viên cũng cần biết thêm cách ước lượng trạng thái hiện tại của robot và cách robot "hiểu" về môi trường xung quanh của mình. Hiện tại có rất nhiều hướng nghiên cứu khác nhau khi đi sâu vào từng kiến thức cốt lõi này.
# Các ngách nghiên cứu
Đây là phần mà mỗi trường sẽ đánh theo điểm mạnh của mình, phần lớn phụ thuộc vào năng lực các giáo sư và phòng lab. Mình tham khảo các hướng tập trung được trường U-M công khai như sau:
- Perception & Reasoning
- Dynamics & Control
- Hardware & Sensors
- Human-Robot Interaction
- Full Stack Robotics
Ngược lại, các trường khác đa số sẽ cho sinh viên học các môn tự chọn. Ví dụ sinh viên CS/CE, ME có thể chọn học thêm các môn liên quan đến robotics như Feedback Control Systems, Robot Kinematics and Dynamics, ...
Hoạt động của các lab ở những trường top cũng rất đa dạng, nghiên cứu nhiều lĩnh vực và ứng dụng trong thực tế. Ví dụ như autonomous vehicles, manufacturing, medicals, rehabilitation và multi-robot systems. Mỗi lab đều có website chính thức và nêu khá đầy đủ về hoạt động của mình. 
# Tự xây roadmap cho bản thân
Sau khi tìm hiểu curriculum của nhiều trường đại học, mình sẽ hình dung được bức tranh tổng thể và tự build lộ trình học cho chính bản thân.
1. Nền tảng
- Như đã đề cập ở phần trước, để đi xa trong lĩnh vực này, không thể nào phớt lờ toán học được. Vì vậy, ít nhất mình phải học và hiểu được các concept trong 3 môn: giải tích, đại số tuyến tính và xác suất. Về khoá học thì có thể tham khảo series 18.0* của MIT được public trên OCW.
- Vì bản thân là sinh viên ngành kỹ thuật máy tính, nên mình được trang bị sẵn các kiến thức về lập trình, kiến trúc máy tính, giải thuật và hệ thống nhúng. Nhưng nếu phải tự học, mình sẽ chọn học Python thay vì C/C++. Python sẽ dễ học hơn cho người mới và dễ ứng dụng vào các môn học sau này của Robotics.
- Sau khi có nền toán và biết lập trình, việc bắt đầu học các kiến thức core trong robotics sẽ dễ dàng hơn. Mình sẽ học các phương pháp ước lượng trạng thái (vd: Kalman filter), lý thuyết điều khiển (PID, MCP), SLAM và trajectory planning. 
2. Chuyên sâu
- Sau khi đã nắm vững được các kiến thức nền tảng, việc chọn ngách để nghiên cứu sâu hơn hoàn toàn phụ thuộc vào năng lực và sở thích của mỗi người. 
## Vấn đề về phần cứng ?
Một trong những khó khăn trong lúc tự học robotics là tài nguyên phần cứng. Sẽ rất khó để làm labs yêu cầu phần cứng của các khoá online. Để tự xây dựng lại mô hình phần cứng y hệt sẽ rất tốn kém và mất thời gian. Giải pháp tạm thời là chỉ đọc yêu cầu của labs để hiểu vấn đề cần giải quyết và lý thuyết cần áp dụng. Sau đó tìm bài toán tương tự có thể mô phỏng dùng Gazebo hoặc Mujoco và giải quyết. 
Tất nhiên, việc chỉ phụ thuộc vào simulation sẽ không giúp mình học được quá trình gỡ lỗi trên phần cứng. Đặc biệt là các vấn đề liên quan đến sensor và actuator.
# Việt Nam hiện tại dạy gì ?

???

Sẽ cập nhật tiếp

