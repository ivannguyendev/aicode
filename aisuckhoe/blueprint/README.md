# Blueprint - Phát triển website aisuckhoe

### Prompts:

```md
Dựng langdingpage cho website domain aisuckhoe.com
ứng dụng về bệnh nhân hỏi AI, AI trả lời vấn đề sức khoè và gợi ý bác sĩ phù hợp
nội dung: bác sĩ giỏi, nguồn uy tín, nhanh chóng, tiện lợi
Trang sẽ ngắn gọn và tập trung hơn vào mục tiêu chính là giới thiệu sản phẩm và chuyển đổi người dùng.
---
Các tính năng chính:
Header với logo và navigation menu
Hero section với 3D animation của AI/Robot y tế
---
Các section giới thiệu tính năng chính: 
Tư vấn AI thông minh
Kết nối bác sĩ uy tín
Tiện lợi & nhanh chóng
FAQ section
Footer với đầy đủ navigation
2 nút CTA chính dẫn đến webapp và telegram
Dark/Light mode toggle
Responsive trên mọi thiết bị
---
Các hiệu ứng đặc biệt:
Particle animation trong background
3D model bác sĩ/robot AI xoay 360° trong hero section
Floating animation cho các cards
Smooth scroll animations
Hover effects trên buttons và cards
Loading skeleton cho dynamic content
Micro-interactions trên các interactive elements
---
công nghệ sử dụng:
Tailwind CSS cho styling
Có thể dùng thêm thư viện khác
---
Cấu trúc:
Layout tổng thể mới:
Header (Fixed - Simplified)
|-----------------------------------------------------------------------------|
| Logo | Health Blog | Tech Blog | Roadmap | 🌙/☀️ | SignIn/SignUp |
|-----------------------------------------------------------------------------|
Hero Section
|---------------------------|
|   Text + CTA buttons     |
|    ___________________   |
|   |                   |  |
|   |   3D Doctor/AI    |  |
|   |   Animation       |  |
|   |___________________| |
|---------------------------|
Features Section (Grid 3 columns)
|-------|-------|-------|
| AI    | Bác sĩ| Tiện  |
| Thông | Uy    | lợi   |
| minh  | tín   |       |
|-------|-------|-------|
How It Works (Timeline)
Step 1 → Step 2 → Step 3
FAQ Section (Accordion)
|--------------------------|
| Question 1              ˅|
|--------------------------|
| Question 2              ˅|
|--------------------------|
Available on (Hero Section)
|---------------------------|
|   Text + [Web App] Buttons   |
|    ___________________   |
|   |                   |  |
|   |   Chat on Webapp  |  |
|   |   Animation       |  |
|   |___________________| |
|---------------------------|

|---------------------------|
|    ___________________   |
|   |                   |  |
|   |  Chat on Telegram |  |
|   |   Animation       |  |
|   |___________________|  |
|   Text + [Telegram] Buttons   |
|---------------------------|
CTA Section
|--------------------------|
|     Hỏi AI ngay!        |
| [Web App] [Telegram]    |
|--------------------------|
Footer
|--------------------------|
| About | Contact | Terms  |
| Social| Privacy | Others |
|--------------------------|


Cho tôi xem phác thảo trước khi bắt đầu.
```



### AI Responses:
```html
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>(blueprint) AI Sức Khỏe - Tư vấn y tế thông minh</title>
  <style>
    :root {
      --primary: #3b82f6;
      --secondary: #10b981;
      --dark: #1e293b;
      --light: #f8fafc;
      --accent: #8b5cf6;
    }
    
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      padding: 0;
      background-color: var(--light);
      color: var(--dark);
    }
    
    .dark-mode {
      --light: #0f172a;
      --dark: #f8fafc;
      background-color: var(--light);
      color: var(--dark);
    }
    
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 1rem;
    }
    
    .btn {
      padding: 0.75rem 1.5rem;
      border-radius: 0.5rem;
      font-weight: bold;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
      transition: all 0.3s ease;
    }
    
    .btn-primary {
      background-color: var(--primary);
      color: white;
    }
    
    .btn-secondary {
      background-color: var(--secondary);
      color: white;
    }
    
    .btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    }
    
    /* Header */
    header {
      padding: 1rem 0;
      position: fixed;
      width: 100%;
      top: 0;
      background-color: var(--light);
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      z-index: 100;
    }
    
    .header-content {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    
    .logo {
      font-size: 1.5rem;
      font-weight: bold;
      color: var(--primary);
    }
    
    .nav-links {
      display: flex;
      gap: 1.5rem;
      align-items: center;
    }
    
    .nav-link {
      text-decoration: none;
      color: var(--dark);
      font-weight: 500;
    }
    
    .theme-toggle {
      background: none;
      border: none;
      font-size: 1.2rem;
      cursor: pointer;
      color: var(--dark);
      margin: 0 1rem;
    }
    
    /* Hero Section */
    .hero {
      padding: 8rem 0 4rem;
      display: flex;
      align-items: center;
      position: relative;
      overflow: hidden;
    }
    
    .hero-content {
      width: 50%;
      z-index: 2;
    }
    
    .hero-title {
      font-size: 3rem;
      font-weight: bold;
      margin-bottom: 1rem;
      background: linear-gradient(45deg, var(--primary), var(--accent));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }
    
    .hero-subtitle {
      font-size: 1.2rem;
      margin-bottom: 2rem;
      color: var(--dark);
      opacity: 0.9;
    }
    
    .hero-cta {
      display: flex;
      gap: 1rem;
    }
    
    .hero-3d {
      width: 50%;
      height: 400px;
      background-color: rgba(0,0,0,0.05);
      border-radius: 1rem;
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    
    .hero-3d-placeholder {
      font-size: 1.2rem;
      color: var(--dark);
      opacity: 0.5;
    }
    
    /* Features */
    .features {
      padding: 4rem 0;
      background-color: rgba(0,0,0,0.02);
    }
    
    .section-title {
      text-align: center;
      font-size: 2rem;
      margin-bottom: 3rem;
      position: relative;
    }
    
    .section-title::after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 50%;
      transform: translateX(-50%);
      width: 50px;
      height: 3px;
      background: linear-gradient(45deg, var(--primary), var(--accent));
    }
    
    .features-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 2rem;
    }
    
    .feature-card {
      background-color: var(--light);
      border-radius: 1rem;
      padding: 2rem;
      box-shadow: 0 5px 15px rgba(0,0,0,0.05);
      text-align: center;
      transition: all 0.3s ease;
    }
    
    .feature-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 15px 30px rgba(0,0,0,0.1);
    }
    
    .feature-icon {
      font-size: 2.5rem;
      margin-bottom: 1rem;
      color: var(--primary);
    }
    
    .feature-title {
      font-size: 1.5rem;
      margin-bottom: 1rem;
    }
    
    .feature-desc {
      color: var(--dark);
      opacity: 0.8;
    }
    
    /* How It Works */
    .how-it-works {
      padding: 4rem 0;
    }
    
    .timeline {
      display: flex;
      justify-content: space-between;
      margin-top: 3rem;
      position: relative;
    }
    
    .timeline::before {
      content: '';
      position: absolute;
      top: 40px;
      left: 0;
      right: 0;
      height: 2px;
      background: linear-gradient(90deg, var(--primary), var(--accent));
      z-index: 1;
    }
    
    .timeline-item {
      width: 22%;
      text-align: center;
      position: relative;
      z-index: 2;
    }
    
    .timeline-icon {
      width: 80px;
      height: 80px;
      background-color: var(--light);
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 0 auto 1rem;
      font-size: 2rem;
      color: var(--primary);
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    }
    
    .timeline-title {
      font-size: 1.2rem;
      margin-bottom: 0.5rem;
    }
    
    .timeline-desc {
      font-size: 0.9rem;
      color: var(--dark);
      opacity: 0.8;
    }
    
    /* FAQ */
    .faq {
      padding: 4rem 0;
      background-color: rgba(0,0,0,0.02);
    }
    
    .faq-container {
      max-width: 800px;
      margin: 0 auto;
    }
    
    .faq-item {
      margin-bottom: 1rem;
      border-radius: 0.5rem;
      overflow: hidden;
      box-shadow: 0 2px 10px rgba(0,0,0,0.05);
      background-color: var(--light);
    }
    
    .faq-question {
      padding: 1.5rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      cursor: pointer;
      font-weight: bold;
    }
    
    .faq-answer {
      padding: 0 1.5rem 1.5rem;
      color: var(--dark);
      opacity: 0.8;
    }
    
    /* CTA Section */
    .cta-section {
      padding: 4rem 0;
      text-align: center;
      background: linear-gradient(45deg, var(--primary), var(--accent));
      color: white;
    }
    
    .cta-title {
      font-size: 2.5rem;
      margin-bottom: 1rem;
    }
    
    .cta-subtitle {
      font-size: 1.2rem;
      margin-bottom: 2rem;
      opacity: 0.9;
    }
    
    .cta-buttons {
      display: flex;
      gap: 1rem;
      justify-content: center;
    }
    
    .btn-light {
      background-color: white;
      color: var(--primary);
    }
    
    /* Footer */
    footer {
      padding: 4rem 0 2rem;
      background-color: var(--dark);
      color: var(--light);
    }
    
    .footer-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 2rem;
      margin-bottom: 2rem;
    }
    
    .footer-column h3 {
      font-size: 1.2rem;
      margin-bottom: 1.5rem;
      position: relative;
    }
    
    .footer-column h3::after {
      content: '';
      position: absolute;
      bottom: -5px;
      left: 0;
      width: 30px;
      height: 2px;
      background-color: var(--primary);
    }
    
    .footer-link {
      display: block;
      margin-bottom: 0.8rem;
      color: var(--light);
      opacity: 0.7;
      text-decoration: none;
      transition: all 0.3s ease;
    }
    
    .footer-link:hover {
      opacity: 1;
      transform: translateX(5px);
    }
    
    .footer-bottom {
      text-align: center;
      padding-top: 2rem;
      border-top: 1px solid rgba(255,255,255,0.1);
      font-size: 0.9rem;
      opacity: 0.7;
    }
    
    /* Responsive */
    @media (max-width: 992px) {
      .hero {
        flex-direction: column;
      }
      
      .hero-content, .hero-3d {
        width: 100%;
      }
      
      .hero-3d {
        margin-top: 2rem;
      }
      
      .features-grid {
        grid-template-columns: repeat(2, 1fr);
      }
      
      .timeline {
        flex-direction: column;
        align-items: center;
      }
      
      .timeline::before {
        display: none;
      }
      
      .timeline-item {
        width: 100%;
        max-width: 300px;
        margin-bottom: 2rem;
      }
      
      .footer-grid {
        grid-template-columns: repeat(2, 1fr);
      }
    }
    
    @media (max-width: 576px) {
      .nav-links {
        display: none;
      }
      
      .features-grid {
        grid-template-columns: 1fr;
      }
      
      .footer-grid {
        grid-template-columns: 1fr;
      }
      
      .hero-title {
        font-size: 2rem;
      }
      
      .hero-cta, .cta-buttons {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
  <!-- Header -->
  <header>
    <div class="container header-content">
      <div class="logo">AI Sức Khỏe</div>
      <div class="nav-links">
        <a href="#" class="nav-link">Health Blog</a>
        <a href="#" class="nav-link">Tech Blog</a>
        <a href="#" class="nav-link">Roadmap</a>
        <button class="theme-toggle">🌙</button>
        <a href="#" class="btn btn-primary">Web App</a>
        <a href="#" class="nav-link">Telegram</a>
      </div>
    </div>
  </header>

  <!-- Hero Section -->
  <section class="hero">
    <div class="container" style="display: flex; align-items: center;">
      <div class="hero-content">
        <h1 class="hero-title">Tư vấn sức khỏe thông minh với AI</h1>
        <p class="hero-subtitle">Giải đáp mọi thắc mắc y tế và kết nối với bác sĩ uy tín chỉ trong vài phút.</p>
        <div class="hero-cta">
          <a href="#" class="btn btn-primary">Hỏi AI ngay</a>
          <a href="#" class="btn btn-secondary">Kết nối bác sĩ</a>
        </div>
      </div>
      <div class="hero-3d">
        <div class="hero-3d-placeholder">[3D Doctor/AI Animation]</div>
      </div>
    </div>
  </section>

  <!-- Features Section -->
  <section class="features">
    <div class="container">
      <h2 class="section-title">Tính năng nổi bật</h2>
      <div class="features-grid">
        <div class="feature-card">
          <div class="feature-icon">🤖</div>
          <h3 class="feature-title">AI Thông minh</h3>
          <p class="feature-desc">Công nghệ AI tiên tiến giúp trả lời câu hỏi y tế của bạn một cách chính xác và nhanh chóng.</p>
        </div>
        <div class="feature-card">
          <div class="feature-icon">👨‍⚕️</div>
          <h3 class="feature-title">Bác sĩ uy tín</h3>
          <p class="feature-desc">Kết nối với đội ngũ bác sĩ giỏi, có nhiều năm kinh nghiệm và được xác thực kỹ lưỡng.</p>
        </div>
        <div class="feature-card">
          <div class="feature-icon">⚡</div>
          <h3 class="feature-title">Tiện lợi & nhanh chóng</h3>
          <p class="feature-desc">Tiết kiệm thời gian chờ đợi và di chuyển, nhận tư vấn y tế mọi lúc, mọi nơi.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- How It Works -->
  <section class="how-it-works">
    <div class="container">
      <h2 class="section-title">Quy trình sử dụng</h2>
      <div class="timeline">
        <div class="timeline-item">
          <div class="timeline-icon">1</div>
          <h3 class="timeline-title">Đặt câu hỏi</h3>
          <p class="timeline-desc">Nhập thắc mắc sức khỏe của bạn vào chatbox</p>
        </div>
        <div class="timeline-item">
          <div class="timeline-icon">2</div>
          <h3 class="timeline-title">Nhận tư vấn AI</h3>
          <p class="timeline-desc">AI phân tích và đưa ra câu trả lời ban đầu</p>
        </div>
        <div class="timeline-item">
          <div class="timeline-icon">3</div>
          <h3 class="timeline-title">Kết nối bác sĩ</h3>
          <p class="timeline-desc">AI gợi ý và kết nối với bác sĩ phù hợp</p>
        </div>
        <div class="timeline-item">
          <div class="timeline-icon">4</div>
          <h3 class="timeline-title">Nhận tư vấn chuyên sâu</h3>
          <p class="timeline-desc">Bác sĩ tư vấn chi tiết và đưa ra phương pháp điều trị</p>
        </div>
      </div>
    </div>
  </section>

  <!-- FAQ Section -->
  <section class="faq">
    <div class="container">
      <h2 class="section-title">Câu hỏi thường gặp</h2>
      <div class="faq-container">
        <div class="faq-item">
          <div class="faq-question">
            AI Sức Khỏe có thay thế được bác sĩ không?
            <span>▼</span>
          </div>
          <div class="faq-answer">
            AI Sức Khỏe không thay thế hoàn toàn bác sĩ mà đóng vai trò hỗ trợ ban đầu, giúp bạn hiểu vấn đề sức khỏe và kết nối với bác sĩ phù hợp khi cần thiết.
          </div>
        </div>
        <div class="faq-item">
          <div class="faq-question">
            Thông tin của tôi có được bảo mật không?
            <span>▼</span>
          </div>
          <div class="faq-answer">
            Chúng tôi cam kết bảo mật tuyệt đối thông tin cá nhân và sức khỏe của người dùng. Mọi dữ liệu đều được mã hóa và tuân thủ các quy định về bảo vệ dữ liệu.
          </div>
        </div>
        <div class="faq-item">
          <div class="faq-question">
            Làm sao để biết bác sĩ trên hệ thống là đáng tin cậy?
            <span>▼</span>
          </div>
          <div class="faq-answer">
            Tất cả bác sĩ trên hệ thống đều được xác thực bằng chứng chỉ hành nghề, kinh nghiệm làm việc và đánh giá từ bệnh nhân. Bạn có thể xem hồ sơ chi tiết của họ trước khi kết nối.
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- CTA Section -->
  <section class="cta-section">
    <div class="container">
      <h2 class="cta-title">Hỏi AI ngay hôm nay!</h2>
      <p class="cta-subtitle">Nhận tư vấn sức khỏe nhanh chóng và kết nối với bác sĩ uy tín</p>
      <div class="cta-buttons">
        <a href="#" class="btn btn-light">Web App</a>
        <a href="#" class="btn btn-light">Telegram</a>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <div class="container">
      <div class="footer-grid">
        <div class="footer-column">
          <h3>AI Sức Khỏe</h3>
          <a href="#" class="footer-link">Giới thiệu</a>
          <a href="#" class="footer-link">Đội ngũ</a>
          <a href="#" class="footer-link">Đối tác</a>
          <a href="#" class="footer-link">Tuyển dụng</a>
        </div>
        <div class="footer-column">
          <h3>Tài nguyên</h3>
          <a href="#" class="footer-link">Health Blog</a>
          <a href="#" class="footer-link">Tech Blog</a>
          <a href="#" class="footer-link">Roadmap</a>
          <a href="#" class="footer-link">Hướng dẫn sử dụng</a>
        </div>
        <div class="footer-column">
          <h3>Hỗ trợ</h3>
          <a href="#" class="footer-link">Trung tâm hỗ trợ</a>
          <a href="#" class="footer-link">FAQ</a>
          <a href="#" class="footer-link">Liên hệ</a>
          <a href="#" class="footer-link">Phản hồi</a>
        </div>
        <div class="footer-column">
          <h3>Pháp lý</h3>
          <a href="#" class="footer-link">Điều khoản sử dụng</a>
          <a href="#" class="footer-link">Chính sách bảo mật</a>
          <a href="#" class="footer-link">Quy định sử dụng</a>
          <a href="#" class="footer-link">Miễn trừ trách nhiệm</a>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2025 AI Sức Khỏe. Tất cả quyền được bảo lưu.</p>
      </div>
    </div>
  </footer>

  <script>
    // This would be replaced with actual code for:
    // 1. Three.js for 3D models
    // 2. GSAP for animations
    // 3. Particles.js for background effects
    // 4. Dark/Light mode toggle
    // 5. FAQ accordion functionality
    document.querySelector('.theme-toggle').addEventListener('click', function() {
      document.body.classList.toggle('dark-mode');
      this.textContent = document.body.classList.contains('dark-mode') ? '☀️' : '🌙';
    });
  </script>
</body>
</html>
```