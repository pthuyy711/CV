# AI_LOG

## Khai báo sử dụng công cụ AI

Tài liệu này ghi nhận minh bạch phần hỗ trợ AI trong quá trình chỉnh sửa gói portfolio. Chủ sở hữu cần đọc, xác nhận nội dung cá nhân và tự chịu trách nhiệm với thông tin trước khi phát hành.

| Ngày | Công cụ / vai trò | Phạm vi hỗ trợ | Xác minh của con người |
|---|---|---|---|
| 03/11/2026 | Copilot SDK trong VS Code | Hỗ trợ biên tập README, báo cáo thiết kế/kiểm thử, chỉ mục bằng chứng, kịch bản demo và release notes theo rubric được cung cấp | Đối chiếu mô tả với cấu trúc tệp, đo layout trong Chromium và rà trạng thái URL công khai |
| 03/11/2026 | Copilot SDK trong VS Code | Soạn workflow GitHub Pages để đóng gói `index.html` và `assets/` khi push nhánh `main`; dùng trình duyệt tích hợp chụp ảnh minh chứng giao diện cục bộ | Workflow được ghi rõ là chưa chạy trên repository; cần chủ sở hữu đồng bộ và xác minh; ảnh chụp cần được đối chiếu với viewport/phiên bản ghi trong evidence index |
| 03/11/2026 | Copilot SDK trong VS Code | Cập nhật tóm tắt báo cáo Word hiện có và tạo lại ảnh giao diện bằng Microsoft Edge headless | Kiểm tra XML bên trong gói DOCX; xem trực tiếp ảnh và xác nhận kích thước PNG |

## Giới hạn và trách nhiệm

- AI không tạo ra các dự án thật, số điểm Lighthouse, kết quả validator, video hoặc commit. Ảnh chụp được tạo bằng công cụ trình duyệt tích hợp và Microsoft Edge headless từ giao diện cục bộ.
- Số đo viewport trong báo cáo lấy từ DOM/CSS của Chromium tích hợp trong phiên làm việc; cần tái lập nếu môi trường thay đổi.
- URL Pages được truy cập chỉ để xác nhận trạng thái công khai; nội dung trang lúc kiểm tra vẫn là phiên bản cũ.
- Không đưa bí mật/credentials vào mã nguồn hoặc tài liệu.
- Trước khi nộp, chủ sở hữu cần kiểm tra quyền dùng ảnh, thông tin liên hệ, nội dung dự án và các tuyên bố trong báo cáo.
