🚀 AI Testing & Evaluation Pipeline (Hệ thống Kiểm thử & Đánh giá AI)
🇻🇳 Tiếng Việt
📌 Project 0001: Kết nối API Gemini
Mục tiêu: Thiết lập nền tảng kết nối với Google AI SDK để chạy các kịch bản kiểm thử tự động.
Công cụ: Google GenAI SDK, Gemini 2.0 Flash.
Kết quả: Thực thi thành công các câu hỏi kiểm tra kiến thức thực tế với cơ chế delay để tối ưu hạn mức API.
📌 Project 0002: Đánh giá suy luận logic đa mô hình (Multi-LLM)
Mục tiêu: Benchmark khả năng logic và tuân thủ chỉ dẫn của các model hàng đầu như Llama 3.3, Gemma 2 và Mixtral.
Kỹ thuật: Sử dụng Structured Prompting (Role, Task, Context, Constraints) để giảm thiểu ảo giác (hallucination).
Điểm nổi bật: Tích hợp LangChain và Groq Cloud để chuyển đổi model linh hoạt qua MODEL_INDEX.
📌 Project 0003: Khung đánh giá AI-as-a-Judge
Mục tiêu: Tự động hóa việc chấm điểm chất lượng phản hồi LLM bằng cách sử dụng một AI "Giám khảo" chuyên nghiệp.
Quy trình: Sử dụng model mạnh (Llama 3.3 70B) làm Giám khảo để chấm điểm dựa trên bộ tiêu chí (Rubric) khắt khe về tính khoa học và sự tuân thủ.
Kết quả: Phản hồi định dạng JSON chuẩn gồm: Điểm số (0-10), lý do chi tiết và phát hiện vi phạm.
📌 Project 0004: So sánh đa mô hình & Bảng xếp hạng (Leaderboard)
Mục tiêu: Chạy thử nghiệm đồng loạt trên nhiều model và xuất bảng xếp hạng hiệu suất tự động.
Tính năng: Tự động hóa luồng: Prompt -> Phản hồi từ nhiều LLM -> Giám khảo chấm điểm -> Xếp hạng Rank.
Kết quả: Tìm ra model tối ưu nhất (ví dụ: Llama 3.3-70B) thông qua dữ liệu thực nghiệm và xử lý lỗi API tự động.
🇺🇸 English
📌 Project 0001: Gemini API Connection
Goal: Establish a baseline connection with Google AI SDK to execute automated test scripts.
Tools: Google GenAI SDK, Gemini 2.0 Flash.
Outcome: Successfully executed factual knowledge tests with delay mechanisms to respect API quotas.
📌 Project 0002: Multi-LLM Logical Reasoning Evaluator
Goal: Benchmark logical consistency and instruction-following across top-tier models like Llama 3.3, Gemma 2, and Mixtral.
Technique: Implemented Structured Prompting (Role, Task, Context, Constraints) to minimize hallucinations.
Highlights: Integrated LangChain and Groq Cloud for seamless model switching via MODEL_INDEX.
📌 Project 0003: AI-as-a-Judge Evaluation Framework
Goal: Automate the assessment of LLM response quality using a professional "Judge" AI.
Process: Leveraging a high-reasoning model (Llama 3.3 70B) as a Judge to score outputs based on strict scientific and compliance rubrics.
Outcome: Standardized JSON responses including scores (0-10), detailed justifications, and violation detection.
📌 Project 0004: Multi-Model Comparison & Leaderboard
Goal: Execute concurrent testing across multiple models and generate an automated performance leaderboard.
Features: Automated workflow: Prompt -> Multi-LLM Responses -> Judge Evaluation -> Ranking.
Outcome: Identified the optimal model (e.g., Llama 3.3-70B) through empirical data and automated API error handling.
