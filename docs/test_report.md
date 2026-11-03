# Báo cáo kiểm thử

## Thông tin lần kiểm thử

- **Ngày:** 03/11/2026
- **Bản:** thư mục làm việc cục bộ, sau khi cập nhật giao diện tím nhạt và thông tin liên hệ.
- **Trình duyệt:** Chromium trong VS Code Integrated Browser.
- **Cách mở:** `file:///C:/Users/hello/Downloads/CV-main/index.html`.
- **Phạm vi:** cấu trúc/nội dung, liên kết, layout responsive, chiều rộng tài liệu, CSS theme và trạng thái triển khai công khai.
- **Không thuộc phạm vi:** validator độc lập, kiểm thử Firefox/Safari/thiết bị thật, WCAG audit, Lighthouse, xâm nhập và backend.
- **Nguồn mã:** GitHub API cho thấy repository có lịch sử commit; commit mới nhất được quan sát là `4fdf961` ngày 27/10/2026. Các thay đổi trong thư mục làm việc hiện chưa có commit/push.

## Kết quả responsive đo được

Đo bằng `page.setViewportSize`, sau đó đọc `window.innerWidth`, `document.documentElement.clientWidth`, `document.documentElement.scrollWidth`, `gridTemplateColumns` và `flexDirection` trên trang hiện hành. Chênh lệch 15px giữa `innerWidth` và `clientWidth` là thanh cuộn dọc của trình duyệt; tiêu chí tràn ngang được xác định bằng `scrollWidth === clientWidth`. Ở cả năm viewport, không phần tử con nào có `scrollWidth > clientWidth + 1`.

| Viewport yêu cầu (CSS px) | `innerWidth` | `clientWidth` | `scrollWidth` | Cột dự án | Hero | Kết quả |
|---:|---:|---:|---:|---:|---|---|
| 360 | 360 | 345 | 345 | 1 | Dọc | Đạt, không tràn ngang |
| 375 | 375 | 360 | 360 | 1 | Dọc | Đạt, không tràn ngang |
| 768 | 768 | 753 | 753 | 2 | Ngang | Đạt, không tràn ngang |
| 1024 | 1024 | 1009 | 1009 | 2 | Ngang | Đạt, không tràn ngang |
| 1280 | 1280 | 1265 | 1265 | 3 | Ngang | Đạt, không tràn ngang |

Các số liệu trên là kết quả đọc DOM/CSS trong một phiên Chromium; không đại diện cho tất cả thiết bị vật lý hoặc trình duyệt.

## Ma trận kiểm thử chức năng và chất lượng

| ID | Hạng mục | Kết quả | Bằng chứng / nhận xét |
|---|---|---|---|
| T-01 | Tiêu đề tab và nội dung nhận diện | Đạt | Title, thương hiệu và H1 hiển thị “Phạm Thị Phương Thúy” |
| T-02 | Các phần nội dung chính | Đạt | Giới thiệu, Kỹ năng, Dự án, Liên hệ hiện diện |
| T-03 | Điều hướng và focus bàn phím | Đạt cơ bản | 4 mục nav đều có đích tồn tại; Tab đầu tiên focus liên kết thương hiệu với outline 2.4px. Chưa ghi nhận kiểm thử thủ công activation từng mục trên trình duyệt khác |
| T-04 | Email | Đạt | Hiển thị `phuongthuy7112008@gmail.com`, đích `mailto:` phù hợp |
| T-05 | GitHub | Đạt | Hiển thị `github.com/pthuyy711/CV`, href `https://github.com/pthuyy711/CV` |
| T-06 | LinkedIn | Đạt | Không còn mục LinkedIn trong giao diện |
| T-07 | Màu chủ đạo/nền | Đạt | CSS tokens dùng tím; nền body và vùng nhấn là tím nhạt |
| T-08 | Responsive | Đạt trong Chromium | Số cột và chiều rộng tài liệu theo bảng đo |
| T-09 | HTML ngữ nghĩa/ảnh | Đạt khi rà mã nguồn | Có landmarks; 5/5 ảnh có `alt`; chưa chạy validator độc lập |
| T-10 | GitHub Pages công khai | Chưa đạt | URL trả nội dung HTML nhưng vẫn hiển thị tên cũ “Nguyễn Văn An”; cần đồng bộ mã nguồn và xác minh sau deploy |
| T-11 | Hiệu năng | Chưa đo | Không báo điểm Lighthouse, thời gian tải hoặc Core Web Vitals khi chưa có phép đo |
| T-12 | Video/screencast | Chưa có | Chưa tạo tệp video; xem hướng dẫn tái lập trong `EVIDENCE_INDEX.md` |

## Lỗi, nguyên nhân và hành động

1. **Bản công khai lệch bản cục bộ.** Nguyên nhân: repository/Pages chưa nhận các thay đổi tên, email, GitHub và giao diện; môi trường làm việc không có Git và thư mục không phải Git repository. Hướng xử lý: đưa các tệp vào repository `pthuyy711/CV`, push lên `main`, bật Pages qua GitHub Actions, đợi deploy, rồi kiểm tra lại URL.
2. **Liên kết chi tiết dự án vẫn là `#`.** Nguyên nhân: chưa có URL dự án thật. Hướng xử lý: bổ sung URL/case study thật hoặc bỏ liên kết mẫu trước khi phát hành.
3. **Chưa có báo cáo accessibility/performance độc lập.** Hướng xử lý: chạy validator, Lighthouse, kiểm tra focus/zoom/tương phản và ghi phiên bản trình duyệt cùng kết quả.

## Tái lập phép đo responsive

Trong Chromium DevTools hoặc Playwright, với trang đang mở:

```js
await page.setViewportSize({ width: 360, height: 900 });
await page.evaluate(() => ({
  innerWidth,
  clientWidth: document.documentElement.clientWidth,
  scrollWidth: document.documentElement.scrollWidth,
  columns: getComputedStyle(document.querySelector(".project-grid"))
    .gridTemplateColumns.split(" ").length,
  heroDirection: getComputedStyle(document.querySelector(".hero-inner")).flexDirection
}));
```

Lặp lại với `width` là `375`, `768`, `1024`, `1280`. Đạt khi `scrollWidth === clientWidth`, không có phần tử con tràn ngang, cột dự án lần lượt `1/1/2/2/3`, hero `column` dưới 768px và `row` từ 768px.

## Kết luận

Bản cục bộ đạt các kiểm tra cấu trúc và layout responsive đã đo trong Chromium. Gói tài liệu và cấu hình triển khai đã được chuẩn bị. **Chưa thể nghiệm thu toàn bộ tiêu chí** vì GitHub Pages công khai còn là phiên bản cũ, chưa có Lighthouse/validator đa trình duyệt và chưa có screencast.