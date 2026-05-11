# Bảng So Sánh Case Study — AI Adoption

## B. Case Comparison

Nhóm tổng hợp một case có tín hiệu thành công bền vững (Morgan Stanley) và một case mang tính cảnh báo rủi ro (Klarna).

| Trường | Case thành công / tín hiệu tốt | Case cảnh báo / thất bại |
|---|---|---|
| **Case** | **Morgan Stanley (AI @ Morgan Stanley Assistant)** | **Klarna (AI Customer Service Assistant)** |
| **Workflow có AI** | Hỗ trợ Financial Advisors tìm kiếm kiến thức nội bộ, tổng hợp báo cáo đầu tư để trả lời khách hàng. | Trợ lý ảo AI thay thế nhân viên chăm sóc khách hàng (tự động trả lời câu hỏi, hoàn tiền, hủy đơn). |
| **Metric chính** | - Tỉ lệ chấp nhận sử dụng (Adoption rate) của Advisors rất cao.<br>- Thời gian tìm kiếm thông tin (Productivity).<br>- Tỉ lệ sai sót tuân thủ tài chính (Quality/Trust). | - 2.3 triệu cuộc trò chuyện.<br>- Thay thế 700 FTEs.<br>- Thời gian xử lý: giảm từ 11 phút xuống 2 phút.<br>- Tiết kiệm $40 triệu. |
| **Metric đó chứng minh được gì?** | - AI hoạt động tốt như một "Co-pilot" (Trợ lý).<br>- Giúp tăng năng suất nội bộ mà không phá vỡ quy trình kiểm soát rủi ro vì Advisor vẫn là người kiểm duyệt cuối cùng (Human-in-the-loop). | - AI có thể xử lý lượng công việc khổng lồ ở quy mô lớn.<br>- Tiết kiệm chi phí vận hành nhanh chóng (Value) và giảm thời gian đóng ticket (Productivity). |
| **Metric đó chưa chứng minh được gì?** | - Chưa đo lường được trực tiếp việc AI có mang lại dòng tiền đầu tư mới hay không (Direct Revenue Value). | - Không chứng minh được sự hài lòng của khách hàng (Quality/Trust). Khách hàng kết thúc chat nhanh có thể do bực tức, không phải do hài lòng. |
| **Thiếu metric nào?** | Khách hàng cuối (End-client) NPS để xem câu trả lời của Advisor có tốt hơn trước khi dùng AI không. | - Customer Satisfaction Score (CSAT).<br>- Human Escalation Rate (Tỉ lệ khách nằng nặc đòi gặp người thật). |
| **Bài học cho dashboard nhóm** | AI ở môi trường rủi ro cao (Y tế, Tài chính) bắt buộc phải là "Co-pilot", không phải "Autopilot". Phải đo lường sự tin tưởng của người dùng nội bộ. | Đo chi phí và tốc độ là chưa đủ. Phải có chỉ số đối trọng (Counter-metric) về mặt Trải nghiệm & Độ chính xác. |

---

## Câu chốt

**Case thành công (Morgan Stanley) dạy nhóm tôi rằng:**
Khi áp dụng AI vào các ngành yêu cầu độ chính xác tuyệt đối và rủi ro pháp lý cao (như y tế hay tài chính), chiến lược tốt nhất là trao quyền cho chuyên gia (Human-in-the-loop). Việc đo lường không chỉ nằm ở năng suất, mà nằm ở mức độ chuyên gia tin tưởng công cụ (Trust) và sự an toàn trong tuân thủ.

**Case cảnh báo (Klarna) dạy nhóm tôi rằng:**
Tối ưu hóa mù quáng vào tốc độ xử lý (Productivity) và cắt giảm chi phí (Value) mà bỏ qua chất lượng trải nghiệm có thể dẫn đến "cạm bẫy đo lường". Số liệu có thể rất đẹp trên báo cáo tài chính nhưng lại là thảm họa về mặt thương hiệu và sự hài lòng của người dùng cuối.

**Vì vậy dashboard nhóm tôi phải:**
Áp dụng cho dự án Medical VLM Copilot: Tuyệt đối không chỉ đo thời gian bác sĩ hoàn thành báo cáo (Turnaround Time), mà bắt buộc phải có một *Counter-metric* là **Tỷ lệ chấp nhận theo ngữ nghĩa (Semantic Acceptance Rate)** hoặc **Tỉ lệ lỗi y khoa (QA Error Rate)**. Nếu năng suất tăng nhưng độ chính xác giảm, hệ thống phải bị dừng để đánh giá lại.
