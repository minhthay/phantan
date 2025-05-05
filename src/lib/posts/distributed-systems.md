
---
title: "Tổng quan về Hệ thống phân tán"
date: "2025-04-29"
excerpt: "Tìm hiểu khái niệm, ứng dụng, thuật ngữ và kiến trúc của hệ thống phân tán hiện đại."
---

# Hệ thống phân tán là gì?

Hệ thống phân tán (Distributed System) là một tập hợp các máy tính riêng biệt (nodes) hoạt động như một hệ thống thống nhất đối với người dùng cuối. Các node này giao tiếp với nhau thông qua mạng để phối hợp thực hiện một nhiệm vụ chung. Mục tiêu chính là cung cấp hiệu suất cao, khả năng mở rộng và độ tin cậy.

---

# Các ứng dụng của hệ thống phân tán

- Dịch vụ web (Google, Facebook, Amazon)
- Hệ thống ngân hàng, tài chính
- Ứng dụng cloud (AWS, Azure, GCP)
- Các nền tảng học trực tuyến (Coursera, edX)
- Game online đa người chơi
- Hệ thống lưu trữ tệp tin phân tán (Dropbox, Google Drive)

---

# Các khái niệm chính của hệ thống phân tán

1. **Scalability** – Khả năng mở rộng khi có thêm người dùng hoặc tài nguyên.
2. **Fault Tolerance** – Khả năng tiếp tục hoạt động khi một phần hệ thống gặp lỗi.
3. **Availability** – Mức độ mà hệ thống luôn sẵn sàng phục vụ.
4. **Transparency** – Ẩn chi tiết kỹ thuật khỏi người dùng (ví dụ: truy cập từ xa như truy cập nội bộ).
5. **Concurrency** – Hệ thống xử lý nhiều yêu cầu cùng lúc.
6. **Parallelism** – Nhiều tác vụ được xử lý song song để tăng hiệu suất.
7. **Openness** – Hệ thống dễ tích hợp, mở rộng với phần mềm khác.
8. **Vertical Scaling** – Tăng sức mạnh một node (nâng cấp CPU/RAM).
9. **Horizontal Scaling** – Thêm nhiều node mới để tăng khả năng xử lý.
10. **Load Balancer** – Phân phối lưu lượng truy cập đồng đều giữa các node.
11. **Replication** – Tạo nhiều bản sao dữ liệu để tăng độ tin cậy và hiệu suất.

---

# Ví dụ và cách các thuật ngữ liên quan

**Ví dụ:** Một hệ thống thương mại điện tử như **Shopee** hoặc **Lazada**.

- Khi bạn truy cập trang web:
  - **Load Balancer** phân phối request đến các server đang hoạt động.
  - **Replication** giúp mỗi khu vực có bản sao dữ liệu gần đó để truy cập nhanh hơn.
  - Khi một server bị lỗi, **Fault Tolerance** giúp tự động chuyển hướng sang server khác.
  - Hệ thống có thể **scale horizontally** bằng cách thêm server khi có nhiều người truy cập.
  - **Concurrency** đảm bảo hàng ngàn người mua hàng cùng lúc không bị chậm.
  - **Transparency** làm người dùng không biết họ đang kết nối đến máy chủ nào.
  - Hệ thống **available** liên tục 24/7, không gián đoạn.

---

# Kiến trúc của hệ thống phân tán

Có nhiều mô hình kiến trúc khác nhau, dưới đây là một số phổ biến nhất:

### 1. **Client-Server**
- Máy khách (client) gửi yêu cầu, máy chủ (server) xử lý và phản hồi.

### 2. **Peer-to-Peer (P2P)**
- Các node đóng vai trò ngang hàng, chia sẻ dữ liệu và tài nguyên (ví dụ: BitTorrent).

### 3. **Three-Tier Architecture**
- Tầng giao diện người dùng (UI) – Ứng dụng – Cơ sở dữ liệu.

### 4. **Microservices Architecture**
- Hệ thống chia nhỏ thành nhiều dịch vụ độc lập, giao tiếp qua API.

### 5. **Event-Driven Architecture**
- Hệ thống phản ứng theo sự kiện, thường dùng trong các hệ thống streaming (Kafka, RabbitMQ).

### 6. **Service-Oriented Architecture (SOA)**
- Tập hợp các dịch vụ cung cấp qua mạng, giao tiếp bằng các chuẩn như SOAP, XML.

### 7. **Serverless Architecture**
- Nhà phát triển chỉ viết code xử lý logic, còn hạ tầng được quản lý bởi cloud provider (ví dụ: AWS Lambda).

---

# Ví dụ

### Ví dụ: **Netflix**

Netflix là ví dụ điển hình của một hệ thống phân tán:

- **Microservices** được triển khai độc lập để xử lý đăng nhập, xem phim, gợi ý,...
- **Load Balancer** giúp hàng triệu người xem phim cùng lúc mà không lag.
- **Replication** đảm bảo video có sẵn ở nhiều khu vực trên thế giới.
- **Fault Tolerance** giúp Netflix tiếp tục hoạt động ngay cả khi một số server bị lỗi.

---


