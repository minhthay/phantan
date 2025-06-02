---
title: "Buổi 2 - Tiến trình và luồng"
date: "2025-12-5"
updated: "2025-12-5"
categories:
  - "sveltekit"
  - "markdown"
coverWidth: 16
coverHeight: 9
excerpt: Check out how heading links work with this starter in this post.
---

# Báo cáo: Tiến trình & Luồng – Hệ Phân Tán

## Câu 1: Kiểm tra cấu hình máy tính và giải thích hiệu năng

**Cấu hình máy cá nhân:**

- **CPU**: AMD Ryzen 5 5500U – 6 nhân, 12 luồng
- **RAM**: 8GB DDR4
- **GPU**: NVIDIA GeForce GTX 1650, 4GB VRAM

**Phân tích hiệu năng:**

- **CPU 6C/12T** hỗ trợ xử lý song song nhiều tiến trình (multi-process) hoặc đa luồng (multi-thread), thích hợp cho lập trình, xử lý dữ liệu, làm việc với máy ảo.
- **8GB RAM** đủ để thực hiện các tác vụ thông thường (code, duyệt web, học online). Tuy nhiên, sẽ bị giới hạn khi xử lý dữ liệu lớn hoặc chạy nhiều container/docker.
- **GPU GTX 1650 4GB** giúp xử lý đồ họa, hỗ trợ các thư viện tính toán song song như CUDA, thích hợp cho học AI cơ bản, dựng phim hoặc chơi game.

---

## Câu 2: Liệt kê 12 bài toán phổ biến có sử dụng đa luồng/đa tiến trình

| STT | Bài toán | Mô tả | Dùng đa tiến trình/đa luồng |
|-----|----------|-------|------------------------------|
| 1 | Web Server | Xử lý nhiều request người dùng | Đa luồng (Thread-per-request) |
| 2 | Tìm kiếm trong dữ liệu lớn | Chia nhỏ file, xử lý song song | Đa tiến trình |
| 3 | Crawl dữ liệu từ web | Mỗi domain 1 tiến trình | Đa tiến trình |
| 4 | Game 3D | Luồng cho hình ảnh, âm thanh, logic game | Đa luồng |
| 5 | Dự đoán dữ liệu AI | Training theo batch song song | Đa tiến trình |
| 6 | Render video | Chia frame xử lý từng phần | Đa tiến trình |
| 7 | IDE biên dịch code | Tách luồng giao diện, logic, biên dịch | Đa luồng |
| 8 | Chat server | Mỗi kết nối là một thread | Đa luồng |
| 9 | Nén và giải nén dữ liệu | Xử lý từng phần dữ liệu song song | Đa tiến trình |
| 10 | Kiểm tra bảo mật website | Tạo nhiều tiến trình kiểm tra song song | Đa tiến trình |
| 11 | App học tiếng Anh | Giao diện, phát âm, bài tập chia luồng | Đa luồng |
| 12 | Simulate hệ thống phân tán | Mỗi nút ảo là 1 process | Đa tiến trình |

---

## Câu 3: Bảng phân biệt khi dùng Thread / Process / Cả hai


| Tình huống                           | Nên dùng Thread | Nên dùng Process | Ví dụ cụ thể |
|-------------------------------------|------------------|------------------|----------------|
| Nhiều tác vụ nhẹ, chia sẻ bộ nhớ    | ✅               | ❌               | App máy tính đơn giản |
| Tác vụ nặng, tách biệt tài nguyên   | ❌               | ✅               | Training mô hình AI |
| Giao tiếp mạng real-time            | ✅               | ❌               | Chat App |
| Xử lý dữ liệu song song             | ❌               | ✅               | Phân tích file log lớn |
| Hệ thống microservices              | ❌               | ✅               | Website lớn |
| Render video + UI song song         | ✅               | ✅               | App dựng phim |
| Web server xử lý nhiều user         | ✅               | ❌               | Flask API Server |

---

## 🔍 Câu 4: ChatGPT được huấn luyện bằng hệ phân tán như thế nào?

**ChatGPT (và các mô hình GPT lớn)** được huấn luyện trên các siêu máy tính với hàng ngàn GPU kết nối trong mô hình hệ thống phân tán.

- Sử dụng **data parallelism** (chia tập dữ liệu cho nhiều máy) và **model parallelism** (chia nhỏ mô hình lớn để huấn luyện song song).
- Các thư viện chính: **DeepSpeed**, **Megatron-LM**, **PyTorch Distributed**, **NCCL**.
- **Hạ tầng**: GPU NVIDIA A100, hạ tầng Azure AI của Microsoft.
- Mỗi node xử lý một phần công việc, dùng **message passing** để trao đổi giữa các thiết bị (giống như MPI/OpenMPI).

🔗 **Nguồn tham khảo:**
- [https://openai.com/research/scaling-laws](https://openai.com/research/scaling-laws)
- [https://www.microsoft.com/en-us/research/blog/building-ai-supercomputers/](https://www.microsoft.com/en-us/research/blog/building-ai-supercomputers/)
- [https://developer.nvidia.com/megatron-lm](https://developer.nvidia.com/megatron-lm)