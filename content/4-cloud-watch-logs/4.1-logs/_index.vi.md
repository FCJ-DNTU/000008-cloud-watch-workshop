---
title: "CloudWatch Logs"

weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

#### CloudWatch Logs

1. Trong trang chính của CloudWatch.

   - Phần menu bên phải, xổ **Logs** xuống.
   - Chọn **Log groups**.

![4.1.1](/images/4-cloud-watch-logs/4.1-logs/4.1.1.png)

2. Trên thành tìm kiếm, nhập `/ec2` và ấn chọn **/ec2/linux/var/log/messages**.

![4.1.2](/images/4-cloud-watch-logs/4.1-logs/4.1.2.png)

![4.1.3](/images/4-cloud-watch-logs/4.1-logs/4.1.3.png)

3. Chọn một instance bất kì để xem.

![4.1.4](/images/4-cloud-watch-logs/4.1-logs/4.1.4.png)

4. Ở đây chúng ta có thể thấy log từ instance này tạo ra, tới từ nhiều nguồn khác nhau như: dhclient, NET, ec2net, systemd...

![4.1.5](/images/4-cloud-watch-logs/4.1-logs/4.1.5.png)

5. Trở lại thông tin của group **/ec2/linux/var/log/messages**. Giờ chúng ta sẽ cài đặt thời gian huỷ event (log) này.

   - Xổ Actions.
   - Edit retention setting.

![4.1.6](/images/4-cloud-watch-logs/4.1-logs/4.1.6.png)

6. Trong **Retention setting**, chọn **1 week (7 days)** cho **Expire events after**.

![4.1.7](/images/4-cloud-watch-logs/4.1-logs/4.1.7.png)

![4.1.8](/images/4-cloud-watch-logs/4.1-logs/4.1.8.png)

Ok thì đó là một số thao tác cơ bản với Logs, bạn có thể biết được trong instance đó các log có thể là tới từ đâu, từ dịch vụ nào, từ ứng dụng nào.
