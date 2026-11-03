# Chỉ mục minh chứng

## Ảnh giao diện

| Tệp | Nội dung | Cách tái lập |
|---|---|---|
| [top-view.png](./screenshots/top-view.png) | Đầu trang: nhận diện, hero, kỹ năng và đầu lưới dự án (PNG 1440 × 900) | Chụp Edge headless tại viewport 1440 × 900 |
| [projects.png](./screenshots/projects.png) | Khu vực bốn thẻ dự án (PNG 1440 × 1040) | Cắt section `#projects` từ ảnh Edge headless |
| [contact.png](./screenshots/contact.png) | Email, GitHub và biểu mẫu liên hệ (PNG 1440 × 840) | Cắt section `#contact` từ ảnh Edge headless |
| [mobile.png](./screenshots/mobile.png) | Điều hướng và hero ở viewport hẹp (PNG 390 × 844) | Chụp Edge headless tại viewport 390 × 844 |

Ảnh là ảnh chụp trình duyệt của bản cục bộ; không chứng minh trạng thái GitHub Pages. Kích thước bảng là kích thước tệp PNG, không thay thế số đo CSS viewport trong báo cáo kiểm thử. Chụp lại nếu HTML/CSS thay đổi đáng kể hoặc nếu ảnh không còn đồng bộ với phiên bản đang kiểm thử.

## Bằng chứng đo được

- Bảng viewport và các phép đo DOM/CSS: [test_report.md](./test_report.md).
- URL công khai đã kiểm tra: [https://pthuyy711.github.io/CV/](https://pthuyy711.github.io/CV/). Tại lần kiểm tra ngày 03/11/2026, trang vẫn hiển thị tên “Nguyễn Văn An”; đây là bằng chứng triển khai chưa đồng bộ, không phải ảnh của bản mới.
- Repository: [https://github.com/pthuyy711/CV](https://github.com/pthuyy711/CV). Lịch sử từ GitHub API có 4 commit; commit mới nhất được quan sát là `4fdf961` ngày 27/10/2026. Đây chỉ là lịch sử remote trước các sửa đổi hiện tại; không có commit mới nào được tạo trong phiên làm việc này.
- Workflow Pages: [.github/workflows/pages.yml](../.github/workflows/pages.yml). Cấu hình đã có trong thư mục làm việc; chưa có run/deploy thành công của phiên bản này.

## Tái lập ảnh chụp

1. Chạy `py -m http.server 8000` (Windows) hoặc `python3 -m http.server 8000` (macOS/Linux) tại thư mục gốc.
2. Mở `http://localhost:8000` bằng Chromium.
3. Dùng trình duyệt desktop để chụp đầu trang; dùng screenshot theo selector cho `#projects` và `#contact`. Kích thước PNG có thể khác theo device scale factor.
4. Chạy Microsoft Edge headless với `--window-size=390,844` để chụp `mobile.png` thành ảnh 390 × 844.
5. Ghi lại ngày, trình duyệt, kích thước CSS và commit/ref nếu có. Không gắn nhãn “production” cho ảnh chụp từ `localhost` hoặc `file://`.

## Minh chứng còn thiếu trước khi nghiệm thu

- Ảnh/screencast từ URL GitHub Pages sau khi cập nhật.
- Kết quả run GitHub Actions thành công và URL deployment.
- Lighthouse hoặc công cụ đo hiệu năng, nếu rubric yêu cầu chỉ số.
- HTML/CSS validation và kiểm tra thủ công bàn phím, zoom 200%, trình duyệt/thiết bị bổ sung.
- Screencast demo 7 phút. Chưa có video trong thư mục bàn giao.
