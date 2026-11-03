# Báo cáo phân tích và thiết kế

## 1. Yêu cầu, mục tiêu và phạm vi

### Mục tiêu

Tạo portfolio CV tĩnh để nhà tuyển dụng có thể nhanh chóng nhận biết chủ sở hữu, kỹ năng, dự án và cách liên hệ. Trang phải đọc được trên điện thoại, máy tính bảng và máy tính; nội dung chính không phụ thuộc JavaScript hay dịch vụ bên ngoài.

### Người dùng và nhu cầu

| Người dùng | Nhu cầu chính |
|---|---|
| Nhà tuyển dụng | Xem hồ sơ, kỹ năng và phương thức liên hệ nhanh |
| Người đánh giá kỹ thuật | Nhận biết cấu trúc HTML/CSS, bố cục và ví dụ dự án |
| Chủ sở hữu portfolio | Cập nhật nội dung, ảnh và liên kết mà không cần build tool |

### Trong phạm vi

- Một trang với các mục Giới thiệu, Kỹ năng, Dự án, Liên hệ.
- HTML5 ngữ nghĩa, CSS3, Flexbox, Grid và media query mobile-first.
- Điều hướng nội trang, ảnh có văn bản thay thế, trạng thái focus bàn phím.
- Tài liệu hướng dẫn, wireframe, kiểm thử, minh chứng và demo.
- Workflow GitHub Actions để triển khai nội dung tĩnh qua GitHub Pages khi được đồng bộ lên repository.

### Ngoài phạm vi / chưa có dữ liệu

- Backend, biểu mẫu gửi dữ liệu, đăng nhập, API hoặc cơ sở dữ liệu.
- Các dự án thật, URL chi tiết dự án, hồ sơ nghề nghiệp và số liệu hiệu năng đã kiểm chứng.
- Triển khai phiên bản làm việc hiện tại lên GitHub Pages: thư mục này không được kết nối với Git; URL công khai đang hiển thị phiên bản cũ.
- Kiểm định WCAG đầy đủ, kiểm thử trên thiết bị thật, kiểm thử đa trình duyệt và screencast.

### Giả định và ràng buộc

- Nội dung hiển thị bằng tiếng Việt; trình duyệt hiện đại hỗ trợ HTML5/CSS Grid.
- Mọi ảnh và thông tin liên hệ do chủ sở hữu cung cấp hoặc có quyền sử dụng.
- Không có build step; GitHub Pages phục vụ `index.html` cùng thư mục `assets/`.
- Các viewport kiểm chứng là chiều rộng CSS 360, 375, 768, 1024 và 1280px.
- Git và quyền đẩy mã không khả dụng trong môi trường làm việc này; không khẳng định đã tạo commit hay triển khai phiên bản mới.

## 2. Wireframe và phương án thiết kế

### Phương án A — Portfolio một trang (được chọn)

```text
MOBILE                              TABLET / DESKTOP
┌──────────────────────┐            ┌──────────────────────────────┐
│ P  Tên               │            │ P  Tên       Điều hướng      │
│ Giới thiệu Kỹ năng   │            ├──────────────────────────────┤
│ Dự án     Liên hệ    │            │ Giới thiệu           Ảnh     │
├──────────────────────┤            │ Mô tả + nút                  │
│ Giới thiệu           │            ├──────────────────────────────┤
│ Mô tả                │            │ Kỹ năng: chip tự xuống dòng  │
│ [Dự án] [Liên hệ]    │            ├──────────────────────────────┤
│ Ảnh                  │            │ Dự án: 2 cột / 3 cột         │
├──────────────────────┤            ├──────────────────────────────┤
│ Kỹ năng              │            │ Liên hệ + Footer             │
├──────────────────────┤            └──────────────────────────────┘
│ Dự án: 1 cột         │
├──────────────────────┤
│ Liên hệ              │
├──────────────────────┤
│ Footer               │
└──────────────────────┘
```

### Phương án B — Website nhiều trang

```text
Trang chủ ─┬─ Hồ sơ
           ├─ Danh sách dự án ─ Chi tiết từng dự án
           └─ Liên hệ
```

### So sánh và trade-off

| Quyết định | Phương án được chọn | Lý do | Đánh đổi |
|---|---|---|---|
| Điều hướng | Một trang, liên kết đến section | Người xem nắm nội dung nhanh; ít tệp và không cần routing | Trang dài hơn; các URL dự án cần bổ sung nếu có nội dung thật |
| Bố cục | Flexbox cho header/nhóm chip; Grid cho project cards | Mỗi layout dùng công cụ phù hợp và co giãn theo số cột | Cần kiểm tra ngưỡng breakpoint và nội dung dài |
| Responsive | Mobile-first; 1 cột, từ 768px 2 cột, từ 1280px 3 cột | Quy tắc đơn giản, dễ mở rộng | Chỉ có bằng chứng hiện tại ở các viewport đã đo |
| Styling | CSS tách tệp và custom properties | Tập trung màu, spacing và typography; dễ đổi chủ đề | Chưa dùng design system/package ngoài |
| Hành vi | HTML/CSS, không dùng JavaScript | Ít phụ thuộc, tải và bảo trì đơn giản | Không có lọc dự án, menu tương tác hoặc biểu mẫu |
| Nội dung dự án | Thẻ minh họa | Giữ cấu trúc portfolio trong khi chờ nội dung thật | Không được trình bày như dự án đã triển khai; liên kết `#` phải thay trước phát hành |

## 3. Tiêu chí chấp nhận

| ID | Tiêu chí kiểm chứng | Kết quả hiện tại |
|---|---|---|
| AC-01 | Có Giới thiệu, Kỹ năng, Dự án và Liên hệ; tên, email và GitHub thống nhất | Đạt trên bản cục bộ |
| AC-02 | Bố cục dự án lần lượt 1/2/3 cột ở 360/768/1280 CSS px | Đạt theo đo Chromium |
| AC-03 | `documentElement.scrollWidth === documentElement.clientWidth` ở các viewport đo | Đạt ở 360, 375, 768, 1024, 1280 |
| AC-04 | Dùng landmark HTML ngữ nghĩa, metadata `lang`, `viewport`, `title` | Đạt khi kiểm tra mã nguồn |
| AC-05 | Bốn liên kết điều hướng trỏ tới ID tồn tại; email dùng `mailto:`; GitHub mở đúng URL | Đạt trên bản cục bộ |
| AC-06 | Tất cả ảnh có `alt`; link có thể nhận focus bàn phím | Đạt cơ bản: 5 ảnh có `alt`; Tab đầu tiên hiển thị focus outline. Chưa audit mọi control/bàn phím |
| AC-07 | URL Pages công khai hiển thị đúng bản cục bộ và workflow kết thúc thành công | Chưa đạt: URL công khai đang hiển thị tên cũ; chưa đẩy mã mới |
| AC-08 | Có báo cáo, README, changelog, AI log, chỉ mục bằng chứng, demo 7 phút | Đạt trong gói bàn giao cục bộ |

## 4. Rủi ro và giảm thiểu

| Rủi ro | Tác động | Cách giảm thiểu / việc cần làm |
|---|---|---|
| GitHub Pages đang phục vụ nội dung cũ | Người xem công khai thấy sai tên, liên hệ và màu | Đồng bộ tệp lên nhánh `main`, chờ Pages chạy, rồi xác minh URL và chụp lại bằng chứng |
| Thẻ dự án và liên kết `#` chỉ là minh họa | Người xem có thể hiểu nhầm là sản phẩm thật hoặc liên kết hỏng | Thay bằng case study và URL có thể truy cập; nếu chưa có thì ghi rõ “đang cập nhật” hoặc bỏ thẻ |
| Liên hệ là dữ liệu cá nhân | Có thể bị thu thập ngoài ý muốn | Chỉ giữ email/GitHub mà chủ sở hữu muốn công khai; rà soát trước khi phát hành |
| Screenshot không cùng phiên bản hoặc viewport | Bằng chứng không phản ánh đúng sản phẩm | Dùng quy trình trong `EVIDENCE_INDEX.md`, ghi ngày và kích thước viewport |
| Kiểm tra Chromium chưa thay cho mọi thiết bị | Có thể bỏ sót khác biệt trình duyệt/zoom | Kiểm tra Chrome/Firefox và điện thoại thật; ghi kết quả bổ sung |
| Chưa có Lighthouse/validator | Chưa có chỉ số hiệu năng hoặc xác nhận chuẩn markup độc lập | Chạy công cụ, lưu kết quả và không tự suy diễn điểm số |

## 5. Tổ chức kỹ thuật

- `index.html`: metadata, điều hướng, nội dung, thẻ dự án và liên hệ.
- `assets/css/styles.css`: design tokens, reset, component và media query.
- `assets/img/avatar.jpg`: ảnh đại diện.
- `docs/`: thiết kế, kết quả kiểm thử, minh chứng và kịch bản demo.
- `.github/workflows/pages.yml`: đóng gói `index.html`/`assets` và triển khai khi push lên `main`.

Workflow chỉ là cấu hình trong bản làm việc. Nó chưa chạy trên phiên bản hiện tại của GitHub vì tệp chưa được đẩy lên repository và cần bật **Settings → Pages → Source: GitHub Actions** nếu chưa cấu hình.

## 6. Hướng cải tiến

1. Đồng bộ bản này lên repository và xác minh Pages.
2. Thay nội dung dự án minh họa bằng case study thật.
3. Chạy validator HTML/CSS, Lighthouse và kiểm tra trên ít nhất Chrome + Firefox.
4. Kiểm tra bàn phím, zoom 200%, tương phản và thiết bị thật; bổ sung kết quả vào báo cáo.
5. Tạo screencast demo và lưu cùng chỉ mục minh chứng nếu yêu cầu nộp video.
