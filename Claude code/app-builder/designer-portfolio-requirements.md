# 设计师个人网站 - 需求文档

**项目名称：** Designer Portfolio Website
**目标用户：** 设计师、开发者、AI 爱好者
**风格定位：** 极简现代（Modern Minimalist）
**技术栈：** HTML/CSS/JavaScript (Vanilla)
**预计时长：** 4-6 小时

---

## 问题陈述

**解决的问题：**
为设计师创建一个专业的个人网站，系统化地展示 Prompt 模板库、Skills 作品集和技术博客，帮助访客快速找到需要的资源并了解设计师的专业能力。

**核心价值：**
- 清晰展示专业作品（Prompt 和 Skills）
- 瀑布流布局提供视觉吸引力
- 便捷的浏览和下载体验

---

## 目标用户

### 主要用户群
1. **寻找灵感的设计师** - 浏览 Prompt 和 Skills，寻找可复用的资源
2. **潜在客户/雇主** - 评估设计能力和技术水平
3. **技术爱好者** - 阅读 Blog，学习设计思路

### 用户需求
- 快速浏览大量作品
- 查看详细说明和使用方法
- 下载或复制所需资源
- 了解设计师背景和联系方式

---

## 核心功能 (MoSCoW)

### Must Have（必须有 - V1）
1. **响应式导航栏**
   - Logo + 4个菜单：Prompt、Skills、Blog、More
   - Sticky 定位，滚动时保持可见
   - 移动端汉堡菜单

2. **Prompt 瀑布流页面**
   - 瀑布流布局（Masonry）展示 Prompt 卡片
   - 每个卡片包含：
     - 标题
     - 简短描述
     - 类别标签
     - 预览缩略图（可选）
   - 点击卡片查看详情（模态框或新页面）
   - 一键复制 Prompt 功能

3. **Skills 瀑布流页面**
   - 瀑布流布局展示 Skills 卡片
   - 每个卡片包含：
     - Skill 名称
     - 功能描述
     - 截图/图标
     - 下载按钮
   - 点击查看详细文档

4. **Blog 列表页**
   - 时间倒序排列的文章列表
   - 每篇文章显示：
     - 标题
     - 发布日期
     - 摘要
     - 阅读时间
   - 点击进入文章详情页

5. **More（更多）页面**
   - 个人简介
   - 技能栈展示
   - 联系方式（邮箱、Twitter、GitHub等）
   - 简历下载

6. **响应式设计**
   - 移动端：单列瀑布流
   - 平板：2列
   - 桌面：3-4列

### Should Have（应该有 - V2）
1. **搜索功能** - 在 Prompt 和 Skills 中搜索关键词
2. **分类筛选** - 按类别过滤内容
3. **暗色模式** - 支持明暗主题切换
4. **平滑动画** - 页面切换、卡片悬停动效

### Could Have（可以有 - V3）
1. **阅读进度条** - Blog 文章阅读进度
2. **标签云** - 热门标签快速导航
3. **统计数据** - 作品数量、博客文章数等
4. **评论系统** - Blog 文章评论（可用第三方服务）

### Won't Have（不包含 - 超出范围）
1. ~~用户登录系统~~
2. ~~后端数据库~~（使用 JSON 数据文件）
3. ~~在线编辑器~~（内容通过代码更新）
4. ~~多语言支持~~（初版仅英文或中文）

---

## 用户故事

### 故事 1：浏览 Prompt
**作为** 一个寻找灵感的设计师，
**我想要** 浏览瀑布流形式的 Prompt 库，
**以便** 快速找到适合我项目的 Prompt 模板。

**验收标准：**
- [ ] 瀑布流布局美观且响应式
- [ ] 每个卡片清晰展示 Prompt 的核心信息
- [ ] 点击卡片可查看完整内容
- [ ] 可以一键复制 Prompt 文本

### 故事 2：下载 Skills
**作为** 一个开发者，
**我想要** 查看并下载 Skills 文件，
**以便** 在我的项目中使用这些工具。

**验收标准：**
- [ ] Skills 卡片展示清晰的功能说明
- [ ] 下载按钮明显且易用
- [ ] 点击下载能获取 .skill 文件

### 故事 3：阅读 Blog
**作为** 一个技术爱好者，
**我想要** 阅读设计师的技术博客，
**以便** 学习他们的设计思路和经验。

**验收标准：**
- [ ] 文章列表清晰，按时间排序
- [ ] 文章页面排版舒适，易于阅读
- [ ] 支持代码高亮和图片展示

### 故事 4：联系设计师
**作为** 一个潜在客户，
**我想要** 快速找到联系方式，
**以便** 与设计师沟通合作事宜。

**验收标准：**
- [ ] More 页面有清晰的联系方式
- [ ] 社交媒体链接可点击
- [ ] 简历可下载

---

## 技术约束

### 技术栈
- **前端：** HTML5, CSS3, JavaScript (ES6+)
- **布局：** CSS Grid + Flexbox
- **瀑布流：** JavaScript 实现（Masonry 算法或 CSS Grid）
- **图标：** SVG 或 Web Icons
- **字体：** 系统字体栈或 Google Fonts

### 浏览器支持
- Chrome/Edge (最新版本)
- Firefox (最新版本)
- Safari (最新版本)
- 移动浏览器（iOS Safari, Chrome Mobile）

### 性能目标
- 首次加载时间：< 2秒
- 瀑布流渲染流畅：60fps
- 图片优化：WebP 格式，懒加载

### 数据存储
- 内容数据：JSON 文件存储
- 不需要后端服务器
- 可部署到静态托管（Vercel, Netlify, GitHub Pages）

### 离线支持
- 不需要离线功能（在线网站）

---

## 设计方向

### 视觉风格
**风格：** 极简现代（Modern Minimalist）
**参考：** Apple.com, Linear.app, Stripe.com

### 配色方案
- **主色调：** 蓝色系（专业、信任）
  - Primary: #5B8DEF 或类似
- **中性色：** 黑白灰
  - Background: #FFFFFF / #FAFAFA
  - Text: #1A1A1A
  - Secondary Text: #6E6E6E
- **强调色：** 鲜艳的品牌色（用于 CTA 按钮）

### 排版
- **字体：** Inter, SF Pro, 或 system-ui
- **层级：**
  - H1: 48-56px, Bold
  - H2: 36px, Semibold
  - H3: 24px, Semibold
  - Body: 16px, Regular
  - Small: 14px

### 布局特点
- 大量留白
- 清晰的视觉层级
- 居中对齐的容器（max-width: 1200px）
- 卡片设计（圆角、阴影）

### 组件风格
- **按钮：** 圆角（8px），微妙阴影，hover 提升效果
- **卡片：** 白色背景，圆角（12px），hover 时上移
- **导航：** 简洁，sticky，半透明背景 + 毛玻璃效果

---

## 成功标准

### 功能成功
- [ ] 所有 Must Have 功能完整实现
- [ ] 瀑布流布局在所有设备上正常工作
- [ ] 复制和下载功能可用
- [ ] 无 JavaScript 错误

### 设计成功
- [ ] 符合极简现代风格
- [ ] 配色协调，对比度达标（WCAG AA）
- [ ] 响应式完美适配（手机、平板、桌面）
- [ ] 视觉层级清晰

### 用户体验成功
- [ ] 首次访问即可理解网站结构
- [ ] 浏览内容无需说明
- [ ] 所有交互有即时反馈
- [ ] 移动端体验流畅

### 性能成功
- [ ] Lighthouse 分数 > 90
- [ ] 首屏加载 < 2秒
- [ ] 滚动和动画流畅（60fps）

---

## 页面结构

### 页面列表
1. **首页/Prompt 页**（默认）- `/` or `/prompts`
2. **Skills 页** - `/skills`
3. **Blog 列表页** - `/blog`
4. **Blog 详情页** - `/blog/:id`
5. **More 页** - `/more`

### 导航结构
```
Header (Sticky)
├── Logo (左侧，点击回首页)
├── Nav Menu (右侧)
│   ├── Prompts
│   ├── Skills
│   ├── Blog
│   └── More
└── Mobile Menu Toggle
```

### 瀑布流结构
```
Container (max-width: 1200px)
└── Masonry Grid
    ├── Card 1
    ├── Card 2
    ├── Card 3
    └── ...
```

---

## 数据结构

### Prompt 数据（prompts.json）
```json
{
  "prompts": [
    {
      "id": "prompt-001",
      "title": "UI Design Analysis Prompt",
      "description": "Analyze UI designs and extract design patterns",
      "category": "Design",
      "tags": ["UI", "Analysis", "Design System"],
      "content": "Full prompt text here...",
      "thumbnail": "images/prompt-001.jpg",
      "createdDate": "2024-01-15"
    }
  ]
}
```

### Skills 数据（skills.json）
```json
{
  "skills": [
    {
      "id": "skill-001",
      "name": "Professional Prompt Writer",
      "description": "Generate high-quality prompts",
      "screenshot": "images/skill-001.png",
      "downloadUrl": "downloads/professional-prompt-writer.skill",
      "tags": ["Productivity", "Writing"],
      "createdDate": "2024-01-10"
    }
  ]
}
```

### Blog 数据（blog.json）
```json
{
  "posts": [
    {
      "id": "post-001",
      "title": "如何构建高质量的设计系统",
      "summary": "分享设计系统构建的最佳实践...",
      "content": "Full markdown content...",
      "publishDate": "2024-01-15",
      "readTime": "8 min",
      "tags": ["Design System", "Tutorial"]
    }
  ]
}
```

---

## 下一步：Stage 2

准备进行 Prompt 增强，生成给 Gemini 的详细指令。

**预计时间分配：**
- Stage 1 (需求)：✅ 完成
- Stage 2 (Prompt 增强)：30 分钟
- Stage 3 (生成第一版)：15 分钟
- Stage 4 (UI 优化)：90 分钟
- Stage 5 (品牌化)：30 分钟
- Stage 6 (细节)：90 分钟
- Stage 7 (复盘)：30 分钟

**总计：** 约 5 小时
