# Từ Backlog cũ đến Backlog chuẩn: Module “Đánh giá sản phẩm” (GreenCart)

**Vai trò:** Business Analyst · **Epic:** Đánh giá & Nhận xét sản phẩm

## PHẦN A — CHẨN ĐOÁN BACKLOG HIỆN TRẠNG

### A1. S1 — ĐÚNG

> “Là một khách hàng, tôi muốn chấm sao (1–5 sao) cho sản phẩm đã mua, so that tôi chia sẻ mức độ hài lòng của mình.”

S1 là một User Story hợp lệ, đặt đúng cấp (Story nằm dưới Feature F1):

| Tiêu chí | Đánh giá |
| --- | --- |
| Cấu trúc As a / I want / So that | Đủ: vai trò (khách hàng), hành động (chấm 1–5 sao), giá trị (chia sẻ mức độ hài lòng) |
| **I**ndependent | Đạt: tự làm được, không phụ thuộc story khác |
| **N**egotiable | Đạt: chưa áp đặt cách thực hiện (sao bấm hay kéo là do team bàn) |
| **V**aluable | Đạt: có giá trị rõ ràng cho khách hàng |
| **E**stimable | Đạt: phạm vi rõ, team ước lượng được |
| **S**mall | Đạt: một hành vi duy nhất, làm gọn trong một Sprint |
| **T**estable | Đạt: kiểm thử được (chọn 1–5 sao, lưu đúng giá trị, không cho 0 hoặc 6) |

Ghi chú nhỏ: nên thống nhất ngôn ngữ (“so that” → “để”) và bổ sung Acceptance Criteria (xem Phần B).

### A2. S2 — SAI

> “Cho phép khách chấm sao, viết bình luận, đính kèm ảnh, gửi đánh giá, hệ thống kiểm duyệt nội dung, rồi hiển thị công khai lên trang sản phẩm.”

**Kết luận:** S2 **không phải User Story**. Nó là mô tả một luồng chức năng trọn vẹn, tức tầm **Feature** (thậm chí gần một Epic nhỏ) nhưng bị điền vào ô Story.

**Vi phạm nguyên tắc phân cấp Epic → Feature → Story**

- Gộp ít nhất 6 hành vi: chấm sao, bình luận, đính kèm ảnh, gửi, kiểm duyệt, hiển thị công khai. Mỗi hành vi đủ tầm một Story riêng.
- Gộp nhiều persona: khách hàng (viết, gửi), Admin/hệ thống (kiểm duyệt), khách xem (đọc). Một Story chỉ nên có một vai trò chính.
- Chồng lấn với S1 (chấm sao) và với F2 (hiển thị cho khách khác xem).

**Vi phạm INVEST**

| Tiêu chí | Vi phạm |
| --- | --- |
| **S**mall | Vi phạm nặng nhất: quá lớn, không xong trong một Sprint |
| **E**stimable | Quá nhiều phần chưa rõ (lưu ảnh, quy tắc kiểm duyệt, hiển thị) nên không thể ước lượng một con số đáng tin |
| **I**ndependent | Chồng lấn S1, kéo theo cả F2; các phần bên trong phụ thuộc nhau |
| **V**aluable | Viết dạng chức năng hệ thống, không có vai trò và không có “so that”, nên không thấy giá trị cho ai |
| **T**estable | Không có tiêu chí chấp nhận chung, kiểm thử trọn khối quá rộng, chỉ cần một phần lỗi là cả Story không “Done” |
| **N**egotiable | Dạng liệt kê giải pháp (gửi, kiểm duyệt, hiển thị) thay vì mô tả nhu cầu |

### A3. Vì sao S2 không thể đưa thẳng vào Sprint

1. **Không ước lượng được và không vừa một Sprint:** quá lớn, rủi ro dang dở cuối Sprint, Burndown mất ý nghĩa.
2. **Không có Definition of Done rõ ràng:** không biết “xong” là xong phần nào (chỉ gửi được, hay phải kiểm duyệt và hiển thị mới tính).
3. **Nhiều vai trò, nhiều phụ thuộc kỹ thuật** (lưu trữ ảnh, quy trình duyệt, trang sản phẩm): khó chia việc và khó test.
4. **Trùng lặp với S1 và F2:** dễ làm hai lần hoặc bỏ sót.
5. **Không thể giao giá trị từng phần:** Product Owner không thể ưu tiên “làm trước cái nào”, đúng như vấn đề họ đang gặp.

→ Cần **tách nhỏ** (split) thành các Story độc lập trước khi đưa vào Sprint Planning.

## PHẦN B — BACKLOG ĐÃ HOÀN THIỆN

**Epic: Đánh giá & Nhận xét sản phẩm**

### Feature F1 — Viết đánh giá sản phẩm

**S1 — Chấm sao sản phẩm** *(giữ nguyên)*

- **Story:** Là một khách hàng đã mua sản phẩm, tôi muốn chấm sao (1–5 sao) cho sản phẩm, để chia sẻ mức độ hài lòng của mình.
- **AC:** (1) Chỉ chọn được giá trị 1–5. (2) Chỉ khách đã mua và nhận hàng mới thấy chức năng chấm sao. (3) Có thể đổi lựa chọn sao trước khi gửi.

**S3 — Viết bình luận cho đánh giá** *(bổ sung)*

- **Story:** Là một khách hàng đã mua sản phẩm, tôi muốn viết bình luận bằng văn bản về trải nghiệm sử dụng, để người mua khác hiểu rõ ưu nhược điểm của sản phẩm.
- **AC:** (1) Ô bình luận tùy chọn, tối đa 1.000 ký tự. (2) Hiển thị bộ đếm ký tự còn lại. (3) Không lưu khoảng trắng thuần; chặn ký tự nguy hiểm (XSS).

**S2.1 — Gửi đánh giá** *(tách từ S2)*

- **Story:** Là một khách hàng đã mua sản phẩm, tôi muốn gửi đánh giá (số sao và bình luận) lên hệ thống, để ghi nhận ý kiến của mình về sản phẩm.
- **AC:** (1) Bắt buộc có số sao mới gửi được. (2) Gửi thành công thì đánh giá có trạng thái “Chờ duyệt” và hiện thông báo xác nhận. (3) Mỗi khách chỉ gửi một đánh giá cho mỗi sản phẩm đã mua.

**S2.2 — Đính kèm ảnh vào đánh giá** *(tách từ S2)*

- **Story:** Là một khách hàng đã mua sản phẩm, tôi muốn đính kèm ảnh thực tế vào đánh giá, để minh chứng chất lượng sản phẩm cho người mua khác.
- **AC:** (1) Tối đa 3 ảnh, định dạng JPG/PNG, mỗi ảnh ≤ 5MB. (2) Xem trước và xóa ảnh trước khi gửi. (3) Sai định dạng hoặc quá dung lượng thì báo lỗi rõ ràng.

**S2.3 — Kiểm duyệt đánh giá** *(tách từ S2)*

- **Story:** Là một Quản trị viên, tôi muốn duyệt hoặc từ chối các đánh giá đang chờ, để nội dung công khai không chứa ngôn từ vi phạm hay spam.
- **AC:** (1) Có danh sách đánh giá “Chờ duyệt” kèm nội dung và ảnh. (2) Duyệt thì chuyển “Đã duyệt”; từ chối thì ghi lý do. (3) Chỉ đánh giá “Đã duyệt” mới được hiển thị công khai (liên kết với F2).

### Feature F2 — Xem điểm trung bình và đánh giá sản phẩm *(đặt tên mới)*

*Lý do đặt tên:* tên Feature mô tả nhóm khả năng của người đọc đánh giá (xem tổng quan điểm + đọc chi tiết), tách bạch với F1 (người viết).

**S4 — Xem điểm đánh giá trung bình**

- **Story:** Là một khách hàng đang xem sản phẩm, tôi muốn thấy điểm đánh giá trung bình và tổng số lượt đánh giá ngay trên trang sản phẩm, để nhanh chóng nắm được mức độ hài lòng chung trước khi quyết định mua.
- **AC:** (1) Điểm trung bình làm tròn 1 chữ số thập phân, tính chỉ trên đánh giá “Đã duyệt”. (2) Hiển thị tổng số đánh giá. (3) Sản phẩm chưa có đánh giá thì hiện “Chưa có đánh giá”.

**S5 — Đọc danh sách đánh giá của khách khác**

- **Story:** Là một khách hàng đang xem sản phẩm, tôi muốn đọc danh sách đánh giá (số sao, bình luận, ảnh) của những người đã mua, để có thêm thông tin thực tế trước khi quyết định mua.
- **AC:** (1) Chỉ hiển thị đánh giá “Đã duyệt”, mới nhất trước. (2) Phân trang 10 đánh giá mỗi trang. (3) Hiển thị tên người đánh giá (che bớt), số sao, bình luận, ảnh nếu có.

### Bảng tổng hợp Backlog

| ID | Feature | User Story | Vai trò | INVEST | Phụ thuộc |
| --- | --- | --- | --- | --- | --- |
| S1 | F1 | Chấm sao 1–5 | Khách hàng | Đạt | Không |
| S3 | F1 | Viết bình luận | Khách hàng | Đạt | Không |
| S2.1 | F1 | Gửi đánh giá | Khách hàng | Đạt | Nên làm sau S1 |
| S2.2 | F1 | Đính kèm ảnh | Khách hàng | Đạt | Cần S2.1 (có thể làm sau) |
| S2.3 | F1 | Kiểm duyệt đánh giá | Quản trị viên | Đạt | Cần S2.1 |
| S4 | F2 | Xem điểm trung bình | Khách hàng | Đạt | Cần S2.3 (có dữ liệu đã duyệt) |
| S5 | F2 | Đọc danh sách đánh giá | Khách hàng | Đạt | Cần S2.3 |

### Gợi ý thứ tự ưu tiên cho Sprint Planning

1. **Sprint 1 (lõi giá trị):** S1 → S3 → S2.1 (khách viết và gửi được đánh giá).
2. **Sprint 2:** S2.3 → S4 → S5 (kiểm duyệt và hiển thị cho khách khác).
3. **Sprint 3 (nâng cao):** S2.2 (đính kèm ảnh), vì không ảnh hưởng luồng chính.

### Ghi chú giả định

- S3 chưa có nội dung trong đề nên được hiểu là Story “viết bình luận”; S2 được tách thành **S2.1, S2.2, S2.3** (ba story, mỗi story một vai trò và một hành vi, đủ độc lập để ước lượng riêng).
- Phần “hiển thị công khai” của S2 được chuyển sang F2 (S5) để tránh trùng lặp.
- Giá trị cụ thể trong AC (1.000 ký tự, 3 ảnh, 5MB, 10 đánh giá/trang) là đề xuất, cần Product Owner xác nhận khi Refinement.
