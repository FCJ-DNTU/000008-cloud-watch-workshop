---
title: "CloudWatch Metric Filter"
weight: 3
chapter: false
pre: " <b> 4.3 </b> "
---

#### CloudWatch Metric Filter

1. Quay lại màn hình chính của **CloudWatch**

   - Chọn **Log groups**
   - Tìm `/ec2`.
   - Chọn **/ec2/linux/var/log/messages**

![4.3.1](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.1.png)

2. Trong giao diện của **/ec2/linux/var/log/messages**

   - Ấn xổ **Actions**.
   - Ấn **Create metric filter**.

![4.3.2](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.2.png)

3. Trong phần **Define Pattern**, điền một số thông tin như sau

   - Filter pattern: xổ xuống và chọn **ERROR**.
   - Test pattern: xổ xuống và chọn bất kì một instance nào, nhưng nên chọn instance mà chúng ta mới thực hiện việc tạo processes ở 2 bước trước.

![4.3.3](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.3.png)

4. Ấn chọn **Test pattern** để kiểm tra thử xem filter chạy ổn không.

![4.3.4](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.4.png)

5. Trong phần **Create filter name** của **Assign metric**, nhập `PythonAppErrors`.

![4.3.5](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.5.png)

6. Trong phần Metric details, nhập một số thông tin như sau:

   - Metric namespace: `ec2-logs`.
   - Metric name: `/var/log/messages - ERROR`.
   - Metric value: **1**.
   - Default value: **0**.
   - Unit: xổ xuống và chọn **Count**.
   - Ấn **Next**.

![4.3.6](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.6.png)

7. Review xong và ấn chọn **Create metric filter**.

![4.3.7](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.7.png)

![4.3.8](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.8.png)

8. Trở lại Metrics > All metrics.

   - Tìm 2 từ khoá là `/var/log/messages` và `ERROR`.
   - Chọn **ec2-logs > Metrics with no dimensions**.

![4.3.9](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.9.png)

![4.3.10](/images/4-cloud-watch-logs/4.3-metric-filter/4.3.10.png)

Như vậy là chúng ta đã có được một Metric được lấy từng những ERROR Logs trong ứng dụng. Trong bước tiếp theo thì chúng ta sẽ thiết lập Alarm cho metric này.
