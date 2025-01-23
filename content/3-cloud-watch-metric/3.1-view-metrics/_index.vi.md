---
title: "Xem các Metrics"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

#### Xem các Metrics

Đầu tiên, chúng ta sẽ thực hành thao tác xem các metrics.

1. Truy cập **AWS Management Console**

   - Tìm **CloudWatch**
   - Chọn **CloudWatch**

![3.1.1](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.1.png)

2. Trong giao diện **CloudWatch**

   - Xổ phần **Metrics** ở bên menu bên trái xuống.
   - Chọn **All metrics**.

![3.1.2](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.2.png)

3. Trong giao diện biểu đồ của metrics. Nhập `EC2` vào trong ô tìm kiếm và tìm.

![3.1.3](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.3.png)

4. Sau khi ra kết quả, chọn **EC2 > Pre-Instance Metrics**.

![3.1.4](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.4.png)

![3.1.5](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.5.png)

5. Trên thanh tìm kiếm, gõ `CPUUtilization` và tìm kiếm

![3.1.6](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.6.png)

Bạn có thể thấy được là khi gõ tìm kiếm, thì mặc định nó sẽ tìm theo **Metric name**.

![3.1.7](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.7.png)

6. Thêm thử 2 trong số 5 instances được tạo ra từ CloudFormation stack, để xem các thông số CPUUtilization của 2 instances này được thể hiện như thế nào (bạn nên cuộn xuống để thấy).

Ở đây thì chúng ta có thể kết luận là: cả 2 instances này bắt đầu hoạt động vào lúc khoảng 2:40, và cũng là lúc có nhiều hoạt động nhất. Sau đó đổ dần về 3:30 thì có vẻ như cả 2 instances này đã làm xong công việc của nó.

![3.1.8](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.8.png)

7. Tiếp theo là chúng ta sẽ thực hiện việc xem các metrics khác của cùng một Instance.

   - Tích bỏ đi dòng của Instance B.
   - Xoá tag tìm kiếm **CPUUtilization**.
   - Trên thanh tìm kiếm, nhập `EBSWriteBytes` và tìm kiếm.

![3.1.9](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.9.png)

![3.1.10](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.10.png)

8. Kéo xuống và tích chọn Instance A

Ở biểu đồ này thì chúng ta cũng thấy một điều tương tự, vào khoảng thời gian đầu mà instance này thực hiện công việc, thì lượng đọc ghi vào EBS rất nhiều, hầu như là CPUUtilization & EBSWriteBytes trùng với nhau (có thời điểm là không trùng). Từ đây thì mình có thể thấy được là ứng dụng của chúng ta cần thao tác với EBS khi khởi động, nhưng ở đoạn trùng thì không cần thao tác với EBS **do nó đang thực hiện một thao tác nào đó khác**.

![3.1.11](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.11.png)

Bạn có thể ẩn một trong 2 đi để xem kỹ hơn.

![3.1.12](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.12.png)

Nhưng chúng ta sẽ không phải làm như thế này. Ở bước tiếp theo chúng ta sẽ đi thao tác với các biểu đồ này để có được cái nhìn trực quan hơn.

#### Thao tác với biểu đồ

Ở bước trước thì biểu đồ của chúng ta khó có thể nhìn được vì cả 2 đơn vị của CPUUtilization và EBSWriteBytes đang ở trên cùng tục tung (Oy), nên trong phần này chúng ta sẽ tách nó ra và thêm một số "dấu" để việc quan sát biểu độ dễ dàng hơn.

1. Vào trong tab **Graphed metrics**, ở dòng **EBSWriteBytes**, cột **Y axis**, chọn **>**. Có thể thấy biểu đồ của chúng ta trông đã khác hơn vừa rồi.

![3.1.13](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.13.png)

2. Tiếp theo, chúng ta sẽ thêm "mark" cho biểu đồ.

   - Vào trong tab **Options**.
   - Ấn chọn **Add horizontal annotation**.

![3.1.14](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.14.png)

3. Nhập một số thông tin cho horizontal annotation như sau:

   - Label: **5% Mark**.
   - Value: **5**.

Và bạn có thể thấy một đường kẻ nét đứt hiện trên biểu đồ, có nhãn.

![3.1.15](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.15.png)

4. Tạo thêm Vertical annotation với label là `Job start`. Và chúng ta sẽ thấy thêm một đường kẻ dọc, nét đứt hiện trên biểu đồ.

![3.1.16](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.16.png)

Nhưng Job start không phải là ở thời điểm 2:16 như mặc định đã tạo. Nên chúng ta cần sẽ phải chỉnh sửa lại thông số này.

5. Chỉnh lại Date cho vertical annotation.

   - Di trỏ chuột vào trong phần đầu của đường chỉ trên biểu đồ.
   - Ở đây thì chúng ta có thể thấy nó Job được bắt đầu vào khoảng **02:40**.

![3.1.17](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.17.png)

- Sửa lại thông tin giờ của Date của Job start thành **02:40**.
- Ấn chọn **Apply** để thay đổi.

![3.1.18](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.18.png)

Đường Job start đã thay đổi vị trí.

![3.1.19](/images/3-cloud-watch-metric/3.1-view-metrics/3.1.19.png)

Ok, thì đó là những gì mà chúng ta thực hiện thao tác trên biểu đồ. Trong phần sau, chúng ta sẽ thao tác chủ yếu với các biểu thức và bạn cũng có thể xoá 2 đường dấu này đi để sang bước tiếp theo.
