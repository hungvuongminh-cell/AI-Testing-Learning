# 🚀 AI Testing & Evaluation Pipeline (Hệ thống Kiểm thử & Đánh giá AI)

Dòng thời gian học tập và xây dựng hệ thống kiểm thử tự động cho các mô hình ngôn ngữ lớn (LLM).

---

## 🇻🇳 Tiếng Việt

### 📌 Project 0001: Kết nối API Gemini 
**Mục tiêu:** Thiết lập nền tảng kết nối với Google AI SDK để chạy các kịch bản kiểm thử tự động.
* **Công cụ:** Google GenAI SDK, Gemini 2.0 Flash.
* **Kết quả:** Thực thi thành công các câu hỏi kiểm tra kiến thức thực tế với cơ chế delay để tối ưu hạn mức API.

### 📌 Project 0002: Đánh giá suy luận logic đa mô hình (Multi-LLM)
**Mục tiêu:** Benchmark khả năng logic và tuân thủ chỉ dẫn của các model hàng đầu như Llama 3.3, Gemma 2 và Mixtral.
* **Kỹ thuật:** Sử dụng **Structured Prompting** (Role, Task, Context, Constraints) để giảm thiểu ảo giác (hallucination).
* **Điểm nổi bật:** Tích hợp LangChain và Groq Cloud để chuyển đổi model linh hoạt qua `MODEL_INDEX`.

### 📌 Project 0003: Khung đánh giá AI-as-a-Judge
**Mục tiêu:** Tự động hóa việc chấm điểm chất lượng phản hồi LLM bằng cách sử dụng một AI "Giám khảo" chuyên nghiệp.
* **Quy trình:** Sử dụng model mạnh (Llama 3.3 70B) làm Giám khảo để chấm điểm dựa trên bộ tiêu chí (Rubric) khắt khe về tính khoa học và sự tuân thủ.
* **Kết quả:** Phản hồi định dạng **JSON** chuẩn gồm: Điểm số (0-10), lý do chi tiết và phát hiện vi phạm.

### 📌 Project 0004: So sánh đa mô hình & Bảng xếp hạng (Leaderboard)
**Mục tiêu:** Chạy thử nghiệm đồng loạt trên nhiều model và xuất bảng xếp hạng hiệu suất tự động.
* **Tính năng:** Tự động hóa luồng: Prompt -> Phản hồi từ nhiều LLM -> Giám khảo chấm điểm -> Xếp hạng Rank.
* **Kết quả:** Tìm ra model tối ưu nhất (ví dụ: Llama 3.3-70B) thông qua dữ liệu thực nghiệm và xử lý lỗi API tự động.

### 📌 Project 0005: Hệ thống đánh giá Đạo đức & Chống bịa đặt (Safety & Hallucination Evaluator)
**Mục tiêu:** Xây dựng quy trình kiểm thử xâm nhập (Adversarial Testing) để đo lường ranh giới an toàn và độ tin cậy của đa mô hình LLM.
* **Kỹ thuật nâng cao:** Complex Structured Prompting: Thiết lập kịch bản "bẫy" y tế khắt khe (Role, Task, Context, Constraints) để ép AI vào tình huống vi phạm đạo đức.
* **Safety Rubric (50% trọng số):** Bộ tiêu chí chấm điểm ưu tiên tính mạng con người, trừ sạch điểm nếu AI tự ý kê đơn thuốc hoặc khẳng định bệnh lý ẩu.
* **Điểm nổi bật:** Tự động hóa hoàn toàn luồng: Prompt độc hại -> Phản hồi đa model -> Giám khảo chấm điểm chuyên sâu -> Xuất bảng xếp hạng kèm lý giải (Reasoning) chi tiết.
* **Kết quả:** Hệ thống phân loại rõ ràng các model "An toàn" vs "Nguy hiểm", giúp tối ưu hóa việc chọn lọc model cho các ứng dụng thực tế nhạy cảm.

###📌 Project 0006: Hệ thống Quản lý Thử nghiệm tập trung qua Google Sheets
**Mục tiêu:** Loại bỏ cấu hình cứng (hardcode), chuyển sang quản lý toàn bộ tham số thử nghiệm thông qua giao diện bảng tính trực tuyến.
* **Kỹ thuật:** Sử dụng gspread và google.auth để đồng bộ dữ liệu thời gian thực giữa Google Colab và Google Sheets.
* **Tính năng mới:**
* **Cấu hình động:** Tự động nạp danh sách TEST_MODELS, JUDGE_MODEL, và các bộ System Prompts từ các ô chỉ định (A2, B2, C2, D2, E2).

---

## 🇺🇸 English

### 📌 Project 0001: Gemini API Connection
**Goal:** Establish a baseline connection with Google AI SDK to execute automated test scripts.
* **Tools:** Google GenAI SDK, Gemini 2.0 Flash.
* **Outcome:** Successfully executed factual knowledge tests with delay mechanisms to respect API quotas.

### 📌 Project 0002: Multi-LLM Logical Reasoning Evaluator
**Goal:** Benchmark logical consistency and instruction-following across top-tier models like Llama 3.3, Gemma 2, and Mixtral.
* **Technique:** Implemented **Structured Prompting** (Role, Task, Context, Constraints) to minimize hallucinations.
* **Highlights:** Integrated LangChain and Groq Cloud for seamless model switching via `MODEL_INDEX`.

### 📌 Project 0003: AI-as-a-Judge Evaluation Framework
**Goal:** Automate the assessment of LLM response quality using a professional "Judge" AI.
* **Process:** Leveraging a high-reasoning model (Llama 3.3 70B) as a Judge to score outputs based on strict scientific and compliance rubrics.
* **Outcome:** Standardized **JSON** responses including scores (0-10), detailed justifications, and violation detection.

### 📌 Project 0004: Multi-Model Comparison & Leaderboard
**Goal:** Execute concurrent testing across multiple models and generate an automated performance leaderboard.
* **Features:** Automated workflow: Prompt -> Multi-LLM Responses -> Judge Evaluation -> Ranking.
* **Outcome:** Identified the optimal model (e.g., Llama 3.3-70B) through empirical data and automated API error handling.

### 📌 Project 0005: Safety & Hallucination Evaluation Pipeline
**Goal:** Build an adversarial testing workflow to measure the safety boundaries and reliability of multiple LLMs.
* **Advanced Techniques:** * Complex Structured Prompting: Designing rigorous medical "trap" scenarios (Role, Task, Context, Constraints) to test AI ethical compliance.
* **Safety Rubric (50% weight):** A scoring system prioritizing human life, disqualifying any model that prescribes medication or makes unauthorized medical claims.
* **Highlights:** Fully automated workflow: Adversarial Prompt -> Multi-LLM Responses -> Deep Judge Evaluation -> Detailed Leaderboard with full reasoning.
* **Outcome:** Clearly categorizes models into "Safe" vs "Dangerous" status, enabling optimized model selection for sensitive real-world applications.

### 📌 Project 0006: Centralized Evaluation Management via Google Sheets
**Goal:** Eliminate hardcoded parameters by migrating the testing workflow management to a dynamic spreadsheet interface.
* **Technique:** Leveraged gspread and google.auth for real-time data synchronization between Google Colab and Google Sheets.
* **New Features:**
* **Dynamic Configuration::** Automatically fetches TEST_MODELS, JUDGE_MODEL, and various System Prompts from designated cells (A2, B2, C2, D2, E2).

---

### 🛠 Tech Stack
* **Language:** Python (Google Colab)
* **Frameworks:** LangChain, Google GenAI SDK
* **Infrastructure:** Groq Cloud, Google AI Studio
* **Models Tested:** Gemini 2.0 Flash, Llama 3.3-70B, Llama 3.1-8B, Mixtral 8x7B, Gemma 2
