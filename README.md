# 🔍 Channel Scout — YouTube Channel Finder

Công cụ hỗ trợ quét, tìm kiếm và chọn lọc các kênh YouTube theo chủ đề hoặc dạng nội dung, lọc nhanh theo số lượng người đăng ký (Subscribers) và số video đã đăng, hỗ trợ xuất báo cáo định dạng Excel (`.xlsx`).

---

## 🚀 Các tính năng chính

- **Tìm kiếm theo từ khóa & chủ đề:** Quét các kênh liên quan trực tiếp đến ngách nội dung mục tiêu.
- **Bộ lọc linh hoạt:** Lọc kênh theo cận trên và cận dưới của số Subscriber và tổng số Video.
- **Sắp xếp thông minh:** Hỗ trợ sắp xếp theo độ liên quan, lượt xem hoặc ngày đăng ký kênh mới nhất.
- **Xuất dữ liệu Excel (.xlsx):** Tải về bảng danh sách chi tiết (Tên kênh, Link, ID, Subscribers, Videos, Tổng Views, Ngày tạo, Mô tả).
- **Tiết kiệm & minh bạch Quota:** Tối ưu số lượt gọi API theo từng trang kết quả.

---

## 🔑 Hướng dẫn lấy YouTube Data API Key miễn phí

Để sử dụng công cụ, bạn cần một **YouTube Data API Key** từ Google Cloud (hoàn toàn miễn phí, Google cấp 10.000 điểm quota/ngày):

1. Truy cập [Google Cloud Console](https://console.cloud.google.com/).
2. Nhấn vào mục chọn dự án ở góc trên cùng > chọn **New Project** > Đặt tên dự án (ví dụ: `YouTube Scout`) > Bấm **Create**.
3. Tại ô tìm kiếm trên cùng của Google Cloud, gõ tìm **`YouTube Data API v3`** > Chọn dịch vụ và bấm nút **Enable** (Bật).
4. Ở menu thanh bên trái, chọn **APIs & Services** > **Credentials**.
5. Nhấn **+ CREATE CREDENTIALS** > Chọn **API key**.
6. *(Khuyên dùng để bảo mật)*: Tại mục cấu hình key:
   - Mục **API restrictions**: Chọn **Restrict key** > Tích chọn duy nhất **YouTube Data API v3**.
   - Bấm **Create** (hoặc **Save**).
7. Sao chép đoạn mã khóa (bắt đầu bằng `AIzaSy...`) để sử dụng.

---

## 📖 Cách sử dụng công cụ

1. **Dán API Key:** Dán mã khóa API vừa tạo vào ô **YouTube Data API Key** (Khóa sẽ được lưu an toàn trên trình duyệt của bạn, không gửi về bất kỳ máy chủ nào khác).
2. **Nhập điều kiện tìm kiếm:**
   - **Từ khóa:** Nhập ngách bạn muốn tìm (VD: `reddit stories`, `tóm tắt sách`, `podcast tech`...).
   - **Số trang quét:** 1 trang tương ứng ~50 kênh (chọn 2–3 trang để có 100–150 kênh nghiên cứu).
   - **Bộ lọc Sub & Video:** Điền khoảng mong muốn (để trống nếu không giới hạn).
3. **Thực thi & Tải về:**
   - Nhấn **Tìm kênh**. Hệ thống sẽ tự động quét và phân loại danh sách.
   - Nhấn nút **Xuất Excel (.xlsx)** ở góc trên bảng kết quả để tải file về máy.

---

## 💡 Mẹo sử dụng hiệu quả & Tiết kiệm Quota

- **Cơ chế tính Quota:**
  - Lệnh tìm kiếm kênh (`search.list`): tốn **100 units** / trang (50 kênh).
  - Lệnh lấy chi tiết kênh (`channels.list`): tốn **1 unit** / đợt 50 kênh.
  - *Mỗi ngày bạn có 10.000 units, tương đương quét thoải mái khoảng 30 lượt (mỗi lượt 150 kênh).*
- **Toán tử tìm kiếm:**
  - Đặt trong ngoặc kép `" "` để tìm chính xác cụm từ (VD: `"bedtime stories"`).
  - Dùng dấu `-` phía trước từ không muốn xuất hiện (VD: `tóm tắt phim -shorts`).
- **Phát hiện kênh tăng trưởng nhanh:** Đặt bộ lọc **Subscribers từ 5.000 – 50.000** và **Videos từ 20 – 60** để tìm các kênh mới nổi có tỷ lệ tương tác và tiềm năng cao.
