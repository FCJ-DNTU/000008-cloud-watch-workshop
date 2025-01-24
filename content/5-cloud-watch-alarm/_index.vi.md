---
title: "CloudWatch Alarms"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

#### CloudWatch Alarms

Trong phần này chúng ta sẽ setup Alarm cho Error Log Metric mà chúng ta đã tạo từ phần trước.

1. Trở lại màn hình chính của CloudWatch.

   - Chọn **Alarms** ở menu bên trái.
   - Chọn **All alarms**.
   - Ấn chọn **Create alarm**.

![5.1](/images/5-cloud-watch-alarm/5.1.png)

2. Chọn **Select metric**.

![5.2](/images/5-cloud-watch-alarm/5.2.png)

Cửa sổ metrics hiện lên, trong **Custom namespaces**, chọn **ec2-logs**.

![5.3](/images/5-cloud-watch-alarm/5.3.png)

Chọn tiếp **Metrics with no dimensions**, chọn **/var/log/messages** và ấn chọn **Select metric**.

![5.4](/images/5-cloud-watch-alarm/5.4.png)

3. Trong phần **Specify metric and conditions**, chọn **Period** là **1 minutes**.

![5.5](/images/5-cloud-watch-alarm/5.5.png)

4. Trong phần **Conditions**

   - Threshold type: **Static**.
   - Điều kiện: **Greater** than **10**.

![5.6](/images/5-cloud-watch-alarm/5.6.png)

Bạn sẽ thấy một đường nét đứt ngang, chỉ ra rằng đây chính là ngưỡng mà **Alarm** sẽ được kích hoạt => khi có quá nhiều lỗi thì đã xảy ra việc gì đó bất trường trong ứng dụng, cần phải được kiếm tra ngay.

![5.7](/images/5-cloud-watch-alarm/5.7.png)

Sau đó là ấn **Next** để tiếp tục.

5. Giờ thì chúng ta cấu hình thông báo như sau

   - Alarm state trigger: **In alarm**.
   - Chọn **Create new topic**.
   - Tên topic là: `Error_logs_reach_10`.
   - Email thông báo tới: bạn sẽ nhập email của bạn vào, ở đây mình sẽ nhập của mình.
   - Ấn **Create topic**.

![5.8](/images/5-cloud-watch-alarm/5.8.png)

![5.9](/images/5-cloud-watch-alarm/5.9.png)

Ấn chọn **Next**.

![5.10](/images/5-cloud-watch-alarm/5.10.png)

6. Ở bước cuối, nhập tên alarm là `PythonApplicationErrorAlarm` và ấn chọn **Next**.

![5.11](/images/5-cloud-watch-alarm/5.11.png)

7. Xem lại kết quả và ấn chọn **Create alarm**.

![5.12](/images/5-cloud-watch-alarm/5.12.png)

![5.13](/images/5-cloud-watch-alarm/5.13.png)

Kết quả

![5.14](/images/5-cloud-watch-alarm/5.14.png)

8. Đăng nhập vào Gmail hoặc bất kì trang email nào mà bạn dùng. Bạn sẽ thấy một email được gửi tới từ **AWS Notification**.

![5.15](/images/5-cloud-watch-alarm/5.15.png)

Ấn chọn **Confirm subscription**.

![5.16](/images/5-cloud-watch-alarm/5.16.png)

![5.17](/images/5-cloud-watch-alarm/5.17.png)

Ok, như vậy thì chúng ta đã setup Alarm xong.
