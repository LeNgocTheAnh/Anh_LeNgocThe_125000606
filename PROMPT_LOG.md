# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

**Họ và tên:** [Lê Ngọc Thế Anh]  
**MSSV:** [125000606]  
**Tên đề tài Website:** Cửa hàng thú cưng
**Công cụ AI đã sử dụng:** Antigravity, gemini

## 1. Yêu cầu ban đầu (System/Initial Prompt)
> *Hãy giúp tôi tạo mã nguồn HTML5 và CSS3 hoàn chỉnh cho trang web cửa hàng thú cưng (Pet Shop) với các yêu cầu: sử dụng đúng chuẩn Semantic HTML5 (<header>, <nav>, <main>, <section>, <footer>), không lạm dụng thẻ div vô nghĩa. Khai báo CSS Variables (:root) gồm primary-color (cam hồng), secondary-color (xanh ngọc), accent-color (vàng), 3 mức màu xám cho text và 1 màu nền. Bố cục dùng CSS Grid & Flexbox, Responsive với Media Queries (< 768px). Các phần gồm Header/Nav, Main (Hero với Animate.css, Section dịch vụ, Section sản phẩm nổi bật, Section đánh giá) và Footer. Kèm theo hiệu ứng hover/focus, hiệu ứng cuộn trang và chuyển đổi hamburger menu thành dấu "X" bằng CSS Transitions.*

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iterations)

### Lần 1: Dựng khung Semantic HTML & Design System (:root)
- **Prompt đã dùng:**
  > *"Hãy tạo file index.html và style.css cho trang Pet Paradise. Đảm bảo dùng các thẻ ngữ nghĩa chuẩn Semantic HTML5 (<header>, <nav>, <main>, <section>, <footer>), tuyệt đối không dùng div bừa bãi. Khai báo :root với các biến màu sắc: cam hồng (--primary-color), xanh ngọc (--secondary-color), vàng (--accent-color), 3 mức xám cho text và màu nền chung."*
- **Kết quả AI tạo ra:**
  AI đã thiết lập xong cấu trúc HTML5 cơ bản và khai báo đầy đủ các biến màu sắc trong `:root` theo đúng tông màu yêu cầu.
- **Nhận xét & Tinh chỉnh của SV:**
  Một số thẻ nội dung danh mục sản phẩm ban đầu AI dùng thẻ `<div>` và đã yêu cầu AI thay thế bằng thẻ `<section>` hoặc `<article>` để đúng chuẩn Semantic.

### Lần 2: Xây dựng Layout (Grid/Flexbox) & Responsive (< 768px)
- **Prompt đã dùng:**
  > *"Hãy viết CSS sử dụng CSS Grid và Flexbox để bố trí các section (Hero, Dịch vụ, Sản phẩm nổi bật, Đánh giá). Thêm Media Queries để trang web tự động điều chỉnh hiển thị tối ưu trên màn hình điện thoại dưới 768px."*
- **Thách thức gặp phải:**
  Khi thu nhỏ màn hình xuống dưới 768px, lưới sản phẩm nổi bật bị tràn ngang và menu điều hướng bị dồn ép, vỡ bố cục.
- **Cách sửa prompt (Debug prompt):**
  > *"Phần lưới sản phẩm bị tràn ngang trên màn hình nhỏ. Hãy sử dụng `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))` kết hợp với Media Query dưới 768px để ẩn menu ngang truyền thống, chuyển sang dạng menu di động phù hợp."*

### Lần 3: Tích hợp Hiệu ứng tương tác, Cuộn trang & Hamburger Menu
- **Prompt đã dùng:**
  > *"Hãy thêm hiệu ứng :hover và :focus mượt mà cho các nút bấm và thẻ cards. Tích hợp hiệu ứng xuất hiện cuộn trang sinh động cho các section và viết hiệu ứng chuyển đổi biểu tượng menu 3 gạch thành dấu 'X' một cách mượt mà bằng CSS Transitions khi người dùng bấm mở menu."*
- **Thách thức gặp phải:**
  Hiệu ứng chuyển đổi 3 gạch thành dấu "X" ban đầu bị lệch tâm và không mượt mà do thiếu thuộc tính căn chỉnh tâm cho các vạch (`span`).
- **Cách sửa prompt (Debug prompt):**
  > *"Biểu tượng hamburger menu chưa xoay thành dấu X chuẩn xác. Hãy viết lại CSS transition cho 3 thẻ `<span>` bên trong nút menu: khi có class `.active`, thanh giữa ẩn đi (`opacity: 0`), thanh trên xoay 45 độ và thanh dưới xoay -45 độ với thuộc tính `transform-origin` cố định để tạo tâm xoay hoàn hảo."*

## 3. Đánh giá cá nhân về quá trình Vibe Coding
- **AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?**
  AI giúp tiết kiệm rất nhiều thời gian trong việc viết các cấu trúc CSS Grid/Flexbox phức tạp, thiết lập nhanh chóng bộ biến màu sắc `:root` đồng bộ và phác thảo các đoạn CSS Transitions cho hiệu ứng hamburger menu.
- **Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web:**
  Cần mô tả rõ ràng các mốc kích thước Responsive, các yêu cầu kỹ thuật cụ thể (như cách xử lý biểu tượng menu hoặc quy chuẩn Semantic HTML) ngay từ đầu để AI không phải chỉnh sửa quá nhiều lần ở các bước sau.