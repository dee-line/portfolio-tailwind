# Portfolio 網站 - TailwindCSS 切版

## 專案說明

這是一個使用 TailwindCSS 製作的個人作品集網站，包含以下區塊：

- Navigation（固定導覽列）
- Hero Section（個人介紹）
- Works Section（作品展示）
- Experience Section（工作經歷）
- Collaborations Section（服務項目）
- Footer/Contact（聯絡資訊）

## 色彩規範

| 用途 | 色碼 | Tailwind 變數 |
|------|------|---------------|
| 強調色-粉紅 | #FF98C7 | `accent-pink` |
| 強調色-藍 | #146EF5 | `accent-blue` |
| 強調色-黃 | #FFF25D | `accent-yellow` |
| 文字灰 | #6B6B6B | `text-gray` |
| 淺灰背景 | #F5F5F5 | `light-gray` |

## 字體設定

- 主要字體：Bricolage Grotesque
- 輔助字體：Roboto、SF Pro Text

---

## 完整程式碼

```html
<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dee - UI/UX Designer Portfolio</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,400;12..96,500;12..96,600;12..96,700&family=Roboto:wght@400;500&display=swap" rel="stylesheet">
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            'accent-pink': '#FF98C7',
            'accent-blue': '#146EF5',
            'accent-yellow': '#FFF25D',
            'text-gray': '#6B6B6B',
            'light-gray': '#F5F5F5',
          },
          fontFamily: {
            'bricolage': ['Bricolage Grotesque', 'sans-serif'],
            'roboto': ['Roboto', 'sans-serif'],
            'sf': ['-apple-system', 'BlinkMacSystemFont', 'SF Pro Text', 'sans-serif'],
          },
          borderRadius: {
            '4xl': '32px',
            '5xl': '40px',
          }
        }
      }
    }
  </script>
  <style>
    .gradient-text {
      background: linear-gradient(90deg, #FF98C7 0%, #146EF5 50%, #FFF25D 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
  </style>
</head>
<body class="bg-white font-bricolage">

  <!-- Navigation -->
  <nav class="fixed top-0 left-0 right-0 z-50 bg-white/90 backdrop-blur-sm">
    <div class="max-w-7xl mx-auto px-8 py-6 flex justify-between items-center">
      <!-- Logo -->
      <div class="w-12 h-12 bg-black rounded-full flex items-center justify-center">
        <span class="text-white text-xl font-bold">D</span>
      </div>
      <!-- Menu -->
      <ul class="flex gap-12 text-sm font-medium tracking-wide">
        <li><a href="#about" class="hover:text-accent-blue transition-colors">ABOUT</a></li>
        <li><a href="#works" class="hover:text-accent-blue transition-colors">WORKS</a></li>
        <li><a href="#experience" class="hover:text-accent-blue transition-colors">EXPERIENCE</a></li>
        <li><a href="#contact" class="hover:text-accent-blue transition-colors">CONTACT</a></li>
      </ul>
    </div>
  </nav>

  <!-- Hero Section -->
  <section id="about" class="min-h-screen pt-32 pb-20 px-8">
    <div class="max-w-7xl mx-auto">
      <div class="flex flex-col lg:flex-row gap-16 items-center">
        <!-- Left Content -->
        <div class="flex-1 space-y-8">
          <!-- Greeting -->
          <h1 class="text-6xl lg:text-7xl font-bold leading-tight">
            Hello,<br>
            I am <span class="gradient-text">Dee</span>.
          </h1>

          <!-- Description -->
          <p class="text-lg text-text-gray max-w-lg leading-relaxed">
            我是一位擁有 5 年以上經驗的 UI/UX 設計師，專注於創造直覺且富有美感的數位產品體驗。從品牌識別到介面設計，我致力於將複雜的問題轉化為簡潔優雅的解決方案。
          </p>

          <!-- Skill Tags -->
          <div class="flex flex-wrap gap-3">
            <span class="px-6 py-3 bg-accent-pink/20 text-black rounded-full text-sm font-medium">
              UI/UX Design
            </span>
            <span class="px-6 py-3 bg-accent-blue/20 text-black rounded-full text-sm font-medium">
              Brand Design
            </span>
            <span class="px-6 py-3 bg-accent-yellow/40 text-black rounded-full text-sm font-medium">
              AI Workflow
            </span>
          </div>

          <!-- CTA Button -->
          <div class="pt-4">
            <a href="#contact" class="inline-flex items-center gap-2 px-8 py-4 bg-black text-white rounded-full font-medium hover:bg-gray-800 transition-colors">
              Let's Talk
              <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/>
              </svg>
            </a>
          </div>
        </div>

        <!-- Right - Photo -->
        <div class="flex-1 flex justify-center">
          <div class="relative">
            <div class="w-80 h-80 lg:w-96 lg:h-96 rounded-full overflow-hidden bg-light-gray">
              <!-- Placeholder for photo -->
              <div class="w-full h-full bg-gradient-to-br from-accent-pink/30 via-accent-blue/30 to-accent-yellow/30 flex items-center justify-center">
                <span class="text-6xl">👩‍💻</span>
              </div>
            </div>
            <!-- Decorative elements -->
            <div class="absolute -top-4 -right-4 w-24 h-24 bg-accent-yellow rounded-full opacity-60"></div>
            <div class="absolute -bottom-4 -left-4 w-16 h-16 bg-accent-pink rounded-full opacity-60"></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Works Section -->
  <section id="works" class="py-20 px-8 bg-light-gray">
    <div class="max-w-7xl mx-auto">
      <!-- Section Title -->
      <div class="text-center mb-16">
        <h2 class="text-5xl font-bold mb-4">Works</h2>
        <p class="text-text-gray">精選作品展示</p>
      </div>

      <!-- Works Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">

        <!-- Work Item 1 - 十全 -->
        <div class="group relative bg-white rounded-4xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-300">
          <div class="aspect-[4/3] bg-gradient-to-br from-amber-100 to-amber-200 flex items-center justify-center">
            <span class="text-8xl">🏥</span>
          </div>
          <div class="p-8">
            <h3 class="text-2xl font-bold mb-2">十全醫美診所</h3>
            <p class="text-text-gray mb-4">品牌識別設計 / 網站設計</p>
            <div class="flex gap-2">
              <span class="px-3 py-1 bg-light-gray rounded-full text-xs">Branding</span>
              <span class="px-3 py-1 bg-light-gray rounded-full text-xs">Web Design</span>
            </div>
          </div>
        </div>

        <!-- Work Item 2 - 宜蘭餅 -->
        <div class="group relative bg-white rounded-4xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-300">
          <div class="aspect-[4/3] bg-gradient-to-br from-orange-100 to-orange-200 flex items-center justify-center">
            <span class="text-8xl">🥮</span>
          </div>
          <div class="p-8">
            <h3 class="text-2xl font-bold mb-2">宜蘭餅食品</h3>
            <p class="text-text-gray mb-4">電商網站 UI/UX 設計</p>
            <div class="flex gap-2">
              <span class="px-3 py-1 bg-light-gray rounded-full text-xs">E-commerce</span>
              <span class="px-3 py-1 bg-light-gray rounded-full text-xs">UI/UX</span>
            </div>
          </div>
        </div>

        <!-- Work Item 3 -->
        <div class="group relative bg-white rounded-4xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-300">
          <div class="aspect-[4/3] bg-gradient-to-br from-blue-100 to-blue-200 flex items-center justify-center">
            <span class="text-8xl">💼</span>
          </div>
          <div class="p-8">
            <h3 class="text-2xl font-bold mb-2">企業管理平台</h3>
            <p class="text-text-gray mb-4">B2B SaaS 產品設計</p>
            <div class="flex gap-2">
              <span class="px-3 py-1 bg-light-gray rounded-full text-xs">SaaS</span>
              <span class="px-3 py-1 bg-light-gray rounded-full text-xs">Dashboard</span>
            </div>
          </div>
        </div>

        <!-- Work Item 4 -->
        <div class="group relative bg-white rounded-4xl overflow-hidden shadow-lg hover:shadow-2xl transition-all duration-300">
          <div class="aspect-[4/3] bg-gradient-to-br from-pink-100 to-pink-200 flex items-center justify-center">
            <span class="text-8xl">📱</span>
          </div>
          <div class="p-8">
            <h3 class="text-2xl font-bold mb-2">行動應用程式</h3>
            <p class="text-text-gray mb-4">iOS/Android App 設計</p>
            <div class="flex gap-2">
              <span class="px-3 py-1 bg-light-gray rounded-full text-xs">Mobile</span>
              <span class="px-3 py-1 bg-light-gray rounded-full text-xs">App Design</span>
            </div>
          </div>
        </div>

      </div>

      <!-- View All Button -->
      <div class="text-center mt-12">
        <a href="#" class="inline-flex items-center gap-2 px-8 py-4 border-2 border-black rounded-full font-medium hover:bg-black hover:text-white transition-colors">
          View All Works
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/>
          </svg>
        </a>
      </div>
    </div>
  </section>

  <!-- Experience Section -->
  <section id="experience" class="py-20 px-8">
    <div class="max-w-7xl mx-auto">
      <!-- Section Title -->
      <div class="text-center mb-16">
        <h2 class="text-5xl font-bold mb-4">Experience</h2>
        <p class="text-text-gray">工作經歷</p>
      </div>

      <!-- Timeline -->
      <div class="max-w-3xl mx-auto space-y-12">

        <!-- Experience Item 1 -->
        <div class="flex gap-8">
          <div class="flex-shrink-0 w-32 text-right">
            <span class="text-sm font-medium text-accent-blue">2022 - NOW</span>
          </div>
          <div class="flex-1 pb-12 border-l-2 border-gray-200 pl-8 relative">
            <div class="absolute left-0 top-0 w-4 h-4 bg-accent-blue rounded-full -translate-x-[9px]"></div>
            <h3 class="text-xl font-bold mb-2">經貿聯網科技</h3>
            <p class="text-text-gray mb-3">Senior UI/UX Designer</p>
            <p class="text-sm text-text-gray leading-relaxed">
              負責多個 B2B SaaS 產品的使用者介面設計，建立設計系統，優化使用者體驗流程，與工程團隊緊密合作確保設計落地品質。
            </p>
          </div>
        </div>

        <!-- Experience Item 2 -->
        <div class="flex gap-8">
          <div class="flex-shrink-0 w-32 text-right">
            <span class="text-sm font-medium text-accent-pink">2020 - 2022</span>
          </div>
          <div class="flex-1 pb-12 border-l-2 border-gray-200 pl-8 relative">
            <div class="absolute left-0 top-0 w-4 h-4 bg-accent-pink rounded-full -translate-x-[9px]"></div>
            <h3 class="text-xl font-bold mb-2">禾相有限公司</h3>
            <p class="text-text-gray mb-3">UI/UX Designer</p>
            <p class="text-sm text-text-gray leading-relaxed">
              負責品牌客戶的網站與應用程式設計，包含電商平台、企業官網等專案，累積豐富的跨產業設計經驗。
            </p>
          </div>
        </div>

        <!-- Experience Item 3 -->
        <div class="flex gap-8">
          <div class="flex-shrink-0 w-32 text-right">
            <span class="text-sm font-medium text-accent-yellow">2019 - 2020</span>
          </div>
          <div class="flex-1 pl-8 relative">
            <div class="absolute left-0 top-0 w-4 h-4 bg-accent-yellow rounded-full -translate-x-[9px] border-2 border-gray-200"></div>
            <h3 class="text-xl font-bold mb-2">Freelance Designer</h3>
            <p class="text-text-gray mb-3">自由接案設計師</p>
            <p class="text-sm text-text-gray leading-relaxed">
              獨立承接品牌識別、平面設計、網頁設計等專案，培養全方位的設計能力與客戶溝通技巧。
            </p>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- Collaborations Section -->
  <section class="py-20 px-8 bg-black text-white">
    <div class="max-w-7xl mx-auto">
      <!-- Section Title -->
      <div class="text-center mb-16">
        <h2 class="text-5xl font-bold mb-4">Collaborations</h2>
        <p class="text-gray-400">服務項目</p>
      </div>

      <!-- Services Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">

        <!-- Service 1 -->
        <div class="p-8 border border-gray-700 rounded-4xl hover:border-accent-pink transition-colors">
          <div class="w-16 h-16 bg-accent-pink/20 rounded-2xl flex items-center justify-center mb-6">
            <span class="text-3xl">🎨</span>
          </div>
          <h3 class="text-xl font-bold mb-3">UI/UX Design</h3>
          <p class="text-gray-400 text-sm leading-relaxed">
            使用者介面設計、使用者體驗優化、原型設計、可用性測試
          </p>
          <div class="flex flex-wrap gap-2 mt-4">
            <span class="px-3 py-1 bg-gray-800 rounded-full text-xs">Figma</span>
            <span class="px-3 py-1 bg-gray-800 rounded-full text-xs">Prototype</span>
          </div>
        </div>

        <!-- Service 2 -->
        <div class="p-8 border border-gray-700 rounded-4xl hover:border-accent-blue transition-colors">
          <div class="w-16 h-16 bg-accent-blue/20 rounded-2xl flex items-center justify-center mb-6">
            <span class="text-3xl">💎</span>
          </div>
          <h3 class="text-xl font-bold mb-3">Brand Design</h3>
          <p class="text-gray-400 text-sm leading-relaxed">
            品牌識別設計、視覺系統建立、品牌策略規劃
          </p>
          <div class="flex flex-wrap gap-2 mt-4">
            <span class="px-3 py-1 bg-gray-800 rounded-full text-xs">Logo</span>
            <span class="px-3 py-1 bg-gray-800 rounded-full text-xs">Identity</span>
          </div>
        </div>

        <!-- Service 3 -->
        <div class="p-8 border border-gray-700 rounded-4xl hover:border-accent-yellow transition-colors">
          <div class="w-16 h-16 bg-accent-yellow/20 rounded-2xl flex items-center justify-center mb-6">
            <span class="text-3xl">🤖</span>
          </div>
          <h3 class="text-xl font-bold mb-3">AI Workflow</h3>
          <p class="text-gray-400 text-sm leading-relaxed">
            AI 輔助設計流程、提示工程、自動化工作流程設計
          </p>
          <div class="flex flex-wrap gap-2 mt-4">
            <span class="px-3 py-1 bg-gray-800 rounded-full text-xs">Midjourney</span>
            <span class="px-3 py-1 bg-gray-800 rounded-full text-xs">ChatGPT</span>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- Footer / Contact -->
  <footer id="contact" class="py-20 px-8">
    <div class="max-w-7xl mx-auto">
      <div class="text-center">
        <!-- Title -->
        <h2 class="text-4xl lg:text-5xl font-bold mb-4">Where to Find Me</h2>
        <p class="text-text-gray mb-12">歡迎聯繫我討論您的專案</p>

        <!-- Email -->
        <a href="mailto:dee.design@example.com" class="inline-flex items-center gap-3 text-2xl lg:text-3xl font-medium hover:text-accent-blue transition-colors">
          <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
          </svg>
          dee.design@example.com
        </a>

        <!-- Social Links -->
        <div class="flex justify-center gap-6 mt-12">
          <a href="#" class="w-12 h-12 bg-light-gray rounded-full flex items-center justify-center hover:bg-accent-pink/20 transition-colors">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
              <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
            </svg>
          </a>
          <a href="#" class="w-12 h-12 bg-light-gray rounded-full flex items-center justify-center hover:bg-accent-blue/20 transition-colors">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/>
            </svg>
          </a>
          <a href="#" class="w-12 h-12 bg-light-gray rounded-full flex items-center justify-center hover:bg-accent-yellow/20 transition-colors">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
              <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z"/>
            </svg>
          </a>
          <a href="#" class="w-12 h-12 bg-light-gray rounded-full flex items-center justify-center hover:bg-accent-pink/20 transition-colors">
            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
              <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
            </svg>
          </a>
        </div>

        <!-- Copyright -->
        <p class="text-text-gray text-sm mt-16">
          © 2024 Dee. All rights reserved.
        </p>
      </div>
    </div>
  </footer>

</body>
</html>
```

---

## 使用方式

1. 直接用瀏覽器開啟 `index.html` 檔案即可預覽
2. 圖片區塊目前使用 emoji 佔位，可替換成實際圖片
3. 如需正式部署，建議改用 npm 安裝 Tailwind 並編譯

## 客製化說明

### 替換圖片

將 emoji 佔位區塊替換為 `<img>` 標籤：

```html
<!-- 原本 -->
<div class="w-full h-full bg-gradient-to-br ... flex items-center justify-center">
  <span class="text-6xl">👩‍💻</span>
</div>

<!-- 替換為 -->
<img src="your-photo.jpg" alt="Profile" class="w-full h-full object-cover">
```

### 修改色彩

在 `tailwind.config` 中修改 `colors` 設定即可全站套用。
