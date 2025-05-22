# 🤖 Xây dựng Chatbot Hỗ Trợ Khách Hàng Thông Minh Ứng Dụng Generative AI (RAG + Gemini + FAISS)

## 📝 Mục tiêu dự án

Dự án nhằm xây dựng một hệ thống chatbot hỗ trợ khách hàng thông minh, kết hợp giữa mô hình ngôn ngữ tiên tiến Gemini 1.5 Flash của Google với kỹ thuật Tạo sinh tăng cường truy xuất (RAG). Hệ thống sử dụng mô hình text-embedding-004 để biểu diễn ngữ nghĩa văn bản và thư viện FAISS để truy xuất nhanh các phản hồi liên quan từ cơ sở tri thức. Từ đó, chatbot có thể tạo ra phản hồi tự nhiên, chính xác và theo ngữ cảnh phù hợp với truy vấn người dùng. Dự án hướng đến ứng dụng thực tiễn trong thương mại điện tử, giúp nâng cao trải nghiệm khách hàng, giảm tải cho bộ phận CSKH và mở rộng quy mô hỗ trợ doanh nghiệp một cách hiệu quả.
---

## 🧠 Công nghệ và thư viện sử dụng

- **Ngôn ngữ** – Python.
- **Nền tảng** – Google Colab
- **Mô hình tạo sinh mạnh mẽ** – Google Gemini 1.5 Flash.
- **Mô hình tạo embedding ngữ nghĩa chất lượng cao** – Gemini text-embedding-004
- **Thư viện truy xuất** – FAISS (Facebook AI Similarity Search)
- **Thư viện hỗ trợ** – Pandas, Numpy, Google Generative AI,JSON,Time

---

## 🔄 Quy trình xây dựng mô hình

### Bước 1: Chuẩn bị và tiền xử lý dữ liệu
- Sử dụng tập dữ liệu chatbot từ Bitext.
- Đổi tên cột `instruction` thành `prompt`.
- Loại bỏ các hàng thiếu `prompt` hoặc `response`.
- Nếu có cột `intent`, điền giá trị `"unknown"` cho các hàng bị thiếu.
- Lấy mẫu ngẫu nhiên **200 dòng** dữ liệu.

### Bước 2: Sinh embedding ngữ nghĩa
- Dùng mô hình `text-embedding-004` để biến đổi các phản hồi thành vector 768 chiều.
- Mục tiêu: Biểu diễn ngữ nghĩa để phục vụ truy xuất chính xác.

### Bước 3: Tạo chỉ mục FAISS
- Dùng thư viện FAISS để tạo chỉ mục vector cho toàn bộ cơ sở tri thức
- Cho phép truy xuất phản hồi tương đồng nhanh và hiệu quả.

### Bước 4: Truy xuất phản hồi theo truy vấn người dùng
- Nhập truy vấn từ người dùng.
- Tạo vector embedding cho truy vấn.
- Truy xuất các phản hồi gần nhất từ FAISS theo độ tương đồng cosine.

### Bước 5: Sinh phản hồi bằng Gemini 1.5 Flash
- Kết hợp truy vấn người dùng và các phản hồi được truy xuất để làm ngữ cảnh.
- Sinh phản hồi cuối cùng bằng Gemini 1.5 Flash.

### Bước 6: Hiển thị & đánh giá
- Trả phản hồi cho người dùng.
- Có thể đánh giá bằng cosine similarity với phản hồi gốc (ground truth).

---

## 📊 Kết quả & Hiệu suất

- Hệ thống có khả năng trả lời chính xác, bám sát ngữ cảnh truy vấn.
- Phản hồi được tạo tự nhiên, rõ nghĩa và sát với cơ sở dữ liệu có sẵn.
- Tốc độ phản hồi nhanh nhờ truy xuất FAISS và sinh nhanh từ Gemini Flash..

---

## ✅ Kết luận

Hệ thống RAG kết hợp Gemini và FAISS là giải pháp hiệu quả để xây dựng chatbot hỗ trợ khách hàng thông minh. Giải pháp vừa có khả năng hiểu ngữ nghĩa sâu, vừa truy xuất tri thức nhanh và sinh phản hồi tự nhiên – phù hợp triển khai trong môi trường thực tế như thương mại điện tử, dịch vụ khách hàng, giáo dục, v.v.

---
