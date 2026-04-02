# MathExam 12 — Hệ thống kiểm tra Toán

MathExam 12 là một ứng dụng web đơn trang (Single-Page Application) giúp giáo viên dễ dàng tạo các bài thi trắc nghiệm Toán học và học sinh có thể tham gia làm bài, nhận điểm ngay lập tức. Hệ thống hỗ trợ lưu trữ dữ liệu dạng Offline (trên trình duyệt) và Online (thông qua Firebase).

---

## 🌟 Chức Năng Chính

### 👨‍🏫 Dành cho Giáo Viên
1. **Tạo Đề Thi Mới:**
   - Hỗ trợ tạo đề thi với 3 dạng câu hỏi: 
     - Trắc nghiệm 4 đáp án (A, B, C, D).
     - Đúng / Sai.
     - Điền đáp án chính xác.
   - Thiết lập cấu hình đề thi: Tên bài kiểm tra, Thời gian làm bài (phút), và Chủ đề (Hàm số, Lượng giác, Tích phân...).
   - **Thêm nhanh từ File:** Tự động đọc và bóc tách câu hỏi từ file Word (`.docx`) hoặc Text (`.txt`).
2. **Quản Lý Đề Thi:**
   - Danh sách các đề thi đã tạo kèm theo Mã Đề (6 chữ số).
   - Dễ dàng Copy mã đề để gửi cho học sinh tham gia.
   - Xóa đề thi không còn cần thiết.
3. **Xem Kết Quả:**
   - Thống kê tự động kết quả của học sinh theo từng đề thi.
   - Xem chi tiết: Tên học sinh, Điểm số (thang điểm 10), Số câu đúng/tổng, Thời gian hoàn thành và Xếp loại.

### 🎓 Dành cho Học Sinh
1. **Tham Gia Thi Nhanh:**
   - Đăng nhập chỉ cần "Họ và Tên" và "Mã đề thi" (do giáo viên cung cấp).
   - Giao diện làm bài trực quan, dễ thao tác.
2. **Quá Trình Làm Bài:**
   - Đồng hồ đếm ngược thời gian.
   - Navigation bar giúp chuyển nhanh giữa các câu hỏi, xem câu nào đã làm/chưa làm.
   - Cảnh báo xác nhận khi nộp bài nếu có câu hỏi chưa hoàn thành.
3. **Kết Quả Tức Thì:**
   - Chấm điểm ngay sau khi nộp bài.
   - Hiển thị chi tiết số câu đúng, câu sai, thời gian đã dùng.

---

## 🚀 Hướng Dẫn Sử Dụng

### 1. Cài Đặt (Tùy chọn Online/Offline)
Ứng dụng có thể chạy hoàn toàn **Offline** ngay trên file `index.html` (dữ liệu lưu cục bộ trong LocalStorage của trình duyệt). Tuy nhiên, để Giáo viên và Học sinh có thể tương tác từ các thiết bị khác nhau, cần cấu hình Firebase.

**Cấu hình Firebase (Cho lưu trữ Online):**
- Mở file `index.html`.
- Tìm đến dòng cấu hình `firebaseConfig`.
- Nhập các khóa (Keys) Firebase Project của bạn vào.

### 2. Giáo Viên - Cách Tạo và Chia Sẻ Đề Thi
1. Truy cập trang chủ, chọn vai trò **Giáo viên**.
2. Ở tab **✏️ Tạo đề**: 
   - Điền Tên đề, thời gian, chủ đề.
   - Bấm **+ Thêm câu hỏi thủ công** hoặc sử dụng **Nhập tự động từ Word / TXT**.
   - Thiết lập nội dung câu hỏi và **click vào đáp án đúng**.
   - Nhấn **💾 Lưu đề kiểm tra**.
3. Chuyển sang tab **📋 Đề thi**:
   - Nhấn **📋 Copy Mã 6 chữ số** và gửi mã này cho học sinh.
4. Chuyển sang tab **📊 Kết quả** để đón xem điểm số của học sinh khi họ nộp bài.

### 3. Học Sinh - Cách Tham Gia Làm Bài
1. Truy cập trang chủ, chọn vai trò **Học sinh**.
2. Nhập **Họ và tên** của bạn.
3. Nhập **Mã đề thi** (Gồm 6 chữ số/chữ cái nhận từ Giáo Viên). Ví dụ: `TOAN01`.
4. Nhấn **Vào phòng thi →** và bắt đầu làm bài.
5. Kiểm tra thời gian, trả lời tất cả các câu, sau đó bấm **✓ Nộp bài**. Xem kết quả chi tiết hiển thị ra.

---

## 🛠 Công Nghệ Sử Dụng

- **HTML5, CSS3, JavaScript (Vanilla):** Xây dựng giao diện và logic (Không sử dụng Framework nặng, giúp ứng dụng chạy cực nhẹ trên một file duy nhất).
- **mammoth.js:** Thư viện hỗ trợ bóc tách nội dung text từ file Word `.docx` ngay trên trình duyệt.
- **Firebase Realtime Database:** Lưu trữ dữ liệu đề thi và kết quả của người dùng (nếu được kết nối key).
