# Portfolio CV - Nguyễn Văn An

## 1. Giới thiệu

Portfolio CV cá nhân dành cho Frontend Developer, được xây dựng dưới dạng website tĩnh. Trang giới thiệu thông tin cá nhân, kỹ năng, các dự án tiêu biểu và phương thức liên hệ; bố cục hỗ trợ màn hình điện thoại, máy tính bảng và máy tính.

## 2. Chức năng

- Hiển thị phần giới thiệu và ảnh đại diện.
- 
- Hiển thị các dự án mẫu cùng mô tả và công nghệ sử dụng.
- Điều hướng nhanh tới các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Cung cấp liên kết email, GitHub và LinkedIn.
- Bố cục responsive, dùng Flexbox và CSS Grid.

## 3. Công nghệ

- HTML5: cấu trúc nội dung và các phần tử ngữ nghĩa.
- CSS3: giao diện, responsive, Flexbox và CSS Grid.
- Nginx (tùy chọn): phục vụ website khi chạy bằng Docker.

Dự án không cần Node.js, npm, cơ sở dữ liệu hoặc thư viện bên ngoài để chạy.

## 4. Yêu cầu môi trường

- Trình duyệt hiện đại như Chrome, Firefox, Edge hoặc Safari.
- Để chạy bằng máy chủ cục bộ: Python 3 (hoặc một máy chủ HTTP tĩnh tương đương).
- Để chạy bằng Docker: Docker Engine hoặc Docker Desktop đang hoạt động.
- Mã nguồn và tài nguyên ảnh nằm đúng cấu trúc thư mục của dự án.

## 5. Cấu trúc dự án

```text
CV-main/
├── index.html
├── README.md
└── assets/
	├── css/
	│   └── styles.css
	└── img/
		└── avatar.jpg
```

## 6. Cài đặt

### Windows

1. Tải hoặc clone mã nguồn về máy.
2. Mở PowerShell trong thư mục dự án, nơi có tệp `index.html`.
3. Nếu dùng Python, kiểm tra cài đặt:

```powershell
py --version
```

Nếu lệnh `py` không có, thử `python --version`. Cài Python 3 nếu cả hai lệnh đều không hoạt động.

### macOS

1. Tải hoặc clone mã nguồn về máy.
2. Mở Terminal và chuyển tới thư mục dự án.
3. Kiểm tra Python 3:

```bash
python3 --version
```

Cài Python 3 nếu máy chưa có.

### Linux

1. Tải hoặc clone mã nguồn về máy.
2. Mở Terminal và chuyển tới thư mục dự án.
3. Kiểm tra Python 3:

```bash
python3 --version
```

Nếu chưa có, cài Python 3 bằng trình quản lý gói của bản phân phối Linux đang sử dụng.

## 7. Cấu hình và tùy chỉnh

Dự án hiện không có tệp cấu hình môi trường hoặc biến môi trường cần thiết.

- Chỉnh nội dung, tiêu đề trang, mô tả, thông tin cá nhân và các liên kết trong `index.html`.
- Thay ảnh `assets/img/avatar.jpg` bằng ảnh của bạn; giữ nguyên tên và đường dẫn, hoặc cập nhật thuộc tính `src` trong `index.html`.
- Chỉnh màu sắc, kiểu chữ và bố cục trong `assets/css/styles.css`.
- Thay email mẫu `an.nguyen@example.com` cùng các liên kết GitHub/LinkedIn dạng mẫu bằng thông tin thật trước khi phát hành.
- Các liên kết dự án hiện là nội dung minh họa; cập nhật `href` của từng liên kết khi có trang dự án thực tế.

## 8. Chạy thử

### Windows (PowerShell)

Chạy tại thư mục dự án:

```powershell
py -m http.server 8000
```

Nếu dùng lệnh `python` thay cho `py`:

```powershell
python -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000) trên trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### macOS và Linux

Chạy tại thư mục dự án:

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000) trên trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### Mở trực tiếp

Có thể mở `index.html` trực tiếp bằng trình duyệt. Dùng máy chủ HTTP cục bộ được khuyến nghị để kiểm tra website trong môi trường gần với lúc triển khai hơn.

## 9. Chạy bằng Docker

Không cần tạo Dockerfile: lệnh dưới đây dùng Nginx image có sẵn và mount thư mục dự án ở chế độ chỉ đọc.

Yêu cầu: cài và khởi động Docker Desktop (Windows/macOS) hoặc Docker Engine (Linux).

### Windows (PowerShell)

Chạy trong thư mục dự án:

```powershell
docker run --rm -d --name cv-portfolio -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

Mở [http://localhost:8080](http://localhost:8080). Dừng container bằng:

```powershell
docker stop cv-portfolio
```

### macOS và Linux

Chạy trong thư mục dự án:

```bash
docker run --rm -d --name cv-portfolio -p 8080:80 -v "$PWD:/usr/share/nginx/html:ro" nginx:alpine
```

Mở [http://localhost:8080](http://localhost:8080). Dừng container bằng:

```bash
docker stop cv-portfolio
```

Nếu cổng `8080` đang được sử dụng, đổi phần `8080:80` thành một cổng trống khác, ví dụ `8081:80`, rồi mở cổng đó trên trình duyệt.

## 10. Thông tin liên hệ

Thông tin đang hiển thị trong trang là dữ liệu minh họa:

- Tên: Nguyễn Văn An
- Email: an.nguyen@example.com
- GitHub: github.com/nguyenvanan
- LinkedIn: linkedin.com/in/nguyenvanan

Hãy cập nhật thông tin trong `index.html` trước khi sử dụng hoặc phát hành website. Các liên kết GitHub và LinkedIn hiện là liên kết mẫu.
