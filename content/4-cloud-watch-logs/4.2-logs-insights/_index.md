---
title: "CloudWatch Logs Insights"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2 </b> "
---

### CloudWatch Logs Insights

Trong phần này, chúng ta sẽ tạo log từ một ứng dụng và sau đó truy vấn các log này trong **CloudWatch Logs Insights**. Mình sẽ chọn một **EC2 instance** làm mẫu.

1. Trên thanh tìm kiếm dịch vụ:

   - Nhập `EC2`.
   - Chọn **EC2**.

![4.2.1](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.1.png)

2. Trong **EC2 Console**, truy cập vào trang **Instances**:

   - Chọn một instance bất kỳ (ở đây mình chọn `Instance-A`).
   - Ấn chọn **Connect**.

![4.2.2](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.2.png)

3. Trong trang **Connect to instance**:

   - Chuyển sang tab **Session Manager**.
   - Nhấn **Connect**.

![4.2.3](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.3.png)

4. Đợi một lúc, một **Terminal** sẽ hiện lên:

   - Di chuyển vào thư mục `/tmp`.
   - Tải xuống script Python từ S3 bucket.

```bash
cd /tmp
sudo aws s3 cp s3://workshop-template-bucket/logger.py .
```

![4.2.4](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.4.png)

5. Cấp quyền thực thi và chạy script:

```bash
sudo chmod +x logger.py
python3 logger.py &
```

![4.2.5](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.5.png)

6. Kiểm tra các logger đang chạy dưới dạng process:

```bash
ps -aux | grep logger
```

Hiện tại có 2 process đang chạy, chúng sẽ chạy cho đến khi kết thúc bài thực hành.

![4.2.6](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.6.png)

7. In ra các dòng log từ file `/var/log/messages`, nó sẽ chạy liên tục cho đến khi bị hủy:

```bash
sudo tail -f /var/log/messages
```

![4.2.7](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.7.png)

8. Trở lại **CloudWatch Console**, vào **Logs Insights** từ menu bên trái để truy vấn log.

![4.2.8](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.8.png)

9. Trong **Selection criteria**, tìm `/ec2` và chọn **/ec2/linux/var/log/messages**.

![4.2.9](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.9.png)

10. Nhập câu truy vấn sau và nhấn **Run query**:

```
fields @timestamp, @message
| sort @timestamp desc
| limit 20
```

Kết quả hiển thị như sau:

![4.2.10](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.10.png)

Đây chính là các log chúng ta vừa tạo.

![4.2.11](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.11.png)

11. Truy vấn log có chứa **ERROR**:

```
fields @timestamp, @message
| filter @message like /ERROR/
| sort @timestamp desc
| limit 20
```

![4.2.12](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.12.png)

Đây là các log lỗi mà chúng ta đã tạo.

![4.2.13](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.13.png)

12. Truy vấn log có chứa **WARN**:

```
fields @timestamp, @message
| filter @message like /WARN/
| sort @timestamp desc
| limit 20
```

![4.2.14](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.14.png)

13. Truy vấn lại log lỗi để xem log mới tạo:

![4.2.15](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.15.png)

14. Truy vấn theo từ khóa khác (`eth0`):

```
fields @timestamp, @message
| filter @message like /eth0/
| sort @timestamp desc
| stats count (*) by bin()
```

![4.2.16](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.16.png)

![4.2.17](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.17.png)

### Trực quan hóa truy vấn log

Chúng ta có thể xem biểu đồ của các truy vấn bằng cách chuyển sang tab **Visualization**.

![4.2.18](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.18.png)

### Lưu lệnh truy vấn

Logs Insights hỗ trợ lưu truy vấn để sử dụng lại sau này.

1. Ví dụ, lưu truy vấn **ERROR logs**:

   - Quay lại Logs Insights.
   - Nhập lại truy vấn **ERROR logs**.
   - Nhấn **Save**.

![4.2.19](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.19.png)

2. Trong **Save a new query**, điền thông tin:

   - **Query name**: `Errors`
   - **Folder**: `cloudwatch-workshop` (chọn **Create new**)
   - Kiểm tra lại thông tin trong **Query definition details**.
   - Nhấn **Save**.

![4.2.20](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.20.png)

![4.2.21](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.21.png)

### Lịch sử truy vấn

Logs Insights cho phép xem lại lịch sử truy vấn. Trong giao diện, chọn **History** (dưới Query editor).

![4.2.22](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.22.png)

![4.2.23](/images/4-cloud-watch-logs/4.2-logs-insights/4.2.23.png)

Trong phần tiếp theo, chúng ta sẽ tạo **Metrics Filter**, chuyển log thành **Metric**, và thiết lập **Alarm**.
