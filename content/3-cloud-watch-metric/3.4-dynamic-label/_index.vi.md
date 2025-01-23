---
title: "Tạo dynamic labels"
weight: 4
chapter: false
pre: " <b> 3.4. </b> "
---

#### Dynamic Labels

Từ đầu tới giờ thì các bạn có thể thấy là nhãn trong phần chú thích của biểu đồ (Legend) chưa lần nào được cập nhật. Chúng ta có thể chỉnh sửa nó thủ công, tuy nhiên việc chỉnh sửa trên nhiều Metrics không phải là một ý hay. Nên trong phần này, chúng ta sẽ thao tác cơ bản cách đổi nhãn tự động mà không cần phải tự tay thay đổi.

1. Xoá các biểu thức cũ trong phần trước.

![3.4.1](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.1.png)

2. Xoá hết các **Filers** và ấn vào **All** để trở phần phần namespaces.

![3.4.2](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.2.png)

3. Sau đó là vào trong namespace **CWAgent**.

![3.4.3](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.3.png)

4. Chọn tiếp Dimension là **ImageId, InstanceId, InstanceType, exe, process_name**.

![3.4.4](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.4.png)

![3.4.5](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.5.png)

5. Trên thanh tìm kiếm, chúng ta nhập 2 thông tin sau.

   - `exe=cloudwatch`
   - `MetricName=procstat_memory_rss` (trong phần này thì chúng ta chỉ rõ là cần Metric name).

![3.4.6](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.6.png)

1. Tiếp tục ấn vào **Graph search** để hiển thị biểu đồ.

![3.4.7](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.7.png)

7. Sang tab **Graphed metrics**.

   - Xổ **Add dynamic label**.
   - Xổ **All labels**.
   - Chọn **PROP('Dim.DimName')**.

![3.4.8](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.8.png)

Chúng ta có thể thấy là Label trên biểu đồ đã thay đổi.

![3.4.9](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.9.png)

8. Sửa lại biểu thức của label theo dạng.

```
${PROP('Dim.exe')} - ${PROP('Dim.InstanceId')} - ${PROP('MetricName')}
```

![3.4.10](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.10.png)

Label đã chuyển về thành các phần như sau.

![3.4.11](/images/3-cloud-watch-metric/3.4-dynamic-label/3.4.11.png)
