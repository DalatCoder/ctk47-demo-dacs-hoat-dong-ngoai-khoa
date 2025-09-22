# EduActivities - Dashboard Layout Instructions

## Tổng quan về Dashboard Layout

**Mục đích:** Hướng dẫn thiết kế và phát triển layout chung cho tất cả các trang trong khu vực người dùng `/me`, đảm bảo tính nhất quán về UI/UX và functionality.

**Base Template:** `/me/dashboard.html` được sử dụng làm template gốc cho tất cả các trang con.

## Cấu trúc Layout Dashboard

### 1. Container Structure
```html
<div class="flex h-screen overflow-hidden">
  <!-- Sidebar -->
  <aside id="sidebar">...</aside>
  
  <!-- Overlay for mobile -->
  <div id="overlay">...</div>
  
  <!-- Main Content -->
  <div class="flex-1 flex flex-col overflow-hidden">
    <!-- Header -->
    <header>...</header>
    
    <!-- Main Content Area -->
    <main>...</main>
  </div>
</div>
```

### 2. Responsive Breakpoints
- **Mobile:** < 768px (lg:hidden sidebar, hamburger menu)
- **Tablet:** 768px - 1024px (collapsible sidebar)
- **Desktop:** > 1024px (fixed sidebar)

## Sidebar Navigation

### Kích thước và Styling
- **Width:** `w-64` (256px)
- **Background:** `bg-white`
- **Shadow:** `shadow-lg`
- **Mobile Transform:** `-translate-x-full` (hidden by default)

### Sections Structure

#### 1. Logo Section
```html
<div class="flex items-center justify-between p-6 border-b border-gray-200">
  <div class="flex items-center space-x-3">
    <div class="w-10 h-10 bg-primary rounded-lg flex items-center justify-center">
      <i class="fas fa-graduation-cap text-white text-xl"></i>
    </div>
    <div>
      <h1 class="text-lg font-bold text-gray-800">EduActivities</h1>
      <p class="text-xs text-gray-500">Sinh viên</p>
    </div>
  </div>
  <!-- Close button for mobile -->
</div>
```

#### 2. User Info Section
```html
<div class="p-4 border-b border-gray-200">
  <div class="flex items-center space-x-3">
    <div class="w-12 h-12 bg-gradient-to-r from-primary to-secondary rounded-full">
      <span class="text-white font-semibold text-lg">NV</span>
    </div>
    <div class="flex-1">
      <h3 class="font-semibold text-gray-800">Nguyễn Văn A</h3>
      <p class="text-sm text-gray-500">SV001234567</p>
    </div>
  </div>
</div>
```

#### 3. Primary Navigation
```html
<nav class="flex-1 px-4 py-6">
  <ul class="space-y-2">
    <!-- Navigation items -->
  </ul>
</nav>
```

**Navigation Items:**
- **Dashboard** - `fas fa-home` - `dashboard.html`
- **Hoạt động** - `fas fa-calendar-alt` - `activities.html`
- **Danh mục** - `fas fa-tags` - `categories.html`
- **Hồ sơ cá nhân** - `fas fa-user-circle` - `profile.html`

**Link Styling:**
```css
.nav-link {
  @apply flex items-center space-x-3 px-4 py-3 rounded-lg text-gray-700 hover:bg-primary hover:text-white transition duration-200;
}

.nav-link.active {
  @apply bg-primary text-white;
}
```

#### 4. Secondary Navigation
```html
<div class="mt-8">
  <h4 class="text-xs font-semibold text-gray-400 uppercase tracking-wider mb-4 px-4">Khác</h4>
  <ul class="space-y-2">
    <!-- Secondary items -->
  </ul>
</div>
```

**Secondary Items:**
- **Thông báo** - `fas fa-bell` - với badge đếm
- **Cài đặt** - `fas fa-cog`
- **Trợ giúp** - `fas fa-question-circle`

#### 5. Logout Section
```html
<div class="p-4 border-t border-gray-200">
  <a href="../login.html" class="flex items-center space-x-3 px-4 py-3 rounded-lg text-red-600 hover:bg-red-50 transition duration-200 w-full">
    <i class="fas fa-sign-out-alt"></i>
    <span>Đăng xuất</span>
  </a>
</div>
```

## Header Section

### Structure
```html
<header class="bg-white shadow-sm border-b border-gray-200">
  <div class="flex items-center justify-between px-6 py-4">
    <!-- Left: Menu toggle + Breadcrumb -->
    <!-- Center: Search bar -->
    <!-- Right: Notifications + User menu -->
  </div>
</header>
```

### Left Section - Navigation
- **Mobile Menu Button** - `fas fa-bars` - `lg:hidden`
- **Breadcrumb Navigation** - `hidden sm:flex`

```html
<nav class="hidden sm:flex" aria-label="Breadcrumb">
  <ol class="flex items-center space-x-2">
    <li>
      <a href="dashboard.html">
        <i class="fas fa-home"></i>
      </a>
    </li>
    <li class="flex items-center">
      <i class="fas fa-chevron-right text-gray-400 mx-2 text-sm"></i>
      <span id="currentPage" class="text-gray-700 font-medium">Dashboard</span>
    </li>
  </ol>
</nav>
```

### Center Section - Search
```html
<div class="hidden md:flex flex-1 max-w-md mx-8">
  <div class="relative w-full">
    <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
      <i class="fas fa-search text-gray-400"></i>
    </div>
    <input type="text" class="block w-full pl-10 pr-3 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary focus:border-primary outline-none transition duration-300" placeholder="Tìm kiếm hoạt động...">
  </div>
</div>
```

### Right Section - User Actions
- **Search Button** (mobile only) - `md:hidden`
- **Notifications** với badge
- **User Menu Dropdown**

```html
<div class="flex items-center space-x-4">
  <!-- Mobile search -->
  <button class="md:hidden text-gray-500 hover:text-gray-700">
    <i class="fas fa-search text-xl"></i>
  </button>

  <!-- Notifications -->
  <div class="relative">
    <button class="text-gray-500 hover:text-gray-700 relative">
      <i class="fas fa-bell text-xl"></i>
      <span class="absolute -top-1 -right-1 bg-red-500 text-white text-xs w-5 h-5 rounded-full">3</span>
    </button>
  </div>

  <!-- User Menu -->
  <div class="relative">
    <!-- User button + dropdown -->
  </div>
</div>
```

## Main Content Area

### Container Structure
```html
<main class="flex-1 overflow-x-hidden overflow-y-auto">
  <div class="container mx-auto px-6 py-8">
    <!-- Page Title -->
    <div class="mb-8">
      <h1 id="pageTitle" class="text-3xl font-bold text-gray-800">Page Title</h1>
      <p id="pageDescription" class="text-gray-600 mt-2">Page description</p>
    </div>

    <!-- Content will be inserted here -->
    <div id="pageContent">
      <!-- Page specific content -->
    </div>
  </div>
</main>
```

### Page Title Section
- **Heading:** `text-3xl font-bold text-gray-800`
- **Description:** `text-gray-600 mt-2`
- **Margin Bottom:** `mb-8`

### Content Area Guidelines
- **Container:** `container mx-auto px-6 py-8`
- **Grid Layouts:** Sử dụng CSS Grid cho responsive
- **Card Components:** `bg-white rounded-xl shadow-sm border border-gray-200`
- **Spacing:** Consistent `gap-6` hoặc `space-y-6`

## JavaScript Functions

### Required Global Functions

#### 1. Page Management
```javascript
// Update page title, description và breadcrumb
function updatePageInfo(title, description, breadcrumb) {
  document.getElementById('pageTitle').textContent = title;
  document.getElementById('pageDescription').textContent = description;
  document.getElementById('currentPage').textContent = breadcrumb || title;
  document.title = title + ' - EduActivities';
}

// Set page content
function setPageContent(content) {
  document.getElementById('pageContent').innerHTML = content;
}
```

#### 2. Navigation Management
```javascript
// Set active navigation item
function setActiveNav() {
  const currentPath = window.location.pathname;
  const navLinks = document.querySelectorAll('.nav-link');
  
  // Clear all active states
  navLinks.forEach(link => {
    link.classList.remove('bg-primary', 'text-white');
    link.classList.add('text-gray-700');
  });

  // Set active based on current page
  if (currentPath.includes('dashboard.html')) {
    document.getElementById('nav-dashboard').classList.add('bg-primary', 'text-white');
  }
  // Add other conditions...
}
```

#### 3. Mobile Menu Management
```javascript
// Sidebar toggle functions
function openSidebar() {
  sidebar.classList.remove('-translate-x-full');
  overlay.classList.remove('hidden');
  document.body.classList.add('overflow-hidden');
}

function closeSidebar() {
  sidebar.classList.add('-translate-x-full');
  overlay.classList.add('hidden');
  document.body.classList.remove('overflow-hidden');
}
```

## Component Styling Guidelines

### Card Components
```css
.dashboard-card {
  @apply bg-white rounded-xl p-6 shadow-sm border border-gray-200;
}

.stats-card {
  @apply bg-white rounded-xl p-6 shadow-sm border border-gray-200;
}

.stats-card-icon {
  @apply w-12 h-12 rounded-lg flex items-center justify-center;
}
```

### Color Coding System
- **Primary Actions:** `bg-primary` (#2563eb)
- **Success/Completed:** `bg-green-500` (#10b981)
- **Warning/Pending:** `bg-yellow-500` (#eab308)
- **Error/Important:** `bg-red-500` (#ef4444)
- **Info/Secondary:** `bg-purple-500` (#8b5cf6)
- **Neutral:** `bg-gray-500` (#6b7280)

### Icon Usage
- **Navigation Icons:** `text-xl` (20px)
- **Action Icons:** `text-lg` (18px)
- **Small Icons:** `text-sm` (14px)
- **Large Display Icons:** `text-2xl` (24px)

## Page Implementation Template

### Cách sử dụng cho trang mới:

1. **Copy toàn bộ dashboard.html**
2. **Thay đổi page-specific content trong `pageContent`**
3. **Update JavaScript initialization:**

```javascript
document.addEventListener('DOMContentLoaded', function() {
  // Update page info
  updatePageInfo('Page Title', 'Page Description', 'Breadcrumb');
  
  // Set active navigation
  setActiveNav();
  
  // Page specific initialization
  initPageSpecificFeatures();
});
```

### Ví dụ cho Activities Page:
```javascript
// activities.html specific
document.addEventListener('DOMContentLoaded', function() {
  updatePageInfo('Hoạt động ngoại khóa', 'Danh sách các hoạt động bạn có thể tham gia', 'Hoạt động');
  setActiveNav();
  loadActivitiesList();
});
```

## Responsive Design Rules

### Mobile (< 768px)
- Sidebar ẩn mặc định
- Search bar ẩn, hiện search button
- Breadcrumb ẩn
- User name ẩn trong header
- Grid layouts chuyển về 1 cột

### Tablet (768px - 1024px)
- Sidebar có thể toggle
- Search bar hiện
- Breadcrumb hiện
- Grid layouts 2 cột

### Desktop (> 1024px)
- Sidebar cố định
- Full layout hiện
- Grid layouts 3-4 cột

## Accessibility Requirements

### ARIA Labels Required
- Menu buttons: `aria-label="Open menu"`
- Close buttons: `aria-label="Close sidebar"`
- Search buttons: `aria-label="Search"`
- Navigation links: `aria-label` descriptions

### Keyboard Navigation
- Tab order logical
- Focus visible
- Escape key closes modals/dropdowns
- Enter/Space activates buttons

### Screen Reader Support
- Semantic HTML structure
- Proper heading hierarchy (h1 > h2 > h3)
- Alt text for icons with meaning
- ARIA live regions for dynamic content

## Performance Considerations

### CSS Optimization
- Sử dụng Tailwind CSS utilities
- Avoid custom CSS khi có thể
- Purge unused CSS trong production

### JavaScript Optimization
- Event delegation cho dynamic content
- Debounce search inputs
- Lazy load content khi cần thiết
- Minimize DOM queries

### Image Optimization
- Avatar placeholder thay vì loading images
- Icon fonts thay vì image icons
- Responsive images với proper sizing

## Quality Checklist

### Trước khi deploy page mới:

#### ✅ Layout & Design
- [ ] Sidebar navigation hoạt động đúng
- [ ] Header responsive proper
- [ ] Mobile menu toggle correctly
- [ ] Active nav highlighting works
- [ ] Page title/description updates
- [ ] Consistent spacing và typography

#### ✅ Functionality
- [ ] All JavaScript functions work
- [ ] Search functionality implemented
- [ ] User dropdown works
- [ ] Notifications display correctly
- [ ] Logout link works

#### ✅ Responsive Design
- [ ] Mobile layout acceptable
- [ ] Tablet layout works
- [ ] Desktop layout optimal
- [ ] Content overflow handled
- [ ] Touch targets appropriate size

#### ✅ Accessibility
- [ ] All buttons have labels
- [ ] Links have proper descriptions
- [ ] Keyboard navigation works
- [ ] Focus states visible
- [ ] Color contrast sufficient

#### ✅ Performance
- [ ] Page loads quickly
- [ ] No JavaScript errors
- [ ] Images optimized
- [ ] CSS minimal và clean

## File Organization

### Recommended Structure cho mỗi page:

```html
<!-- Copy từ dashboard.html -->
<!DOCTYPE html>
<html lang="vi">
<head>
  <!-- Standard head -->
</head>
<body>
  <!-- Standard layout structure -->
  
  <!-- Chỉ thay đổi nội dung trong pageContent -->
  <div id="pageContent">
    <!-- Page specific content here -->
  </div>
  
  <!-- Standard scripts + page specific scripts -->
  <script>
    // Standard functions
    // Page specific initialization
  </script>
</body>
</html>
```

### Maintain Consistency
- **Color scheme** identical across pages
- **Typography** consistent
- **Icon usage** standardized
- **Animation timing** same (duration-200, duration-300)
- **Spacing system** uniform (p-4, p-6, py-8, etc.)

## Future Extensibility

### Component System Ready
Layout được thiết kế để dễ dàng:
- Thêm navigation items mới
- Extend secondary menu
- Add new page types
- Implement role-based features
- Integrate with backend APIs

### Theme System Preparation
- CSS custom properties ready
- Color system well-defined
- Component-based architecture
- Easy customization points

Sử dụng file instructions này để đảm bảo tất cả các trang trong `/me` đều có trải nghiệm người dùng nhất quán và chuyên nghiệp!