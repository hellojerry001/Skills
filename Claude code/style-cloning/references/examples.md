# Style Cloning Examples

这个文档提供完整的风格提取和迁移案例，展示从分析到实施的全过程。

## 案例 1：Linear - Developer-First Project Management

### 源信息
- **网站：** linear.app
- **风格类型：** Modern Minimalist + Developer-Focused
- **提取难度：** ⭐⭐⭐☆☆ (中等)

### Step 1: 视觉分析

#### 第一印象
- 干净、高对比度
- 大量使用紫色作为品牌色
- 密集的信息呈现
- 暗色模式为主

#### 详细提取

**配色方案：**
```css
/* Primary Colors */
--color-primary-purple: #5E6AD2;
--color-primary-blue: #3B82F6;

/* Backgrounds */
--color-bg-primary: #FFFFFF;    /* Light mode */
--color-bg-dark: #0F0F0F;       /* Dark mode (常用) */
--color-bg-surface: #1A1A1A;    /* Dark mode surface */
--color-bg-hover: #242424;      /* Hover state */

/* Text */
--color-text-primary: #E0E0E0;  /* Dark mode */
--color-text-secondary: #999999;
--color-text-tertiary: #666666;

/* Borders */
--color-border: #2A2A2A;
--color-border-hover: #3A3A3A;

/* Status Colors */
--color-status-todo: #6B7280;
--color-status-inprogress: #8B5CF6;
--color-status-done: #10B981;
--color-status-canceled: #EF4444;
```

**排版系统：**
```css
/* Font Family */
--font-primary: 'Inter', -apple-system, sans-serif;

/* Font Sizes (紧凑，信息密度高) */
--text-xs: 11px;    /* Metadata, labels */
--text-sm: 12px;    /* Secondary text */
--text-base: 13px;  /* Main UI text (注意：比标准 16px 小) */
--text-md: 14px;    /* Emphasized text */
--text-lg: 16px;    /* Section titles */
--text-xl: 20px;    /* Page titles */

/* Font Weights */
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;

/* Line Heights (紧凑) */
--leading-tight: 1.4;
--leading-normal: 1.5;
```

**间距系统：**
```css
/* 基于 4px */
--space-1: 4px;
--space-2: 8px;
--space-3: 12px;
--space-4: 16px;
--space-6: 24px;
--space-8: 32px;

/* 组件特定 */
--padding-list-item: 8px 12px;    /* 紧凑列表 */
--padding-panel: 16px;             /* 侧边栏面板 */
--gap-property: 12px;              /* 属性间距 */
```

**圆角系统：**
```css
--radius-sm: 4px;   /* Inputs, buttons */
--radius-md: 6px;   /* Cards, panels */
--radius-lg: 8px;   /* Modals */
```

**阴影系统：**
```css
/* 微妙的阴影，暗色模式下几乎不可见 */
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.3);
--shadow-md: 0 2px 8px rgba(0, 0, 0, 0.4);
--shadow-lg: 0 8px 24px rgba(0, 0, 0, 0.5);
```

### Step 2: 识别关键模式

#### 模式 1：紧凑型列表项
```css
.issue-row {
  display: flex;
  align-items: center;
  padding: 8px 12px;
  gap: 12px;
  border-bottom: 1px solid var(--color-border);
  font-size: 13px;
  transition: background 150ms ease;
}

.issue-row:hover {
  background: var(--color-bg-hover);
}

/* 状态指示器 */
.issue-status {
  width: 16px;
  height: 16px;
  border-radius: 50%;
  border: 2px solid currentColor;
}

/* 优先级图标 */
.issue-priority {
  width: 16px;
  height: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
}

/* ID 标签 */
.issue-id {
  color: var(--color-text-tertiary);
  font-size: 12px;
  font-variant-numeric: tabular-nums; /* 等宽数字 */
}
```

#### 模式 2：Command Palette（命令面板）
```css
.command-palette {
  background: var(--color-bg-surface);
  border: 1px solid var(--color-border);
  border-radius: 8px;
  box-shadow: var(--shadow-lg);
  width: 600px;
  max-height: 400px;
  overflow: hidden;
}

.command-input {
  background: transparent;
  border: none;
  border-bottom: 1px solid var(--color-border);
  padding: 16px;
  font-size: 14px;
  color: var(--color-text-primary);
}

.command-input::placeholder {
  color: var(--color-text-tertiary);
}

.command-results {
  padding: 4px;
  overflow-y: auto;
  max-height: 340px;
}

.command-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 8px 12px;
  border-radius: 4px;
  cursor: pointer;
}

.command-item:hover,
.command-item[data-selected] {
  background: var(--color-bg-hover);
}

.command-item kbd {
  margin-left: auto;
  font-size: 11px;
  color: var(--color-text-tertiary);
  font-family: var(--font-primary);
}
```

#### 模式 3：键盘快捷键显示
```css
kbd {
  display: inline-block;
  padding: 2px 6px;
  font-size: 11px;
  line-height: 1.4;
  color: var(--color-text-secondary);
  background: var(--color-bg-surface);
  border: 1px solid var(--color-border);
  border-radius: 3px;
  font-family: var(--font-primary);
  font-weight: 500;
}
```

### Step 3: 风格迁移实施

#### 实现 Linear 风格的 Task 列表

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <meta charset="UTF-8">
  <title>Linear-Style Task List</title>
  <style>
    /* Import Linear Design Tokens */
    :root[data-theme="dark"] {
      --color-bg-primary: #0F0F0F;
      --color-bg-surface: #1A1A1A;
      --color-bg-hover: #242424;
      --color-text-primary: #E0E0E0;
      --color-text-secondary: #999999;
      --color-text-tertiary: #666666;
      --color-border: #2A2A2A;
      --color-primary: #5E6AD2;
      --color-success: #10B981;
      --font-primary: 'Inter', -apple-system, sans-serif;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: var(--font-primary);
      background: var(--color-bg-primary);
      color: var(--color-text-primary);
      font-size: 13px;
      line-height: 1.5;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 24px;
    }

    .header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 16px 0;
      border-bottom: 1px solid var(--color-border);
      margin-bottom: 16px;
    }

    .header h1 {
      font-size: 20px;
      font-weight: 600;
    }

    .task-list {
      background: var(--color-bg-surface);
      border: 1px solid var(--color-border);
      border-radius: 6px;
      overflow: hidden;
    }

    .task-item {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 8px 12px;
      border-bottom: 1px solid var(--color-border);
      transition: background 150ms ease;
      cursor: pointer;
    }

    .task-item:last-child {
      border-bottom: none;
    }

    .task-item:hover {
      background: var(--color-bg-hover);
    }

    .task-checkbox {
      width: 16px;
      height: 16px;
      border: 2px solid var(--color-text-tertiary);
      border-radius: 50%;
      flex-shrink: 0;
      transition: all 150ms ease;
    }

    .task-item.completed .task-checkbox {
      background: var(--color-success);
      border-color: var(--color-success);
    }

    .task-id {
      color: var(--color-text-tertiary);
      font-size: 12px;
      font-variant-numeric: tabular-nums;
      width: 60px;
      flex-shrink: 0;
    }

    .task-title {
      flex: 1;
      color: var(--color-text-primary);
    }

    .task-item.completed .task-title {
      color: var(--color-text-secondary);
      text-decoration: line-through;
    }

    .task-assignee {
      width: 24px;
      height: 24px;
      border-radius: 50%;
      background: var(--color-primary);
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 11px;
      font-weight: 500;
    }

    .task-due {
      color: var(--color-text-tertiary);
      font-size: 12px;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="header">
      <h1>My Tasks</h1>
    </div>

    <div class="task-list">
      <div class="task-item">
        <div class="task-checkbox"></div>
        <div class="task-id">TASK-101</div>
        <div class="task-title">Implement user authentication</div>
        <div class="task-assignee">JD</div>
        <div class="task-due">Today</div>
      </div>

      <div class="task-item completed">
        <div class="task-checkbox"></div>
        <div class="task-id">TASK-98</div>
        <div class="task-title">Fix responsive layout issues</div>
        <div class="task-assignee">SM</div>
        <div class="task-due">Yesterday</div>
      </div>

      <div class="task-item">
        <div class="task-checkbox"></div>
        <div class="task-id">TASK-105</div>
        <div class="task-title">Add dark mode support</div>
        <div class="task-assignee">AL</div>
        <div class="task-due">Tomorrow</div>
      </div>
    </div>
  </div>
</body>
</html>
```

### Step 4: 关键学习点

#### Linear 风格的精髓

1. **信息密度优先**
   - 比常规设计更小的字号（13px vs 16px）
   - 更紧凑的行高和间距
   - 适合需要快速浏览大量信息的场景

2. **键盘优先交互**
   - 显著的快捷键提示
   - Command Palette 作为核心交互方式
   - 减少鼠标依赖

3. **微妙但一致的反馈**
   - 简单的 hover 状态（背景变化）
   - 快速的过渡效果（150ms）
   - 避免过度动画

4. **暗色模式优先**
   - 真正的暗色（#0F0F0F）而非深灰
   - 高对比度确保可读性
   - 适合长时间使用

---

## 案例 2：Stripe - Corporate Minimalist

### 源信息
- **网站：** stripe.com
- **风格类型：** Modern Minimalist + Corporate Professional
- **提取难度：** ⭐⭐☆☆☆ (简单)

### Step 1: 视觉分析

**配色方案：**
```css
/* Primary Colors */
--color-primary: #635BFF; /* Stripe Purple */
--color-primary-dark: #0A2540; /* Stripe Navy */

/* Backgrounds */
--color-bg: #FFFFFF;
--color-bg-subtle: #F7FAFC;

/* Text */
--color-text-primary: #0A2540;
--color-text-secondary: #425466;
--color-text-tertiary: #8898AA;

/* Borders */
--color-border: #E3E8EE;

/* Success/Error */
--color-success: #00D924;
--color-error: #DF1B41;
```

**排版系统：**
```css
--font-primary: 'Camphor', -apple-system, sans-serif;

/* 舒适的字号 */
--text-base: 16px;
--text-lg: 18px;
--text-xl: 21px;
--text-2xl: 28px;
--text-3xl: 40px;
--text-4xl: 56px;

/* 轻量的字重为主 */
--font-normal: 400;
--font-medium: 500;

/* 宽松的行高 */
--leading-normal: 1.6;
--leading-relaxed: 1.8;
```

**间距系统：**
```css
/* 宽松的间距 */
--space-4: 16px;
--space-6: 24px;
--space-8: 32px;
--space-12: 48px;
--space-16: 64px;
--space-24: 96px;
--space-32: 128px;
```

### Step 2: 关键模式

#### Hero Section
```css
.hero {
  padding: 128px 32px;
  text-align: center;
  max-width: 800px;
  margin: 0 auto;
}

.hero h1 {
  font-size: 56px;
  font-weight: 500;
  line-height: 1.1;
  margin-bottom: 24px;
  color: var(--color-text-primary);
}

.hero p {
  font-size: 21px;
  line-height: 1.6;
  color: var(--color-text-secondary);
  margin-bottom: 32px;
}

.hero .cta-button {
  background: var(--color-primary);
  color: white;
  padding: 14px 32px;
  font-size: 16px;
  font-weight: 500;
  border-radius: 6px;
  border: none;
  cursor: pointer;
  transition: opacity 200ms ease;
}

.hero .cta-button:hover {
  opacity: 0.9;
}
```

#### Feature Cards
```css
.feature-card {
  background: white;
  border: 1px solid var(--color-border);
  border-radius: 12px;
  padding: 48px;
  transition: box-shadow 300ms ease;
}

.feature-card:hover {
  box-shadow: 0 8px 32px rgba(10, 37, 64, 0.1);
}

.feature-card h3 {
  font-size: 28px;
  font-weight: 500;
  margin-bottom: 16px;
  color: var(--color-text-primary);
}

.feature-card p {
  font-size: 18px;
  line-height: 1.6;
  color: var(--color-text-secondary);
}
```

### Step 3: 关键学习点

#### Stripe 风格的精髓

1. **极简但优雅**
   - 大量留白
   - 简洁的配色（主要是紫色+深蓝）
   - 避免不必要的装饰

2. **舒适的可读性**
   - 较大的基础字号（16px+）
   - 宽松的行高（1.6-1.8）
   - 充足的段落间距

3. **微妙的交互**
   - 简单的 hover 效果（透明度或阴影）
   - 平滑的过渡（200-300ms）
   - 避免突兀的变化

4. **专业且平易近人**
   - 企业级的稳重感
   - 友好的紫色打破严肃
   - 清晰的信息层级

---

## 案例 3：Apple - Minimalist Luxury

### 源信息
- **网站：** apple.com
- **风格类型：** Premium Minimalist
- **提取难度：** ⭐⭐⭐⭐☆ (困难 - 细节极致)

### Step 1: 视觉分析

**配色方案：**
```css
/* Minimalist Palette */
--color-bg: #FBFBFD; /* 非纯白，更柔和 */
--color-text-primary: #1D1D1F; /* 非纯黑 */
--color-text-secondary: #6E6E73;
--color-accent: #0071E3; /* Apple Blue */

/* 极少的颜色使用 */
```

**排版系统：**
```css
--font-primary: 'SF Pro Display', -apple-system, sans-serif;
--font-secondary: 'SF Pro Text', -apple-system, sans-serif;

/* 大胆的标题 */
--text-hero: 96px;
--text-xxl: 80px;
--text-xl: 56px;

/* 精准的字重 */
--font-light: 300;
--font-regular: 400;
--font-semibold: 600;

/* 紧凑的标题行高 */
--leading-tight: 1.05;
```

**间距系统：**
```css
/* 大量负空间 */
--section-padding: 120px 0;
--element-gap: 40px;
```

### Step 2: 关键模式

#### Hero Section
```css
.apple-hero {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 0 20px;
}

.apple-hero h1 {
  font-size: 96px;
  font-weight: 600;
  line-height: 1.05;
  letter-spacing: -0.015em;
  margin-bottom: 8px;
}

.apple-hero .subtitle {
  font-size: 28px;
  font-weight: 400;
  line-height: 1.14;
  color: var(--color-text-secondary);
  margin-bottom: 24px;
}

.apple-hero .cta-group {
  display: flex;
  gap: 24px;
  justify-content: center;
  margin-top: 16px;
}

.apple-hero a {
  color: var(--color-accent);
  font-size: 21px;
  text-decoration: none;
}

.apple-hero a::after {
  content: ' ›';
}
```

### Step 3: 关键学习点

#### Apple 风格的精髓

1. **绝对的极简**
   - 几乎只用黑白灰
   - 去除所有边框、阴影
   - 产品图片是焦点

2. **精准的细节**
   - 字间距调整（letter-spacing）
   - 非纯黑/白的颜色选择
   - 完美的对齐和比例

3. **大胆的排版**
   - 超大的标题字号
   - 极紧凑的行高
   - 留白与文字的完美平衡

4. **隐藏的复杂性**
   - 看似简单，实则细节极致
   - 每个像素都经过深思熟虑
   - 难以复制的"奢华感"

---

## 提取技巧总结

### 从这些案例中学到的

#### 1. 风格不是孤立的元素

Linear 的风格 = 紧凑字号 + 暗色模式 + 等宽数字 + 快捷键提示
Stripe 的风格 = 紫色 + 宽松间距 + 大字号 + 微妙阴影
Apple 的风格 = 超大标题 + 极简色彩 + 完美对齐 + 精准细节

**所有元素组合**才构成完整的风格。

#### 2. 数值背后有逻辑

- Linear 的 13px：信息密度 > 舒适性
- Stripe 的 21px：可读性 > 空间利用
- Apple 的 96px：视觉冲击 > 常规

**理解"为什么"**比记住"是什么"更重要。

#### 3. 约束创造风格

- Linear：限制颜色种类，强调功能
- Stripe：限制装饰元素，强调内容
- Apple：限制一切，强调产品

**做减法**往往比做加法更能体现风格。

#### 4. 细节决定品质

同样是"极简风格"：
- 入门级：删除边框和阴影
- 进阶级：调整字间距和颜色
- 大师级：每个像素都恰到好处

**精益求精**是从"像"到"是"的关键。

---

## 练习建议

### 初级练习
1. 选择一个简单网站（如 Stripe）
2. 只提取配色和字号
3. 创建一个单页应用原型

### 中级练习
1. 选择一个中等复杂度网站（如 Linear）
2. 提取完整的设计系统
3. 实现 3-5 个核心组件

### 高级练习
1. 选择一个复杂网站（如 Apple）
2. 提取所有细节（包括微交互）
3. 创建完整的设计系统文档

---

**记住：** 风格提取的目标不是"抄袭"，而是理解优秀设计背后的原则和决策逻辑，然后将这些洞察应用到你自己的独特场景中。
