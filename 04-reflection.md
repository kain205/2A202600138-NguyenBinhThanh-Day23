# Phản Tư Cá Nhân (Reflection)

**Chủ đề:** Giả định tôi sẽ thay đổi sau khi học về thiết kế Product ROI Dashboard.

Trước buổi học này, tôi luôn giữ một giả định rằng: Giá trị lớn nhất của Synapsy nằm ở tốc độ và số lượng. Tôi từng nghĩ chỉ cần đo lường xem AI có thể tự động sinh ra bao nhiêu thẻ flashcard mỗi phút, hay tiết kiệm được bao nhiêu giờ so với việc gõ Anki thủ công là đủ để chứng minh tính hiệu quả của sản phẩm (ROI).

Tuy nhiên, khi phân tích sâu vào rào cản áp dụng (Adoption Barrier) của sinh viên Y khoa, tôi nhận ra đó là một "chỉ số ảo" (Vanity Metric) chết người. Với đặc thù "Zero-tolerance" (không khoan nhượng với lỗi sai lâm sàng), nếu AI sinh ra 1.000 thẻ nhanh chóng nhưng bịa đặt (hallucinate) dù chỉ 1 thẻ, sinh viên sẽ lập tức mất niềm tin (Trust Gap) và tẩy chay toàn bộ ứng dụng. 

Vì vậy, tôi quyết định thay đổi hoàn toàn cách tiếp cận: Chuyển metric cốt lõi từ "Số lượng thẻ sinh ra" sang "Tỷ lệ click Xem Nguồn" (Source Verification Rate) làm đối trọng. Tôi học được rằng, với sinh viên Y khoa, giá trị cốt lõi của AI không phải là "tự động hóa 100% để học vẹt", mà là cung cấp một quy trình kiểm chứng minh bạch (Traceability) ngay trong luồng học. Tốc độ sinh thẻ chỉ tạo ra ROI thực sự khi người dùng dám tin và gắn bó với sản phẩm.
