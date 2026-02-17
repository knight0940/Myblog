# Amorend 个人网站

一个现代化的个人作品集和博客网站，采用 Apple 风格的液态玻璃设计。

## 📁 文件结构

```
Myblog/
├── index.html          # 主页（包含 Hero, About, 作品预览4条, 博客预览4条, Contact）
├── work.html           # 作品页面（展示所有作品项目）
├── blog.html           # 博客列表页（展示所有博客文章，带模态框）
│
├── posts/              # 文章内容目录
│   ├── blog/          # 博客文章 markdown 文件
│   │   ├── ai-agent-future.md
│   │   ├── medical-cv.md
│   │   ├── llm-finetuning.md
│   │   ├── ai-infra.md
│   │   ├── vqa-research.md
│   │   └── pathology-vlp.md
│   │
│   └── work/          # 作品详情 markdown 文件
│       ├── ai-agent-platform.md
│       ├── medical-imaging-system.md
│       ├── portfolio.md
│       ├── saas-platform.md
│       ├── knowledge-graph.md
│       ├── llm-framework.md
│       ├── video-processing.md
│       └── recommendation-engine.md
│
├── Music/             # 音乐文件
│   └── 在雨后醒来.mp3
│
└── README.md          # 本文件
```

## ✨ 特性

### 设计特点
- **Apple 风格液态玻璃**：导航栏、模态框使用 backdrop-filter 实现毛玻璃效果
- **生成式线条艺术背景**：HTML5 Canvas 实现，支持鼠标交互涟漪效果
- **平滑滚动**：Lenis + GSAP ScrollTrigger 实现流畅的滚动动画
- **响应式设计**：完美适配桌面和移动设备

### 技术栈
- **GSAP 3.12.5**：强大的动画库
- **ScrollTrigger**：滚动触发动画
- **Lenis**：平滑滚动体验
- **CSS Backdrop Filter**：液态玻璃效果

## 🎯 核心功能

### 1. 主页 (index.html)
- Hero 区域：大标题展示
- About：个人介绍和荣誉
- Work Preview：最新 4 个作品
- Blog Preview：最新 4 篇博客
- Contact：联系方式

### 2. 作品页面 (work.html)
- 展示所有 8 个作品项目
- 网格布局，响应式设计
- 滚动触发动画

### 3. 博客页面 (blog.html)
- 展示所有 6 篇博客文章
- **模态框功能**：点击文章在页面内弹出液态玻璃风格窗口
- 支持 ESC 键关闭、点击背景关闭
- 平滑的打开/关闭动画

### 4. 音乐播放
- 右下角浮动按钮控制
- 自动播放（需用户交互）
- 播放状态脉冲动效

### 5. 主题切换
- 支持明/暗主题
- 自动检测系统偏好
- 平滑过渡效果

## 🎨 模态框设计

博客页面采用页面内模态框设计：

**特点**：
- 液态玻璃背景（backdrop-filter: blur(40px)）
- 平滑的打开/关闭动画
- 支持长内容滚动
- 响应式设计

**交互方式**：
- 点击文章标题或"阅读全文"打开
- 点击 × 按钮关闭
- 点击背景关闭
- 按 ESC 键关闭

## 📝 添加新文章

### 添加博客文章

1. 在 `posts/blog/` 创建新的 markdown 文件
2. 在 `blog.html` 的 `blogPosts` 对象中添加内容：
```javascript
'your-post-slug': {
    title: '文章标题',
    date: '2026-01-20',
    tag: '#YourTag',
    content: `<p>文章 HTML 内容...</p>`
}
```
3. 在页面中添加对应的博客卡片：
```html
<article class="blog-card" data-post="your-post-slug">
    <!-- 卡片内容 -->
</article>
```

### 添加作品项目

类似流程，在 `posts/work/` 创建 markdown 文件，并在 `work.html` 中添加项目卡片。

## 🚀 部署建议

- **静态托管**：可直接部署到 GitHub Pages, Netlify, Vercel
- **CDN**：GSAP 和 Lenis 已使用 CDN
- **性能优化**：
  - 使用图片压缩
  - 启用 gzip/brotli
  - 配置缓存策略

## 📱 浏览器支持

- Chrome/Edge 90+
- Safari 14+
- Firefox 88+

## 🎵 音乐来源

"在雨后醒来" - 艾志恒Asen

## 👤 作者

Amorend - 厦门大学软件工程专业

---
最后更新：2026-02-16
