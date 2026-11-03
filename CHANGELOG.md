# Release notes

## v1.1 - 03/11/2026

### Thay đổi

- Cập nhật tên hiển thị thành Phạm Thị Phương Thúy.
- Cập nhật email liên hệ và liên kết GitHub; bỏ mục LinkedIn.
- Đổi màu chủ đạo sang tím và nền sang tím nhạt.
- Bổ sung workflow GitHub Actions để triển khai trang tĩnh lên GitHub Pages từ nhánh `main`.
- Hoàn thiện README, báo cáo thiết kế/kiểm thử, AI log, evidence index và kịch bản demo 7 phút.

### Kiểm chứng

- Đo layout trong Chromium tại viewport 360, 375, 768, 1024 và 1280 CSS px.
- Xác nhận không có tràn ngang theo `scrollWidth === clientWidth`; lưới dự án lần lượt 1, 1, 2, 2 và 3 cột.
- Trang GitHub Pages công khai chưa được cập nhật theo bản này; URL vẫn hiển thị phiên bản cũ.

### Hạn chế còn lại

- Thẻ dự án và liên kết “Xem chi tiết” là nội dung minh họa; các URL hiện chưa trỏ tới dự án thật.
- Chưa có deploy thành công của workflow mới, screencast, Lighthouse, validator độc lập hoặc kiểm thử đa trình duyệt/thiết bị thật.
- Website là trang tĩnh, không có chức năng ứng dụng tương tác hay backend.

## v1.0 - 27/10/2026

### Phát hành ban đầu

- Ra mắt website portfolio CV tĩnh, responsive, dùng HTML5 và CSS3.
- Hiển thị Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Hỗ trợ chạy bằng máy chủ HTTP tĩnh hoặc Docker/Nginx.