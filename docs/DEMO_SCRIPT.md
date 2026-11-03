# Kịch bản demo và bảo vệ (7 phút)

## Kịch bản trình bày

| Thời gian | Nội dung / thao tác | Điểm cần nhấn mạnh |
|---|---|---|
| 0:00–0:40 | Giới thiệu bối cảnh và người dùng mục tiêu | Portfolio giúp nhà tuyển dụng xem thông tin chính nhanh; trang tĩnh, không có backend |
| 0:40–1:30 | Mở đầu trang và điều hướng | Thương hiệu, H1, mô tả, CTA và menu đến các section |
| 1:30–2:20 | Trình bày kỹ năng và dự án | Nêu rõ các project card hiện là minh họa; link `#` chưa phải demo thật |
| 2:20–3:10 | Cuộn đến Liên hệ | Email và GitHub; LinkedIn đã bỏ khỏi giao diện |
| 3:10–4:20 | Bật responsive mode, thử 360, 768, 1280px | 1/2/3 cột; chỉ ra phép đo `scrollWidth === clientWidth` |
| 4:20–5:10 | Kiểm tra accessibility cơ bản | Thứ bậc heading/landmark, `alt`, tab/focus-visible, `prefers-reduced-motion`; không tuyên bố đã đạt WCAG audit |
| 5:10–6:00 | Giải thích thiết kế/kỹ thuật | Mobile-first; Flexbox cho điều hướng; Grid cho thẻ; custom properties để đổi theme; tránh JS/dependency |
| 6:00–6:40 | Kiểm thử, rủi ro và hiệu năng | Nêu số đo ở Chromium, giới hạn chưa có Lighthouse/Firefox/thiết bị thật |
| 6:40–7:00 | Trạng thái phát hành và kết luận | Workflow Pages đã chuẩn bị nhưng URL công khai còn bản cũ; không trình bày deploy là thành công cho tới khi xác minh |

## Checklist trước buổi demo

- Dùng bản mới nhất sau khi đồng bộ và xác minh GitHub Pages; nếu chưa, demo rõ là localhost.
- Đóng tab cá nhân/thông báo; kiểm tra email và liên kết không bị lộ thêm dữ liệu riêng.
- Mở DevTools Responsive Design Mode; chuẩn bị 360, 768 và 1280 CSS px.
- Kiểm tra trước liên kết và ảnh; không click các liên kết dự án `#` như thể là sản phẩm thật.
- Có README, báo cáo, chỉ mục evidence và lịch sử commit thực tế; không tự tạo lời khẳng định về chỉ số chưa đo.

## Câu hỏi phản biện gợi ý

**Vì sao dùng website một trang thay vì nhiều trang?**
Nội dung portfolio nhỏ và mục tiêu là xem nhanh. Một trang tránh router/build step. Đổi lại trang dài hơn và case study chi tiết sẽ cần trang riêng khi có dự án thật.

**Vì sao kết hợp Flexbox với Grid?**
Flexbox phù hợp hàng điều hướng và chip có chiều dài linh hoạt; Grid phù hợp danh sách card cần số cột nhất quán theo breakpoint.

**Website đã deploy chưa?**
Workflow triển khai tự chạy khi có cập nhật trên `main`. Chỉ xác nhận deploy sau khi workflow thành công và nội dung mới xuất hiện trên URL công khai.

**Đã chứng minh hiệu năng hay đạt WCAG chưa?**
Chưa. Đã đo layout/overflow responsive trong Chromium; chưa chạy Lighthouse, validator độc lập hoặc audit WCAG đầy đủ. Cần đo và lưu kết quả trước khi đưa ra kết luận.

**Các dự án có phải sản phẩm thật không?**
Các thẻ hiện là nội dung minh họa, chưa có URL chi tiết. Trước khi phát hành chuyên nghiệp cần thay bằng case study thật hoặc ghi trạng thái rõ ràng.

**Làm sao cập nhật theme?**
Sửa các CSS custom properties ở `:root`, kiểm tra màu chữ/nền và trạng thái hover/focus ở mọi section.
