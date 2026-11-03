# Portfolio CV - Phạm Thị Phương Thúy

Website portfolio CV tĩnh, xây dựng bằng HTML5 và CSS3, giới thiệu bản thân, kỹ năng, dự án và thông tin liên hệ. Giao diện dùng Flexbox, CSS Grid và thiết kế mobile-first.

## Trạng thái bàn giao

- **Mã nguồn trong thư mục này:** đã cập nhật nội dung, giao diện tím nhạt và tài liệu theo các tiêu chí bàn giao.
- **Kiểm thử responsive:** đã đo ở viewport 360, 375, 768, 1024 và 1280 CSS px bằng Chromium tích hợp.
- **GitHub Pages:** workflow GitHub Actions triển khai trang khi có thay đổi trên nhánh `main`. Sau khi đẩy mã nguồn, cần kiểm tra workflow và xác minh URL công khai.

## Tính năng và cấu trúc

- Các phần Giới thiệu, Kỹ năng, Dự án, Liên hệ và điều hướng nội trang.
- HTML ngữ nghĩa với `header`, `nav`, `main`, `section`, `article`, `figure` và `footer`.
- CSS được tách khỏi HTML; design token tập trung trong `:root`.
- Bố cục mobile-first: dự án 1 cột, từ 768px 2 cột, từ 1280px 3 cột.
- Hỗ trợ focus bàn phím, văn bản thay thế cho ảnh và tùy chọn giảm chuyển động.
- Không cần Node.js, npm, cơ sở dữ liệu hay thư viện phía trình duyệt.

## Cấu trúc thư mục

```text
CV-main/
├── index.html
├── README.md
├── CHANGELOG.md
├── BAOCAO-A2.1.docx
├── AI_LOG.md
├── docs/
│   ├── DESIGN_REPORT.md
│   ├── DEMO_SCRIPT.md
│   ├── EVIDENCE_INDEX.md
│   ├── test_report.md
│   └── screenshots/
├── assets/
│   ├── css/styles.css
│   └── img/avatar.jpg
└── .github/workflows/pages.yml
```

## Chạy cục bộ

Yêu cầu: trình duyệt hiện đại. Có thể mở `index.html` trực tiếp; khuyến nghị dùng máy chủ HTTP tĩnh.

### Windows PowerShell

```powershell
py -m http.server 8000
```

### macOS/Linux

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000), dừng máy chủ bằng `Ctrl+C`.

## Triển khai GitHub Pages

Workflow tại `.github/workflows/pages.yml` triển khai nội dung từ nhánh `main` lên GitHub Pages khi được đưa vào repository. Để hoàn tất:

1. Đẩy mã nguồn lên nhánh `main` của repository [pthuyy711/CV](https://github.com/pthuyy711/CV).
2. Trong **Settings → Pages**, đặt **Source** là **GitHub Actions** nếu repository chưa cấu hình nguồn này.
3. Chờ workflow **Deploy to GitHub Pages** chạy thành công.
4. Mở [https://pthuyy711.github.io/CV/](https://pthuyy711.github.io/CV/) và kiểm tra tên, email, GitHub, màu sắc, ảnh và các breakpoint.

## Tùy chỉnh

- Nội dung, metadata và liên kết: `index.html`.
- Màu sắc, typography, breakpoint và bố cục: `assets/css/styles.css`.
- Ảnh đại diện: thay `assets/img/avatar.jpg` bằng ảnh có quyền sử dụng.
- Các nút “Xem chi tiết” trong dự án hiện là liên kết `#`; cần thay bằng URL dự án thật trước khi phát hành.
- Email và GitHub trong trang là thông tin liên hệ do chủ sở hữu cung cấp. Liên kết GitHub hiện trỏ tới repository CV.

## Tài liệu bàn giao

- [Phân tích yêu cầu, wireframe và quyết định thiết kế](./docs/DESIGN_REPORT.md)
- [Báo cáo kiểm thử và các giới hạn đã xác nhận](./docs/test_report.md)
- [Chỉ mục minh chứng và cách tái lập](./docs/EVIDENCE_INDEX.md)
- [Kịch bản demo 7 phút và câu hỏi phản biện](./docs/DEMO_SCRIPT.md)
- [Nhật ký sử dụng AI](./AI_LOG.md)
- [Release notes](./CHANGELOG.md)
- [Báo cáo Word](./BAOCAO-A2.1.docx)

## Giới hạn đã biết

- Thẻ dự án là nội dung minh họa; các URL chi tiết chưa được cung cấp.
- Chưa có kết quả Lighthouse, validator HTML/CSS, kiểm thử đa trình duyệt thực tế hoặc screencast đính kèm.
- Kiểm tra hiện tại xác nhận cấu trúc và layout ở Chromium; không thay thế đánh giá WCAG đầy đủ hay kiểm thử trên thiết bị thật.
- Sau mỗi lần cập nhật nhánh `main`, xác minh workflow triển khai và trang công khai.
