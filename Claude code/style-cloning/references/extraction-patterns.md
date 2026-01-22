# Style Extraction Patterns

这个文档提供系统化的方法来提取各类设计元素的风格特征。

## 提取方法论

### 自上而下 vs 自下而上

**自上而下（推荐用于整体风格理解）**
1. 先识别整体设计哲学
2. 再分析如何体现在各个元素中
3. 最后提取具体数值

**自下而上（推荐用于详细复刻）**
1. 先提取所有具体数值
2. 再识别其中的系统和规律
3. 最后总结设计原则

**最佳实践：两种方法结合使用**

## 模式 1：色彩系统提取

### 提取流程

#### Step 1: 色彩清单
使用取色工具记录所有出现的颜色：
- 背景色
- 文字色
- 边框色
- 阴影色
- 交互状态色（hover, active, focus）

**工具推荐：**
- 浏览器开发者工具（F12 → Elements → Computed）
- ColorZilla（浏览器插件）
- Figma/Sketch 的取色器

#### Step 2: 色彩分类
将清单中的颜色归类：

```
Primary Colors（品牌主色）:
- Main: #1a73e8
- Light: #4285f4
- Dark: #1557b0

Secondary Colors（辅助色）:
- Main: #34a853
- Light: #46b15c
- Dark: #2d8e47

Neutral Colors（中性色）:
- Background: #ffffff
- Surface: #f8f9fa
- Border: #dadce0
- Text Primary: #202124
- Text Secondary: #5f6368
- Text Disabled: #9aa0a6

Status Colors（状态色）:
- Success: #34a853
- Warning: #fbbc04
- Error: #ea4335
- Info: #4285f4
```

#### Step 3: 识别色彩关系

**问自己：**
1. 颜色之间是如何关联的？
   - 是否使用了相同的色相，只改变明度/饱和度？
   - 是否有固定的对比度比例？
   - 是否遵循某种配色理论（互补色、三角色、类比色）？

2. 变体是如何生成的？
   - Hover 状态：原色 + 10% 亮度？
   - Disabled 状态：降低 opacity 到 50%？
   - Light 版本：混入 20% 白色？

**示例分析：**
```
发现规律：
- Primary Light = Primary + 15% brightness
- Primary Dark = Primary - 15% brightness
- All colors use 5:1 contrast ratio minimum (WCAG AA)
- Hover states: darken by 8%
- Disabled: opacity 0.38
```

#### Step 4: 文档化色彩系统

```css
/* Design Tokens: Color System */
:root {
  /* Base Colors */
  --color-primary-base: #1a73e8;
  --color-primary-light: #4285f4;
  --color-primary-dark: #1557b0;

  /* Semantic Colors */
  --color-background: #ffffff;
  --color-surface: #f8f9fa;
  --color-text-primary: #202124;
  --color-text-secondary: #5f6368;

  /* Interactive States */
  --color-hover-overlay: rgba(0, 0, 0, 0.08);
  --color-active-overlay: rgba(0, 0, 0, 0.12);
  --color-disabled-opacity: 0.38;
}
```

### 高级技巧：色彩心理学分析

不仅提取数值，还要理解颜色选择的意图：

| 颜色 | 心理学 | 常见用途 |
|------|--------|----------|
| 蓝色 | 信任、专业、冷静 | 金融、企业、科技产品 |
| 绿色 | 成功、成长、安全 | 健康、环保、金融 |
| 红色 | 紧急、激情、警告 | 错误提示、促销、警告 |
| 紫色 | 创造力、奢华、智慧 | 创意工具、高端产品 |
| 橙色 | 活力、友好、创新 | 社交、电商、娱乐 |
| 灰色 | 中性、专业、现代 | 背景、辅助信息 |

## 模式 2：排版系统提取

### 提取流程

#### Step 1: 字体家族识别

**方法 1：浏览器检查**
```
1. 右键元素 → 检查（Inspect）
2. 查看 Computed 标签页
3. 找到 font-family 属性
```

**方法 2：字体识别工具**
- WhatFont（浏览器插件）
- Font Ninja
- WhatTheFont（上传截图识别）

#### Step 2: 排版清单

记录所有文字元素的样式：

```
Headings:
- H1: Inter 48px/56px, weight 700, -0.02em
- H2: Inter 36px/44px, weight 700, -0.01em
- H3: Inter 28px/36px, weight 600, -0.01em
- H4: Inter 24px/32px, weight 600, normal
- H5: Inter 20px/28px, weight 600, normal
- H6: Inter 18px/24px, weight 600, normal

Body Text:
- Large: Inter 18px/28px, weight 400, normal
- Base: Inter 16px/24px, weight 400, normal
- Small: Inter 14px/20px, weight 400, normal

Special:
- Caption: Inter 12px/16px, weight 400, 0.01em
- Code: 'Monaco' 14px/20px, weight 400, normal
- Button: Inter 14px/20px, weight 500, 0.01em
```

格式：`字体名 字号/行高, 字重, 字间距`

#### Step 3: 识别排版比例

**Type Scale（字号比例）**

计算相邻字号之间的比例关系：
```
48 ÷ 36 = 1.33
36 ÷ 28 = 1.29
28 ÷ 24 = 1.17
24 ÷ 20 = 1.2
```

**常见比例系统：**
- 1.125 (Major Second)
- 1.2 (Minor Third)
- 1.25 (Major Third)
- 1.333 (Perfect Fourth)
- 1.414 (Augmented Fourth)
- 1.5 (Perfect Fifth)
- 1.618 (Golden Ratio)

**发现：** 该设计没有严格遵循单一比例，而是在 1.17-1.33 之间变化，可能是为了在不同屏幕尺寸下保持灵活性。

#### Step 4: 行高规律

```
H1: 48px → 56px (line-height: 1.17)
Body: 16px → 24px (line-height: 1.5)
Caption: 12px → 16px (line-height: 1.33)
```

**规律识别：**
- 标题：1.1-1.3 倍行高（紧凑）
- 正文：1.4-1.6 倍行高（舒适阅读）
- 说明文字：1.2-1.4 倍行高（紧凑但可读）

#### Step 5: 文档化排版系统

```css
/* Typography System */
:root {
  /* Font Families */
  --font-primary: 'Inter', -apple-system, system-ui, sans-serif;
  --font-code: 'Monaco', 'Courier New', monospace;

  /* Font Sizes */
  --text-xs: 0.75rem;   /* 12px */
  --text-sm: 0.875rem;  /* 14px */
  --text-base: 1rem;    /* 16px */
  --text-lg: 1.125rem;  /* 18px */
  --text-xl: 1.25rem;   /* 20px */
  --text-2xl: 1.5rem;   /* 24px */
  --text-3xl: 1.75rem;  /* 28px */
  --text-4xl: 2.25rem;  /* 36px */
  --text-5xl: 3rem;     /* 48px */

  /* Font Weights */
  --font-normal: 400;
  --font-medium: 500;
  --font-semibold: 600;
  --font-bold: 700;

  /* Line Heights */
  --leading-tight: 1.25;
  --leading-normal: 1.5;
  --leading-relaxed: 1.75;

  /* Letter Spacing */
  --tracking-tight: -0.02em;
  --tracking-normal: 0;
  --tracking-wide: 0.01em;
}
```

### 高级技巧：响应式排版

检查排版在不同屏幕下的变化：

```css
/* 桌面 */
h1 { font-size: 48px; }
body { font-size: 16px; }

/* 平板 */
@media (max-width: 768px) {
  h1 { font-size: 36px; }  /* 缩小 25% */
  body { font-size: 16px; } /* 保持不变 */
}

/* 手机 */
@media (max-width: 480px) {
  h1 { font-size: 32px; }  /* 再缩小 */
  body { font-size: 14px; } /* 稍微缩小 */
}
```

**规律：** 标题在小屏幕下缩放更激进，正文保持相对稳定。

## 模式 3：间距系统提取

### 提取流程

#### Step 1: 测量所有间距

使用浏览器开发者工具或设计软件测量：
- Padding（内边距）
- Margin（外边距）
- Gap（网格/弹性布局间距）

**记录格式：**
```
Buttons:
- Padding: 12px 24px (vertical horizontal)
- Gap between buttons: 16px

Cards:
- Padding: 24px
- Gap between cards: 24px
- Margin bottom: 32px

Sections:
- Padding: 64px 0 (vertical horizontal)
- Gap between sections: 96px
```

#### Step 2: 寻找基础单位

列出所有测量值，寻找最大公约数：
```
出现的间距值：4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 96

最大公约数：4

可能的系统：
- 4px 基础单位 × 倍数：1x, 2x, 3x, 4x, 5x, 6x, 8x, 10x, 12x, 16x, 24x
```

#### Step 3: 识别间距层级

将间距值分组命名：

```
XXS: 4px   (元素内最小间距)
XS:  8px   (图标与文字)
SM:  12px  (紧凑型组件内部)
MD:  16px  (默认间距)
LG:  24px  (组件间距)
XL:  32px  (卡片内边距)
2XL: 48px  (区块间距)
3XL: 64px  (大区块间距)
4XL: 96px  (章节间距)
```

#### Step 4: 文档化间距系统

```css
/* Spacing System */
:root {
  --space-1: 0.25rem;  /* 4px */
  --space-2: 0.5rem;   /* 8px */
  --space-3: 0.75rem;  /* 12px */
  --space-4: 1rem;     /* 16px */
  --space-5: 1.25rem;  /* 20px */
  --space-6: 1.5rem;   /* 24px */
  --space-8: 2rem;     /* 32px */
  --space-10: 2.5rem;  /* 40px */
  --space-12: 3rem;    /* 48px */
  --space-16: 4rem;    /* 64px */
  --space-24: 6rem;    /* 96px */
}
```

### 高级技巧：语义化间距

不仅按大小定义，还按用途定义：

```css
:root {
  /* Component Spacing */
  --space-component-xs: var(--space-2);
  --space-component-sm: var(--space-4);
  --space-component-md: var(--space-6);
  --space-component-lg: var(--space-8);

  /* Layout Spacing */
  --space-section: var(--space-16);
  --space-page: var(--space-24);

  /* Content Spacing */
  --space-paragraph: var(--space-4);
  --space-heading: var(--space-8);
}
```

## 模式 4：圆角系统提取

### 提取方法

```
小元素圆角：
- Buttons: 6px
- Inputs: 6px
- Badges: 4px
- Chips: 16px (pill shape)

中等元素圆角：
- Cards: 8px
- Modals: 12px
- Popovers: 8px

大元素圆角：
- Images: 8px
- Panels: 12px
- Containers: 16px
```

### 识别规律

```
规律 1：小型交互元素（button, input）= 6px
规律 2：容器类元素（card, modal）= 8-12px
规律 3：大型布局元素 = 12-16px
规律 4：特殊形状（badges, avatars）= 50% (circle/pill)
```

### 文档化

```css
:root {
  --radius-sm: 0.25rem;  /* 4px - badges */
  --radius-md: 0.375rem; /* 6px - buttons, inputs */
  --radius-lg: 0.5rem;   /* 8px - cards */
  --radius-xl: 0.75rem;  /* 12px - modals */
  --radius-2xl: 1rem;    /* 16px - large containers */
  --radius-full: 9999px; /* circular/pill */
}
```

## 模式 5：阴影系统提取

### 提取流程

使用开发者工具查看 `box-shadow` 属性：

```
Button:
box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);

Card:
box-shadow: 0 2px 4px rgba(0, 0, 0, 0.06),
            0 4px 8px rgba(0, 0, 0, 0.04);

Modal:
box-shadow: 0 8px 16px rgba(0, 0, 0, 0.08),
            0 16px 32px rgba(0, 0, 0, 0.06);

Dropdown:
box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1),
            0 2px 4px rgba(0, 0, 0, 0.06);
```

### 识别层级系统

Material Design 启发的高程系统：

```
Elevation 0: none (平面元素)
Elevation 1: 0 1px 2px rgba(0,0,0,0.05) (微弱悬浮)
Elevation 2: 0 2px 4px rgba(0,0,0,0.06) (卡片)
Elevation 3: 0 4px 8px rgba(0,0,0,0.08) (下拉菜单)
Elevation 4: 0 8px 16px rgba(0,0,0,0.1) (模态框)
Elevation 5: 0 16px 32px rgba(0,0,0,0.12) (顶层元素)
```

### 文档化

```css
:root {
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 2px 4px rgba(0, 0, 0, 0.06),
               0 4px 8px rgba(0, 0, 0, 0.04);
  --shadow-lg: 0 4px 8px rgba(0, 0, 0, 0.08),
               0 8px 16px rgba(0, 0, 0, 0.06);
  --shadow-xl: 0 8px 16px rgba(0, 0, 0, 0.1),
               0 16px 32px rgba(0, 0, 0, 0.08);
}
```

## 模式 6：布局系统提取

### 网格系统

```
检查要点：
- 列数：12 columns? 16 columns? Fluid?
- Gutter（列间距）：16px? 24px? 32px?
- 最大宽度：1280px? 1440px? 100%?
- 边距（Container padding）：16px mobile, 32px desktop?
```

### 示例提取

```css
/* Layout System */
.container {
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 16px;
}

@media (min-width: 768px) {
  .container {
    padding: 0 32px;
  }
}

.grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 24px;
}
```

## 提取清单模板

使用这个清单确保完整提取：

### 视觉元素清单
- [ ] 颜色系统（primary, secondary, neutral, status）
- [ ] 排版系统（字体、字号、字重、行高、字间距）
- [ ] 间距系统（padding, margin, gap）
- [ ] 圆角系统
- [ ] 阴影系统
- [ ] 边框系统（宽度、样式、颜色）

### 组件清单
- [ ] 按钮（primary, secondary, ghost, sizes, states）
- [ ] 输入框（text, textarea, select, checkbox, radio）
- [ ] 卡片（不同变体）
- [ ] 导航（header, sidebar, breadcrumb）
- [ ] 反馈（alert, toast, modal, tooltip）

### 交互状态
- [ ] Hover（悬停）
- [ ] Active（激活）
- [ ] Focus（聚焦）
- [ ] Disabled（禁用）
- [ ] Loading（加载中）
- [ ] Error（错误）

### 响应式规则
- [ ] 断点（breakpoints）
- [ ] 移动端适配规则
- [ ] 排版缩放规则
- [ ] 组件变化规则

## 常见错误与解决

### 错误 1：只提取表面值，不识别系统

**错误示例：**
```
Button padding: 12px 24px
Card padding: 24px
Modal padding: 32px
```

**正确方法：**
```
发现系统：8px base unit
Button: 1.5x 3x (12px 24px)
Card: 3x (24px)
Modal: 4x (32px)

规律：padding 随组件大小成比例增长
```

### 错误 2：忽略响应式变化

**问题：** 只记录桌面端的值，没有考虑移动端的不同

**解决：** 明确记录不同断点下的值
```
Desktop (>1024px):
- H1: 48px
- Container padding: 32px

Tablet (768-1024px):
- H1: 40px
- Container padding: 24px

Mobile (<768px):
- H1: 32px
- Container padding: 16px
```

### 错误 3：混淆绝对值与相对值

**问题：** 在文档中同时使用 px 和 rem，造成混乱

**解决：** 统一使用一种单位系统，并注明转换关系
```
/* 基准：1rem = 16px */
--text-base: 1rem;     /* 16px */
--text-lg: 1.125rem;   /* 18px */
--text-xl: 1.25rem;    /* 20px */
```

## 工具推荐

### 浏览器工具
- Chrome DevTools（免费）
- Firefox Developer Tools（免费）

### 浏览器插件
- ColorZilla - 取色器
- WhatFont - 字体识别
- Dimensions - 测量间距
- Perfect Pixel - 像素对比

### 设计工具
- Figma（有免费版）
- Sketch（付费）
- Adobe XD（有免费版）

### 代码工具
- CSS Stats - 分析 CSS 使用情况
- Stylify Me - 自动提取网站风格
- HTML/CSS Analyzer - 分析页面样式

---

记住：提取风格不是机械地复制数值，而是理解设计背后的系统和逻辑。当你能够理解"为什么"做出这样的选择时，你才真正掌握了这个风格。
