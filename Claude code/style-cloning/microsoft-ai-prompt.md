# Microsoft.ai 风格复刻 Prompt

## 基础风格定义

创建一个网页，遵循 Microsoft.ai 的设计风格：**Modern Minimalist + Corporate Approachable**

---

## 核心设计令牌

### 配色方案
- **品牌渐变**: 青蓝 (#0693E3) → 紫色 (#9B51E0)
- **辅助色**: 粉色 (#F78DA7)、橙色 (#FF6900)、绿色 (#00D084)
- **中性色**: 黑色文字 (#000000)、灰色背景 (#F0F0F0)、白色 (#FFFFFF)
- **渐变使用**: Hero 区域和卡片 overlay 大量使用品牌渐变

### 排版系统
- **字体**: Segoe UI, -apple-system, sans-serif
- **字号**:
  - Hero 标题: 56px (3.5rem)
  - 章节标题: 42px (2.625rem)
  - 卡片标题: 24px (1.5rem)
  - 正文: 16px (1rem)
  - 小字: 13px (0.8125rem)
- **字重**: Regular (400), Medium (500), Semibold (600), Bold (700)
- **行高**: 标题 1.2, 正文 1.6

### 间距与布局
- **基础单位**: 8px
- **容器最大宽度**: 1280px
- **卡片内边距**: 32px
- **区块间距**: 80px
- **Grid 间距**: 2em (32px)

### 圆角与阴影
- **圆角**: 卡片 16px, 按钮 8px
- **卡片阴影**: `0 4px 8px rgba(0, 0, 0, 0.08)`
- **Hover 阴影**: `0 12px 32px rgba(0, 0, 0, 0.15)`

---

## 关键组件规范

### Hero Section（首屏）
```
- 最小高度: 70vh
- 背景: 青蓝到紫色的渐变 + 20% 黑色遮罩
- 文字: 白色，居中对齐
- 主标题: 56px, Bold, 行高 1.2
- 副标题: 24px, Regular, 透明度 95%
- CTA 按钮:
  - Primary: 渐变背景，白色文字
  - Secondary: 透明背景，白色边框
```

### News/Article Card（新闻卡片）
```
- 背景: 白色
- 圆角: 16px
- 阴影: 中等 + Hover 时提升
- 图片高度: 240px
- 内边距: 32px
- Hover 效果: 向上移动 4px + 增强阴影
- Meta 信息: 13px, 灰色 (#6E6E6E)
- 标题: 24px, Semibold, 黑色
- 摘要: 16px, Regular, 深灰 (#424242)
- 链接: 青蓝色，带右箭头 →
```

### Navigation（导航栏）
```
- 位置: Sticky 定位
- 背景: 白色 95% 透明度 + 毛玻璃效果
- 边框: 底部 1px 浅灰色
- Logo: 24px, Bold, 黑色
- 链接: 14px, Medium, 灰色 → Hover 变黑色
- 内边距: 16px 垂直
```

### Button（按钮）
```
Primary:
- 背景: 渐变 (青蓝→紫色)
- 文字: 白色, 16px, Medium
- 内边距: 12px 32px
- 圆角: 8px
- Hover: 轻微阴影 + 向上 2px

Secondary:
- 背景: 透明
- 边框: 2px 白色
- Hover: 白色背景 + 青蓝色文字
```

---

## 布局结构

### 整体布局
```
1. Sticky Navigation
2. Hero Section (70vh, 渐变背景)
3. News Section (白色背景, 3列 Grid)
4. Products Section (浅灰背景, 3列 Grid)
5. Research/Stats Section (白色背景, 居中文字)
6. CTA Section (浅灰背景, 大按钮)
7. Footer (灰色背景, 居中对齐)
```

### Grid 系统
```css
display: grid;
grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
gap: 2em;
```

---

## 设计原则

1. **Approachable（亲和力）**
   - 使用友好的渐变色
   - 大量留白
   - 圆角设计
   - 高质量图片/emoji

2. **Professional（专业）**
   - 黑白主色调
   - 清晰的信息层级
   - 一致的间距
   - 微妙的阴影

3. **Modern（现代）**
   - 毛玻璃效果（导航栏）
   - 卡片式布局
   - 平滑动画（150-250ms）
   - 响应式设计

---

## 响应式规则

### 移动端 (<768px)
- Hero 标题: 36px → 降低
- Grid: 单列显示
- 导航: 汉堡菜单
- 间距: 减少 25%

### 平板 (768px-1024px)
- Grid: 2列显示
- 字号: 保持或略微缩小

### 桌面 (>1024px)
- 完整 3列 Grid
- 最大宽度 1280px 居中

---

## 动画效果

```css
/* 页面加载淡入 */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 卡片 Hover */
.card:hover {
  transform: translateY(-4px);
  transition: all 250ms cubic-bezier(0.4, 0, 0.2, 1);
}

/* 按钮 Hover */
.button:hover {
  transform: translateY(-2px);
  transition: all 150ms ease;
}
```

---

## 使用方法

### 方式 1：直接提示词
```
"创建一个网页，使用 Microsoft.ai 的风格：
- 渐变色（青蓝#0693E3 到紫色#9B51E0）
- Hero 区域使用渐变背景，白色大标题
- 3列新闻卡片布局，白色卡片带圆角和阴影
- Segoe UI 字体，简洁现代
- 响应式设计"
```

### 方式 2：详细规范
将上述所有规范提供给 AI，要求严格遵循设计令牌和组件规范。

### 方式 3：示例代码
参考生成的 `microsoft-ai-style.css` 和完整分析文档 `microsoft-ai-analysis.md`。

---

## 快速检查清单

设计完成后，检查是否符合：
- ✅ 使用了青蓝→紫色渐变
- ✅ Hero 区域高度至少 70vh
- ✅ 卡片有 16px 圆角和微妙阴影
- ✅ Hover 效果流畅（250ms 过渡）
- ✅ 字体使用 Segoe UI 或系统字体
- ✅ 间距遵循 8px 基准
- ✅ 响应式设计工作正常
- ✅ 整体感觉"专业但友好"

---

## 示例 Prompt（直接可用）

**短版 Prompt:**
```
创建一个 Microsoft AI 风格的网页：使用青蓝(#0693E3)到紫色(#9B51E0)的渐变作为品牌色。包含：1) 渐变背景的 Hero 区域，白色大标题"Approachable Intelligence"，2) 三列新闻卡片，白色背景，16px圆角，悬停时上移，3) Segoe UI 字体，响应式布局，整体风格现代极简且专业友好。
```

**完整 Prompt:**
```
创建一个完整的单页网页，复刻 Microsoft.ai 的设计风格：

设计系统：
- 配色：品牌渐变(#0693E3→#9B51E0)，辅助色(粉#F78DA7/橙#FF6900/绿#00D084)，黑白灰中性色
- 排版：Segoe UI字体，Hero标题56px/Bold，卡片标题24px/Semibold，正文16px/Regular
- 间距：8px基准单位，容器最大1280px，卡片内边距32px，区块间距80px
- 圆角：卡片16px，按钮8px
- 阴影：卡片默认0 4px 8px rgba(0,0,0,0.08)，hover时0 12px 32px rgba(0,0,0,0.15)

页面结构：
1. Sticky导航栏：白色半透明背景+毛玻璃效果，Logo+菜单链接
2. Hero区域：70vh高，渐变背景+20%黑色遮罩，白色居中大标题和副标题，两个CTA按钮（Primary渐变背景/Secondary透明边框）
3. 新闻区域：3列Grid布局(gap 2em)，白色卡片，240px高图片，32px内边距，Meta信息+标题+摘要+链接，hover上移4px
4. 产品区域：浅灰背景(#F0F0F0)，同样3列卡片布局
5. 统计数据：居中大数字展示(青蓝/紫/绿色)
6. CTA区域：浅灰背景，居中文字和大按钮
7. Footer：灰色背景，版权信息+链接

交互效果：
- 所有过渡250ms cubic-bezier(0.4, 0, 0.2, 1)
- 卡片hover：上移4px+增强阴影
- 按钮hover：上移2px+阴影
- 链接hover：箭头向右移动4px
- 页面加载：淡入+上移动画

响应式：
- 移动端(<768px)：Grid变单列，Hero标题缩小到36px，汉堡菜单
- 平板(768-1024px)：2列Grid
- 桌面(>1024px)：3列Grid，1280px最大宽度居中

整体风格：Modern Minimalist + Corporate Approachable - 专业但友好，简洁但不冷淡，科技感但易接近。
```

---

**生成的完整分析文档**: `/Users/jerry/Desktop/Claude code/style-cloning/microsoft-ai-analysis.md`

**CSS 样式文件**: `/Users/jerry/Desktop/Claude code/style-cloning/microsoft-ai-style.css`
