---
tags:
  - blogs
  - robotics
  - projects
---
>[!info]
> Nói nhảm về quá trình làm project định vị và điều khiển robot 4 chân "Puppy Pi".
# Behind the scene
- Có thể coi đây là dự án đầu tiên của mình làm về robotics. Mình từng làm 1 vài dự án sinh viên trên hệ thống nhúng, nên điểm lợi là đã đụng đến sensor, máy tính nhúng, động cơ, ... Tuy nhiên, đây là lần đầu mình tìm hiểu về khái niệm như *State Estimation*, *Control Theory*, *Kinematics & Dynamics*, ... Và cũng nhờ dịp này mà mình ôn và học lại toán khá nhiều. Hầu như tất cả các thành phần trong hệ thống robotics đều có ứng dụng của toán.
# Robot 4 chân này làm gì ?
- Mục tiêu của mình rất đơn giản, đặt robot vào 1 môi trường biết trước, chọn toạ độ bất kỳ trên map và robot sẽ di chuyển đến vị trí đó.
# Về phần cứng
- Robot 4 chân mình dùng là bộ kit PuppyPi của HiWonder:
<div align="center">
  <img src="imgs/Pasted image 20261007162601.png" width="350">
</div>

- Robot có các thành phần chính như sau:
	- Raspberry Pi 4 làm bo xử lý.
	- Bo mạch mở rộng dùng để điều khiển Servo, đọc IMU, ...
	- 8 DOF, sử dụng servo
	- Camera ở phía trước đầu
	- Có thể gắn thêm cánh tay, Lidar, ...
- Về định vị trong map, mình sử dụng bộ UltraWideBand DWN 1000.
# Làm sao giờ ?
- Initial thought: đầu tiên, robot phải biết nó đang ở đâu trên bản đồ. Trong robotics, phần này gọi là State Estimation. Khi biết vị trí hiện tại và điểm cần đến, robot lập con đường để đi tới đó (Trajectory Planning). Khi biết con đường cần để đi, robot được điều khiển để tới đích.
- Mình sẽ làm mọi thứ có thể trên mô phỏng trước, sau đó mới deploy trên robot thực tế. 