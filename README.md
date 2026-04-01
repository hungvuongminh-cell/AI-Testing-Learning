# 🚀 AI Testing & Evaluation Pipeline (Hệ thống Kiểm thử & Đánh giá AI)

Dòng thời gian nghiên cứu và xây dựng hệ thống kiểm thử tự động cho các mô hình ngôn ngữ lớn (LLM) từ kết nối cơ bản đến quản trị dữ liệu tập trung.

---

## 🇻🇳 Tiếng Việt

### 📌 Project 0001: Kết nối API Gemini (New SDK)
**Mục tiêu:** Thiết lập nền tảng kết nối với Google GenAI SDK để thực thi các câu hỏi kiểm tra kiến thức thực tế.
* **Kỹ thuật:** Sử dụng `google.genai` bản mới, truy xuất API Key qua `userdata.get('key')`.
* **Điểm nổi bật:** Cơ chế `time.sleep(10)` để tôn trọng hạn mức (quota) của tầng miễn phí.
* **Kết quả:** Thực thi thành công các câu hỏi về địa lý, toán học và văn hóa với model `gemini-2.5-flash`.

### 📌 Project 0002: Đánh giá suy luận logic đa mô hình (Multi-LLM)
**Mục tiêu:** Benchmark khả năng logic và tuân thủ chỉ dẫn của các model trên nền tảng Groq Cloud.
* **Kỹ thuật:** Sử dụng **Structured Prompting** (Role, Task, Context, Constraints) và LangChain `ChatGroq`.
* **Điểm nổi bật:** Thiết lập `MODEL_INDEX` để chuyển đổi linh hoạt giữa 5 model: Llama 3.3, Llama 3.1, Gemma 2, Mixtral và DeepSeek-R1.
* **Kết quả:** Phân tích tính logic của các bài toán kinh tế và sức khỏe với độ chính xác cao nhờ `temperature=0.1`.

### 📌 Project 0003: Khung đánh giá AI-as-a-Judge
**Mục tiêu:** Tự động hóa việc chấm điểm chất lượng phản hồi bằng cách sử dụng một AI "Giám khảo" chuyên nghiệp.
* **Quy trình:** Model `llama-3.1-8b` trả lời câu hỏi, sau đó `llama-3.3-70b` (Giám khảo) tiến hành chấm điểm.
* **Kỹ thuật:** Thiết lập bộ tiêu chí (Rubric) khắt khe và ép định dạng đầu ra duy nhất là **JSON**.
* **Kết quả:** Nhận về phản hồi chuẩn hóa gồm: `score` (0-10), `justification` và `violation_detected`.

### 📌 Project 0004: So sánh đa mô hình & Bảng xếp hạng (Leaderboard)
**Mục tiêu:** Chạy thử nghiệm đồng loạt trên nhiều model và xuất bảng xếp hạng hiệu suất tự động.
* **Tính năng:** Tự động hóa luồng: Prompt -> Phản hồi từ 5 LLM -> Giám khảo chấm điểm -> Xử lý lỗi API (BadRequestError).
* **Điểm nổi bật:** Sử dụng `json.loads` để parse kết quả từ Giám khảo và sắp xếp theo điểm số.
* **Kết quả:** Xuất bảng Leaderboard trực quan, xác định model tối ưu nhất thông qua dữ liệu thực nghiệm.

### 📌 Project 0005: Đánh giá Đạo đức & Chống bịa đặt (Safety & Hallucination)
**Mục tiêu:** Xây dựng quy trình kiểm thử xâm nhập (Adversarial Testing) với kịch bản "bẫy" y tế nguy hiểm.
* **Kỹ thuật:** Thiết lập **Safety Rubric** với trọng số 50% cho tính an toàn; trừ sạch điểm nếu AI kê đơn thuốc hoặc khẳng định bệnh lý ẩu.
* **Điểm nổi bật:** Sử dụng `textwrap` để trình bày phần lý giải (Reasoning) chi tiết của Giám khảo một cách đẹp mắt.
* **Kết quả:** Phân loại rõ ràng trạng thái `✅ AN TOÀN` vs `❌ NGUY HIỂM` cho từng mô hình được thử nghiệm.

### 📌 Project 0006: Quản lý Thử nghiệm qua Google Sheets (Single Case)
**Mục tiêu:** Loại bỏ cấu hình cứng, chuyển sang quản lý tham số thử nghiệm qua giao diện bảng tính trực tuyến.
* **Kỹ thuật:** Sử dụng `gspread` và `google.auth` để đồng bộ dữ liệu giữa Colab và Google Sheets.
* **Tính năng:** Tự động nạp danh sách model, câu hỏi và prompts từ các ô chỉ định (A2, B2, C2, D2, E2).
* **Kết quả:** Cho phép thay đổi kịch bản test ngay trên Sheet mà không cần can thiệp vào mã nguồn Python.

### 📌 Project 0007: Automated Multi-Model Evaluation Framework
**Mục tiêu:** Hoàn thiện khung làm việc tự động hóa hoàn toàn việc kiểm thử hàng loạt và lưu trữ kết quả bền vững.
* **Cấu hình động:** Quét toàn bộ danh sách câu hỏi tại cột C và các bộ prompts tương ứng tại cột D, E.
* **Tự động xuất báo cáo:** Kết quả từ nhiều model được ghi trực tiếp xuống `Sheet2` theo cấu trúc: [Câu hỏi, Model, Trả lời AI, Đánh giá của Judge].
* **Điểm nổi bật:** Xử lý lỗi cục bộ cho từng model bằng `try-except` bên trong vòng lặp, giúp quá trình test không bị dừng lại khi gặp lỗi API đơn lẻ.

---

## 🇺🇸 English

### 📌 Project 0001: Gemini API Connection (New SDK)
**Goal:** Establish a baseline connection using Google GenAI SDK for factual knowledge testing.

### 📌 Project 0002: Multi-LLM Logical Reasoning Evaluator
**Goal:** Benchmark logical consistency and instruction-following using LangChain and Groq Cloud.

### 📌 Project 0003: AI-as-a-Judge Evaluation Framework
**Goal:** Automate quality assessment using a professional "Judge" AI with standardized JSON output.

### 📌 Project 0004: Multi-Model Comparison & Leaderboard
**Goal:** Execute concurrent testing across multiple models and generate an automated ranking.

### 📌 Project 0005: Safety & Hallucination Evaluation Pipeline
**Goal:** Build an adversarial testing workflow to measure ethical boundaries and hallucination risks.

### 📌 Project 0006: Centralized Management via Google Sheets
**Goal:** Migrate testing parameters to a dynamic spreadsheet interface for flexible configuration.

### 📌 Project 0007: Automated Multi-Model Evaluation Framework
**Goal:** Fully automate batch testing and persistent result storage in a multi-sheet environment.
* **Key Feature:** Automatically writes Question, Model, AI Answer, and Judge's Score directly to `Sheet2`.

---

### 🛠 Tech Stack
* **Language:** Python (Google Colab)
* **Frameworks:** LangChain, Google GenAI SDK
* **Infrastructure:** Groq Cloud, Google AI Studio, Google Sheets API
* **Models:** Gemini 2.5 Flash, Llama 3.3-70B, Llama 3.1-8B, Gemma 2, Mixtral, DeepSeek-R1
