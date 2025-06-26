Tổng quan dự án
Hệ thống gara xe thông minh được xây dựng với mục tiêu tự động hóa việc kiểm soát và bảo vệ khu vực để xe tại gia đình, nhà trọ hoặc khu dân cư nhỏ. Hệ thống sử dụng Raspberry Pi 4 làm trung tâm điều khiển, kết hợp với các mô hình AI hiện đại để thực hiện 3 chức năng chính:

- Nhận diện khuôn mặt: Xác thực người dùng hợp lệ để mở cửa tự động (sử dụng thư viện face_recognition với mô hình ResNet-34).

- Phát hiện người: Cảnh báo khi có người lạ xâm nhập bằng mô hình YOLOv8n đã fine-tune cho điều kiện ánh sáng yếu.

- Nhận diện giọng nói: Điều khiển thiết bị như đèn, cửa, còi bằng lệnh thoại, sử dụng mô hình nhận dạng tiếng nói VOSK.

Ngoài ra, hệ thống còn được tích hợp với các thiết bị như Arduino, động cơ servo, động cơ bước, đèn LED, buzzer và có giao diện web điều khiển từ xa qua mạng. Giải pháp có tính mở rộng cao, chi phí thấp và dễ dàng triển khai thực tế trong môi trường gia đình hoặc bán chuyên nghiệp.

