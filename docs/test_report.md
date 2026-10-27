# Báo cáo kiểm thử

- **Ngày kiểm thử:** 27/10/2026
- **Đối tượng:** Website portfolio CV tĩnh
- **Cách chạy:** Mở `index.html` trực tiếp bằng trình duyệt tích hợp (`file://`).
- **Phạm vi:** Kiểm tra hiển thị và cấu trúc trang, tài nguyên cục bộ, liên kết nội bộ, kiểm tra tĩnh HTML/CSS và khả năng mở trang. Đây là kiểm thử thủ công, không thay thế kiểm thử đa trình duyệt, kiểm thử xâm nhập hoặc kiểm thử triển khai thực tế.

## Kết quả theo tiêu chí

| Tiêu chí | Kết quả | Minh chứng và nhận xét |
|---|---|---|
| **Tính đúng đắn** | Đạt cơ bản | Trang mở được; tiêu đề và bốn phần Giới thiệu, Kỹ năng, Dự án, Liên hệ hiển thị. CSS được tải, cả 5 ảnh tải thành công, các liên kết điều hướng nội bộ đều trỏ tới phần tử tồn tại. Nhấn Enter trên liên kết điều hướng tới Kỹ năng, Dự án và Liên hệ lần lượt cập nhật đúng fragment URL. Không ghi nhận lỗi JavaScript hoặc lỗi console trong lần chạy. Các liên kết dự án và GitHub/LinkedIn vẫn là `#`, chưa dẫn tới đích thực tế. Xem ảnh [đầu trang](./screenshots/top-view.png), [dự án](./screenshots/projects.png) và [liên hệ](./screenshots/contact.png). |
| **UI/UX** | Đạt một phần | Có điều hướng, nút kêu gọi hành động, bố cục thẻ dự án và ảnh có văn bản thay thế; CSS khai báo các breakpoint 768px và 1280px. Đã chụp giao diện ở viewport hẹp tại [mobile.png](./screenshots/mobile.png). Trình duyệt kiểm thử không giữ đúng kích thước yêu cầu: viewport đo được là 780 CSS px khi yêu cầu 1440px, và 225 CSS px khi yêu cầu 390px; vì vậy breakpoint desktop 1280px chưa được xác minh. Ở viewport hẹp, `scrollWidth` của trang lớn hơn viewport 1px. Kiểm thử click chuột tự động không ổn định do công cụ báo vùng chứa header chặn click; điều hướng bằng bàn phím đã được xác nhận. Cần kiểm tra lại trên trình duyệt/thiết bị thực tế. |
| **Khả năng vận hành - xử lý lỗi** | Đạt một phần | Mở trang bằng `file://` thành công và tài nguyên cục bộ tải được. Trang không có JavaScript, biểu mẫu hay xử lý dữ liệu động; do đó chưa có kịch bản lỗi nghiệp vụ để kiểm thử. Chưa mô phỏng lỗi thiếu tài nguyên, lỗi máy chủ hoặc lỗi mạng. |
| **Bảo mật** | Đạt trong phạm vi kiểm tra tĩnh | Trong HTML/CSS được kiểm tra, không thấy mã JavaScript, biểu mẫu nhập liệu, thư viện script bên thứ ba hoặc điểm nhận dữ liệu phía máy chủ. Đây chỉ là nhận xét theo phạm vi mã nguồn tĩnh; chưa thực hiện kiểm thử xâm nhập, rà soát cấu hình máy chủ hoặc đánh giá bảo mật toàn diện. |
| **Chất lượng mã nguồn** | Đạt một phần | HTML dùng các landmark và phần tử nội dung có ý nghĩa; ảnh có `alt`, CSS được tách riêng. Không có lỗi console trong lần chạy và không phát hiện đích neo nội bộ bị thiếu. Chưa có bộ kiểm thử tự động, linter hoặc validator HTML/CSS được cấu hình trong dự án. |
| **Khả năng triển khai** | Đạt một phần | Website tĩnh mở được trực tiếp và các tài nguyên tham chiếu tương đối đều tải được. README mô tả cách chạy bằng máy chủ HTTP tĩnh hoặc Docker/Nginx, nhưng chưa chạy thử máy chủ/Docker hay triển khai lên môi trường production trong lần kiểm thử này. |

## Ảnh minh chứng

Các ảnh dưới đây được chụp trực tiếp từ trang đang chạy trong trình duyệt và lưu trong `docs/screenshots/`:

- [Giao diện đầu trang](./screenshots/top-view.png)
- [Khu vực dự án](./screenshots/projects.png)
- [Khu vực liên hệ](./screenshots/contact.png)
- [Giao diện viewport hẹp](./screenshots/mobile.png)

## Kết luận

Các chức năng trình bày nội dung cơ bản và tải tài nguyên cục bộ hoạt động trong lần kiểm thử này. Trước khi phát hành nên thay các liên kết mẫu, kiểm tra lại responsive ở kích thước thiết bị phổ biến và chạy thử quy trình triển khai dự kiến. Các giới hạn về xử lý lỗi và bảo mật cần được đánh giá lại nếu bổ sung JavaScript, biểu mẫu, API hoặc máy chủ.