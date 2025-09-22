# EduActivities - Hướng dẫn Thiết kế và Phát triển

## Tổng quan về Dự án

**Tên dự án:** EduActivities - Hệ thống Quản lý Hoạt động Ngoại khóa

**Mục đích:** Nền tảng toàn diện giúp sinh viên tham gia, theo dõi và quản lý các hoạt động ngoại khóa một cách dễ dàng và tiện lợi trong môi trường giáo dục.

## Cấu trúc Thư mục và Định tuyến

### Trang chính
- `/` (index.html) - Landing page giới thiệu chung về phần mềm
- `/login.html` - Trang đăng nhập

### Khu vực Người dùng (/me)
Sau khi đăng nhập thành công, người dùng được chuyển hướng đến:
- `/me/` - Dashboard cá nhân
- `/me/categories` - Danh mục hoạt động
- `/me/activities` - Các hoạt động ngoại khóa
- `/me/profile` - Trang cá nhân

### Khu vực Quản trị (/admin)
Dành cho người dùng có quyền quản trị:
- `/admin/` - Dashboard chung
- `/admin/users` - Quản lý danh sách người dùng

## Tính năng Chính

### 1. Quản lý Hoạt động
- **Mục đích:** Tạo, chỉnh sửa và theo dõi các hoạt động ngoại khóa
- **Giao diện:** Trực quan và dễ sử dụng
- **Icon:** fas fa-calendar-alt
- **Màu:** Primary blue (#2563eb)

### 2. Quản lý Thành viên
- **Mục đích:** Theo dõi danh sách sinh viên tham gia, điểm danh và đánh giá hiệu suất
- **Phương pháp:** Hệ thống sistemát
- **Icon:** fas fa-users
- **Màu:** Green (#10b981)

### 3. Báo cáo & Thống kê
- **Mục đích:** Xem báo cáo chi tiết về tình hình tham gia và hiệu quả
- **Dữ liệu:** Các hoạt động ngoại khóa
- **Icon:** fas fa-chart-line
- **Màu:** Purple (#8b5cf6)

### 4. Hệ thống Thông báo
- **Mục đích:** Nhận thông báo về các hoạt động mới, thay đổi lịch trình
- **Loại thông báo:** Cập nhật quan trọng
- **Icon:** fas fa-bell
- **Màu:** Red (#ef4444)

### 5. Phân loại Hoạt động
- **Mục đích:** Tổ chức các hoạt động theo danh mục
- **Lợi ích:** Dễ dàng tìm kiếm và quản lý
- **Icon:** fas fa-tags
- **Màu:** Yellow (#eab308)

### 6. Hồ sơ Cá nhân
- **Mục đích:** Quản lý thông tin cá nhân và theo dõi lịch sử tham gia
- **Dữ liệu:** Các hoạt động ngoại khóa đã tham gia
- **Icon:** fas fa-user-circle
- **Màu:** Indigo (#6366f1)

## Quy trình Sử dụng (User Journey)

### Bước 1: Đăng ký & Đăng nhập
- Tạo tài khoản mới hoặc đăng nhập bằng thông tin sinh viên
- Truy cập vào hệ thống

### Bước 2: Khám phá Hoạt động
- Duyệt qua danh sách các hoạt động ngoại khóa
- Chọn những hoạt động phù hợp với sở thích cá nhân

### Bước 3: Tham gia & Theo dõi
- Đăng ký tham gia hoạt động
- Theo dõi tiến trình thông qua dashboard cá nhân

## Thiết kế UI/UX

### Màu sắc chính
- **Primary:** #2563eb (Blue)
- **Secondary:** #1e40af (Dark Blue)
- **Accent:** #fbbf24 (Yellow)
- **Background:** #f9fafb (Gray-50)
- **Text:** #1f2937 (Gray-800)

### Typography
- **Font family:** System fonts (Tailwind default)
- **Headings:** Font weight bold
- **Body text:** Font weight normal
- **Accent text:** Font weight semibold

### Layout Principles
- **Responsive Design:** Mobile-first approach
- **Grid System:** CSS Grid và Flexbox
- **Spacing:** Consistent padding và margin
- **Cards:** Rounded corners với shadow
- **Buttons:** Rounded với hover effects

### Icons
- **Library:** FontAwesome 6.0.0
- **Style:** Solid icons (fas)
- **Sizes:** text-xl (20px) và text-2xl (24px)

## Công nghệ Sử dụng

### Frontend
- **HTML5:** Semantic markup
- **CSS:** Tailwind CSS framework
- **JavaScript:** Vanilla JS cho interactive elements
- **Icons:** FontAwesome
- **Responsive:** Mobile-first design

### Features
- **Smooth Scrolling:** Navigation mượt mà
- **Mobile Menu:** Hamburger menu cho mobile
- **Hover Effects:** Transition animations
- **Accessibility:** ARIA labels và semantic HTML

## Tầm nhìn và Sứ mệnh

### Tầm nhìn
EduActivities được thiết kế đặc biệt cho môi trường giáo dục, nhằm hỗ trợ việc phát triển toàn diện của sinh viên không chỉ về mặt học thuật mà còn về kỹ năng sống, kỹ năng xã hội và phát triển cá nhân.

### Sứ mệnh
Với giao diện thân thiện, tính năng mạnh mẽ và khả năng tùy biến cao, EduActivities giúp các tổ chức giáo dục quản lý hiệu quả các chương trình ngoại khóa, đồng thời mang lại trải nghiệm tuyệt vời cho sinh viên trong việc khám phá và tham gia các hoạt động phù hợp với sở thích và mục tiêu cá nhân.

## Hướng dẫn Phát triển

### Quy tắc Naming
- **Files:** lowercase với dấu gạch ngang (kebab-case)
- **CSS Classes:** Tailwind conventions
- **IDs:** camelCase cho JavaScript
- **Variables:** camelCase

### Responsive Breakpoints
- **Mobile:** < 768px
- **Tablet:** 768px - 1024px
- **Desktop:** > 1024px

### Performance Optimization
- **Images:** Optimize và lazy loading
- **CSS:** Purge unused Tailwind classes
- **JavaScript:** Minimize và defer loading
- **CDN:** Sử dụng cho external libraries

### Accessibility Guidelines
- **ARIA Labels:** Cho interactive elements
- **Semantic HTML:** Sử dụng đúng HTML tags
- **Color Contrast:** Đảm bảo contrast ratio
- **Keyboard Navigation:** Tab index và focus states

## Cấu trúc File Dự án

```
/
├── index.html              # Landing page
├── login.html              # Trang đăng nhập
├── instructions.md         # File hướng dẫn này
├── admin/
│   ├── dashboard.html      # Admin dashboard
│   └── users.html          # Quản lý users
└── me/
    ├── dashboard.html      # User dashboard
    ├── activities.html     # Danh sách hoạt động
    ├── categories.html     # Danh mục hoạt động
    └── profile.html        # Hồ sơ cá nhân
```

## Checklist Phát triển

### Landing Page ✅
- [x] Header với navigation
- [x] Hero section
- [x] Features showcase
- [x] How it works
- [x] About section
- [x] Call-to-action
- [x] Footer
- [x] Mobile responsive
- [x] Accessibility

### Cần phát triển
- [ ] Trang đăng nhập
- [ ] Dashboard người dùng
- [ ] Quản lý hoạt động
- [ ] Quản lý danh mục
- [ ] Hồ sơ cá nhân
- [ ] Admin dashboard
- [ ] Quản lý users
- [ ] Backend API
- [ ] Database design
- [ ] Authentication system

## Ghi chú Quan trọng

1. **Consistent Branding:** Sử dụng logo và tên "EduActivities" một cách nhất quán
2. **User Experience:** Ưu tiên trải nghiệm người dùng đơn giản và trực quan
3. **Performance:** Tối ưu tốc độ tải trang
4. **Security:** Bảo mật thông tin sinh viên
5. **Scalability:** Thiết kế có thể mở rộng trong tương lai