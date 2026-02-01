# 🤖 chatbot_gemini

Một chatbot hỏi đáp đơn giản sử dụng **Google Gemini API**, được xây dựng bằng **Python**, giao diện với **Streamlit**, quản lý môi trường bằng **Anaconda Navigator**, và có thể chạy bằng **Docker**.

---

## 🚀 Tính năng

* Giao diện web đơn giản, dễ dùng với Streamlit
* Gửi câu hỏi và nhận phản hồi trực tiếp từ mô hình **Gemini 2.0 Flash**
* Dễ dàng chạy local hoặc deploy bằng Docker
* Cấu trúc project gọn nhẹ, phù hợp cho học tập và demo

---

## 🗂️ Cấu trúc project

```
chatbot_gemini/
│-- app.py              # File chính chạy Streamlit
│-- requirements.txt    # Danh sách thư viện Python
│-- Dockerfile          # Cấu hình chạy bằng Docker
│-- README.md           # Hướng dẫn sử dụng (file này)
```

---

## ⚙️ Công nghệ sử dụng

* **Python 3.10**
* **Google Gemini API** (`google-genai`)
* **Streamlit** (xây dựng UI chatbot)
* **Anaconda Navigator** (quản lý môi trường)
* **Docker** (đóng gói & triển khai)

---

## 🧪 Chạy project bằng Anaconda (Local)

### 1️⃣ Tạo môi trường Python

Mở **Anaconda Navigator** → tạo environment mới (Python 3.10), sau đó activate:

```bash
conda create -n chatbot_gemini python=3.10
conda activate chatbot_gemini
```

### 2️⃣ Cài đặt thư viện

```bash
pip install -r requirements.txt
```

> ⚠️ Lưu ý: cần cài thêm thư viện `google-genai` nếu chưa có

```bash
pip install google-genai
```

### 3️⃣ Chạy ứng dụng Streamlit

```bash
streamlit run app.py
```

Sau đó mở trình duyệt và truy cập:

```
http://localhost:8501
```

---

## 🐳 Chạy bằng Docker

### 1️⃣ Build Docker image

```bash
docker build -t chatbot_gemini .
```

### 2️⃣ Chạy container

```bash
docker run -p 8501:8501 chatbot_gemini
```

Mở trình duyệt tại:

```
http://localhost:8501
```

---

## 🔑 Cấu hình API Key (QUAN TRỌNG)

Hiện tại API key đang được **hard-code** trong `app.py`:

```python
genai_client = genai.Client(api_key="YOUR_API_KEY")
```

👉 **Khuyến nghị**: dùng biến môi trường để bảo mật:

```bash
export GEMINI_API_KEY=your_api_key
```

Và sửa code:

```python
import os
genai_client = genai.Client(api_key=os.getenv("GEMINI_API_KEY"))
```

---

✨ Nếu thấy hay thì nhớ ⭐ repo nha!
