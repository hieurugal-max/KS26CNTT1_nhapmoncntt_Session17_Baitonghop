(Bài tập tổng hợp) Ngày Đầu Thực Tập Dev Tại Công Ty Công Nghệ

Phần A - Thiết lập Profile và Bookmark chuẩn Dev
1. nếu dung chung 1 profile cho cả GitHub cá nhân và GitHub công ty thì dễ sảy ra xung đột đăng nhập bị nhầm tài khoản hoặc bị trộn lẫn dữ liệu, cần tchs riêng profile để đame bảo Data lsolation 

2. mô hình 3 Profile chuẩn Developer 
- Profile 1: Personal: Dùng GitHub cá nhân , Gmail cá nhân
- Profile 2: Company_work: Dùng GitHub công ty, gmail công ty
- Profile 3: Sanbox_Tesr: Dùng để kiểm thử website

3. Cấu trúc Bookmark gồm 3 thư mục
- Personal: Facebook, YouTube
- Company_Work: GitHub, Gmail
- Dev_Tools: Chrome Developers, JSON Formatter
4. Đồng nghiệp mượn máy

Cho đồng nghiệp sử dụng Guest Mode để không truy cập được dữ liệu, lịch sử và Bookmark cá nhân. Khi đóng cửa sổ Guest, dữ liệu phiên duyệt web sẽ bị xóa.

PHẦN B – CHỌN EXTENSION
1. Nhóm Extension

Chọn Dev Suite, sử dụng JSON Formatter để định dạng dữ liệu JSON thô thành cấu trúc dễ đọc
- Productivity Suite: Hỗ trợ quản lý công việc, ghi chú, không phù hợp
- Security Suite: Tập trung vào bảo mật, không giải quyết nhu cầu đọc JSON
2. Site Access

Chọn On click vì Extension chỉ hoạt động khi người dùng chủ động nhấn vào, hạn chế quyền truy cập không cần thiết trên các website khác.

PHẦN C – PHÂN TÍCH HTTP REQUEST
1. Bốn giai đoạn xử lý
- Bước 1 – DNS Resolution: Phân giải tên miền thành địa chỉ IP
- Bước 2 – TCP Connection / TLS Handshake: Thiết lập kết nối với máy chủ
- Bước 3 – HTTP Request / Response: Gửi yêu cầu và nhận phản hồi từ máy chủ
- Bước 4 – Browser Rendering: Trình duyệt phân tích HTML, CSS, JavaScript và hiển thị website
2. So sánh mã trạng thái HTTP

- 404 Not Found
- Ý nghĩa: Không tìm thấy tài nguyên
- Lỗi: URL sai hoặc API endpoint không tồn tại
- Debug: Kiểm tra URL và đường dẫn API
- 500 Internal Server Error
- Ý nghĩa: Máy chủ gặp lỗi nội bộ
- Lỗi: Thường nằm ở phía Backend/Server
- Debug: Kiểm tra Server Log và mã xử lý Backend
3. Tab xem mã trạng thái HTTP

Chọn Network vì tab này hiển thị Request, Response và Status Code

Các tab khác:
- Elements: Kiểm tra HTML, CSS
- Console: Kiểm tra lỗi JavaScript
- Application: Quản lý Cookies, Cache và Storage

PHẦN D – CHẨN ĐOÁN CACHE VÀ COOKIES
1. CSS đã sửa nhưng F5 vẫn thấy giao diện cũ

Nguyên nhân: Trình duyệt đang sử dụng file CSS cũ trong Cache.

Cách khắc phục:
- Mở F12 → Network.
- Tích Disable cache.
- Nhấn giữ Reload, chọn Empty Cache and Hard Reload.
2. Cookie session_id không bật HttpOnly

JavaScript có thể truy cập Cookie. Nếu website có lỗ hổng XSS (Cross-Site Scripting), kẻ tấn công có thể đánh cắp Session ID và thực hiện Session Hijacking.

3. Đăng xuất nhưng giữ Cache
- Mở F12 → Application → Cookies
- Chọn tên miền website
- Xóa Cookie session_id
- Tải lại trang.
Kết quả: Phiên đăng nhập bị xóa nhưng Cache ảnh và CSS vẫn được giữ

PHẦN E – DEBUG BẰNG INSPECT ELEMENT VÀ NETWORK
1. Kiểm tra màu nút Đăng nhập
- Mở F12 → Elements.
- Chọn biểu tượng Select Element và nhấn vào nút Đăng nhập
- Tìm thuộc tính background-colo
- Thay đổi mã màu trực tiếp trong CSS
- Quan sát kết quả và ghi lại mã màu đúng để báo cho Dev
Lưu ý: Chỉ chỉnh sửa trên trình duyệt, không sửa file CSS gốc

2. Quy trình 4 bước Debugging
- Bước 1 – Identify: Xác định Request bị lỗi trên Network
- Bước 2 – Inspect: Kiểm tra URL, Method, Status Code, Headers và Response
- Bước 3 – Analyze: Phân tích nguyên nhân lỗi dựa trên thông tin nhận được
- Bước 4 – Verify: Kiểm tra lại Request sau khi Dev xử lý để xác nhận lỗi đã được khắc phục
3. Hai thao tác trên Network
- Chọn Fetch/XHR để chỉ xem các API Request
