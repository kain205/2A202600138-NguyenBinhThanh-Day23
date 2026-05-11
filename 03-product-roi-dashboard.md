# Product ROI Dashboard — Synapsy (Medical Study Copilot)

## Phần A: Thách Thức Và Phạm Vi Sản Phẩm (Adoption Context)

### A.1 Thách Thức Nhóm Chọn

| Trường | Trả lời |
|---|---|
| Thách thức áp dụng AI | "Trust Gap": Sinh viên Y khoa từ chối dùng AI vì sợ ảo giác (hallucination). Một thẻ flashcard sai kiến thức lâm sàng có thể dẫn đến hậu quả nghiêm trọng trong kỳ thi và tư duy điều trị sau này. |
| Tình huống xuất phát từ ai / ở đâu? | Sinh viên Y khoa tại Việt Nam (60-90K người) đang trong giai đoạn ôn thi nước rút 48h. |
| Dấu hiệu bị kẹt | Sinh viên vẫn thà mất 3-5 tiếng/ngày tự làm thẻ Anki thủ công thay vì dùng AI, vì họ không tin vào độ chính xác của chatbot truyền thống. |
| Vì sao thách thức này đáng giải quyết? | Giải phóng thời gian chuẩn bị tài liệu để tập trung vào việc học (Active Recall), giúp sinh viên vượt qua áp lực khối lượng kiến thức khổng lồ của ngành Y. |

### A.2 Sản Phẩm / Công Cụ AI

| Trường | Trả lời |
|---|---|
| Tên sản phẩm / công cụ AI | Synapsy |
| Người dùng chính | Sinh viên Y khoa năm 3-6 (Giai đoạn lâm sàng) |
| Bối cảnh sử dụng | Khi sinh viên có một file PDF giáo trình/slide mới và cần ôn tập cấp tốc cho kỳ thi nội trú hoặc kết thúc học phần. |
| Mục tiêu kinh doanh / học tập / vận hành | Đạt PMF Signal: 50 users hoàn thành ôn 50+ thẻ trong 48h. Tăng hiệu suất ôn tập (Time-to-Study). |
| Không nằm trong phạm vi | Tư vấn chẩn đoán y tế lâm sàng thực tế, hệ thống SRS dài hạn (đã đẩy sang giai đoạn Later). |

### A.3 Các Quy Trình Chính

| # | Tên quy trình | Vai trò AI | Điểm người kiểm tra | Khi AI sai thì xử lý thế nào? |
|---|---|---|---|---|
| 1 | Upload & Diagnosing | Generate (Parse PDF và sinh Diagnostic Quiz để tìm điểm mù) | Sinh viên làm Quiz và xem bản đồ ưu tiên (Priority Map) | Sinh viên gắn cờ câu hỏi sai, AI điều chỉnh trọng số ưu tiên. |
| 2 | Study & Verify | Recommend (Tự động sinh flashcard từ tài liệu gốc) | Sinh viên học thẻ bằng giao diện Split-screen (F4-lite) | Sinh viên click "Xem Nguồn" để đối chiếu PDF gốc. Nếu sai, xóa thẻ ngay lập tức. |

### A.4 Chẩn Đoán Nhanh ADKAR

| Stage | Câu hỏi | Nhận định nhóm |
|---|---|---|
| Awareness | Người dùng có biết AI này giúp gì không? | Có, giúp tạo flashcard nhanh và tìm lỗ hổng kiến thức. |
| Desire | Người dùng có muốn dùng không? | Trung bình thấp. Rào cản lớn nhất là nỗi sợ AI bịa đặt kiến thức (Hallucination). |
| Knowledge | Người dùng có biết dùng đúng không? | Có, giao diện tập trung vào luồng (Opinionated Workflow) nên dễ hiểu. |
| Ability | Người dùng có đủ access, thời gian, kỹ năng không? | Có, chỉ cần upload PDF. Tuy nhiên, tốc độ xử lý (Latency) là rào cản kỹ thuật. |
| Reinforcement | Có cơ chế khiến họ quay lại dùng không? | Có, nếu họ thấy điểm Quiz cải thiện sau khi học thẻ đã được verify. |

**Barrier chính:** `Desire (Trust)`: Sinh viên Y có "Zero-tolerance" với lỗi sai. Nếu Synapsy không chứng minh được mọi thẻ đều có nguồn gốc (Traceability), họ sẽ quay lại làm thủ công.

### A.5 3 Tactic Áp Dụng

| Tactic | Nhắm vào barrier nào? | Áp dụng cho quy trình nào? | Người phụ trách | Khi nào hoàn thành? |
|---|---|---|---|---|
| 1. Triển khai Split-screen UI (F4-lite) trỏ nguồn về PDF | Desire (Trust) | Quy trình 2 | Founder / Frontend | Tuần 2 |
| 2. Implement nút "Flag Hallucination" trực tiếp trên thẻ | Desire / Quality | Quy trình 2 | Founder / Backend | Tuần 1 |
| 3. Xây dựng "No-AI-Creativity" Prompt (Ép AI chỉ trích xuất) | Desire (Risk) | Quy trình 1 & 2 | AI Engineer | Tuần 1 |

---

## Phần B: Dashboard Đo ROI Của Sản Phẩm

### B.1 Chỉ Số Toàn Sản Phẩm

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu (90 ngày) | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % users hoàn thành ôn 50 thẻ/48h đầu | 0% | 50 users | DB Query | Founder | User chỉ click "Easy" cho xong để xem kết quả | Đo thời gian trung bình xem 1 mặt thẻ (>3s) |
| Value (Productivity) | Thời gian từ lúc Upload đến lúc có bộ thẻ 50 câu | 180p (Anki) | < 5 phút | System Logs | AI Engineer | AI sinh thẻ rác, không dùng được | Kết hợp với chỉ số Retention (D7 upload lại) |
| Trust / Quality | % Thẻ bị xóa/Flag do lỗi kiến thức | N/A | < 3% | App Database | Founder | User lười không thèm flag dù sai | Theo dõi % click "Xem Nguồn" để verify |

### B.2 Chỉ Số Theo Từng Quy Trình

#### Quy trình 1 — Upload & Diagnosing

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Activation | % PDF upload thành công (không lỗi parse) | N/A | 95% | MinerU Logs | Backend Lead | File quá dài (>200 trang) bị fail | Cảnh báo giới hạn trang trước khi upload |
| Productivity | Latency sinh Priority Map (Bản đồ ưu tiên) | N/A | < 45 giây | Helicone | AI Engineer | 45s vẫn là quá lâu cho 1 session | Dùng Global Caching để trả kết quả tức thì |

#### Quy trình 2 — Study & Verify

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
|---|---|---:|---:|---|---|---|---|
| Engagement | % users click nút "Xem Nguồn" (Verify) | 0% | > 50% | Telemetry | UX Designer | Click nhiều chứng tỏ AI không đáng tin | Là tín hiệu tốt của "Trust building" ở giai đoạn đầu |
| Quality | Accuracy Rate (Do chuyên gia check mẫu) | N/A | > 97% | Manual Audit | Founder | Chuyên gia kiểm định tốn chi phí/thời gian | Dùng LLM-as-a-judge (Claude) để audit chéo |
| Trust | D7 Retention (Tỷ lệ upload file thứ 2 sau 7 ngày) | 0% | 40% | Amplitude | Founder | User chỉ dùng khi có kỳ thi (seasonal) | Chấp nhận tính mùa vụ, đo theo chu kỳ thi |

---

## Phần C: Dashboard Mock (Synapsy Monitor)

```text
┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 1: PMF SIGNAL (KR2)           │ │ TILE 2: TRUST BUILDER (F4)         │
│ Metric: Users 50/50/48h            │ │ Metric: "Xem Nguồn" Click Rate     │
│ Current: 12 users   Target: 50     │ │ Current: 65%      Target: >50%     │
│ Status: AMBER                      │ │ Status: GREEN                      │
│ Action if red: Customer Discovery  │ │ Action if red: Làm nút
