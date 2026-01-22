# Style Transfer Templates

这个文档提供多种格式的风格迁移模板，帮助你将提取的风格应用到新项目中。

## 模板类型概览

1. **Design Tokens** - 设计令牌（变量系统）
2. **Style Guide Document** - 风格指南文档
3. **Component Specifications** - 组件规范
4. **Implementation Code** - 实现代码

根据你的项目类型和团队需求选择合适的模板。

---

## 模板 1：CSS Custom Properties（CSS 变量）

最通用的格式，适用于任何现代 Web 项目。

```css
/**
 * Design Tokens - [Project Name]
 * Extracted from: [Source URL or Description]
 * Date: [YYYY-MM-DD]
 */

:root {
  /* ============================================
     COLOR SYSTEM
     ============================================ */

  /* Primary Colors */
  --color-primary-50: #f0f9ff;
  --color-primary-100: #e0f2fe;
  --color-primary-200: #bae6fd;
  --color-primary-300: #7dd3fc;
  --color-primary-400: #38bdf8;
  --color-primary-500: #0ea5e9; /* Base */
  --color-primary-600: #0284c7;
  --color-primary-700: #0369a1;
  --color-primary-800: #075985;
  --color-primary-900: #0c4a6e;

  /* Secondary Colors */
  --color-secondary-500: #8b5cf6; /* Base */
  /* ... similar scale */

  /* Neutral Colors */
  --color-neutral-50: #fafafa;
  --color-neutral-100: #f5f5f5;
  --color-neutral-200: #e5e5e5;
  --color-neutral-300: #d4d4d4;
  --color-neutral-400: #a3a3a3;
  --color-neutral-500: #737373;
  --color-neutral-600: #525252;
  --color-neutral-700: #404040;
  --color-neutral-800: #262626;
  --color-neutral-900: #171717;

  /* Semantic Colors */
  --color-success: #22c55e;
  --color-warning: #f59e0b;
  --color-error: #ef4444;
  --color-info: #3b82f6;

  /* Functional Colors */
  --color-background: #ffffff;
  --color-surface: #f9fafb;
  --color-text-primary: #1f2937;
  --color-text-secondary: #6b7280;
  --color-text-tertiary: #9ca3af;
  --color-border: #e5e7eb;
  --color-divider: #f3f4f6;

  /* ============================================
     TYPOGRAPHY
     ============================================ */

  /* Font Families */
  --font-primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-secondary: 'Georgia', serif;
  --font-code: 'JetBrains Mono', 'Courier New', monospace;

  /* Font Sizes */
  --text-xs: 0.75rem;      /* 12px */
  --text-sm: 0.875rem;     /* 14px */
  --text-base: 1rem;       /* 16px */
  --text-lg: 1.125rem;     /* 18px */
  --text-xl: 1.25rem;      /* 20px */
  --text-2xl: 1.5rem;      /* 24px */
  --text-3xl: 1.875rem;    /* 30px */
  --text-4xl: 2.25rem;     /* 36px */
  --text-5xl: 3rem;        /* 48px */
  --text-6xl: 3.75rem;     /* 60px */

  /* Font Weights */
  --font-thin: 100;
  --font-light: 300;
  --font-normal: 400;
  --font-medium: 500;
  --font-semibold: 600;
  --font-bold: 700;
  --font-extrabold: 800;
  --font-black: 900;

  /* Line Heights */
  --leading-none: 1;
  --leading-tight: 1.25;
  --leading-snug: 1.375;
  --leading-normal: 1.5;
  --leading-relaxed: 1.625;
  --leading-loose: 2;

  /* Letter Spacing */
  --tracking-tighter: -0.05em;
  --tracking-tight: -0.025em;
  --tracking-normal: 0;
  --tracking-wide: 0.025em;
  --tracking-wider: 0.05em;
  --tracking-widest: 0.1em;

  /* ============================================
     SPACING
     ============================================ */

  --space-0: 0;
  --space-1: 0.25rem;   /* 4px */
  --space-2: 0.5rem;    /* 8px */
  --space-3: 0.75rem;   /* 12px */
  --space-4: 1rem;      /* 16px */
  --space-5: 1.25rem;   /* 20px */
  --space-6: 1.5rem;    /* 24px */
  --space-7: 1.75rem;   /* 28px */
  --space-8: 2rem;      /* 32px */
  --space-10: 2.5rem;   /* 40px */
  --space-12: 3rem;     /* 48px */
  --space-16: 4rem;     /* 64px */
  --space-20: 5rem;     /* 80px */
  --space-24: 6rem;     /* 96px */

  /* ============================================
     BORDER RADIUS
     ============================================ */

  --radius-none: 0;
  --radius-sm: 0.25rem;    /* 4px */
  --radius-base: 0.375rem; /* 6px */
  --radius-md: 0.5rem;     /* 8px */
  --radius-lg: 0.75rem;    /* 12px */
  --radius-xl: 1rem;       /* 16px */
  --radius-2xl: 1.5rem;    /* 24px */
  --radius-full: 9999px;   /* Circular */

  /* ============================================
     SHADOWS
     ============================================ */

  --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
  --shadow-base: 0 1px 3px 0 rgba(0, 0, 0, 0.1),
                 0 1px 2px 0 rgba(0, 0, 0, 0.06);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
               0 2px 4px -1px rgba(0, 0, 0, 0.06);
  --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1),
               0 4px 6px -2px rgba(0, 0, 0, 0.05);
  --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1),
               0 10px 10px -5px rgba(0, 0, 0, 0.04);
  --shadow-2xl: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
  --shadow-inner: inset 0 2px 4px 0 rgba(0, 0, 0, 0.06);

  /* ============================================
     TRANSITIONS
     ============================================ */

  --transition-fast: 150ms cubic-bezier(0.4, 0, 0.2, 1);
  --transition-base: 250ms cubic-bezier(0.4, 0, 0.2, 1);
  --transition-slow: 350ms cubic-bezier(0.4, 0, 0.2, 1);

  /* Easing Functions */
  --ease-in: cubic-bezier(0.4, 0, 1, 1);
  --ease-out: cubic-bezier(0, 0, 0.2, 1);
  --ease-in-out: cubic-bezier(0.4, 0, 0.2, 1);

  /* ============================================
     Z-INDEX LAYERS
     ============================================ */

  --z-base: 0;
  --z-dropdown: 1000;
  --z-sticky: 1100;
  --z-fixed: 1200;
  --z-modal-backdrop: 1300;
  --z-modal: 1400;
  --z-popover: 1500;
  --z-tooltip: 1600;

  /* ============================================
     BREAKPOINTS (for reference)
     ============================================ */

  /* Use in media queries:
  --breakpoint-sm: 640px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 1024px;
  --breakpoint-xl: 1280px;
  --breakpoint-2xl: 1536px;
  */
}

/* ============================================
   DARK MODE OVERRIDES
   ============================================ */

[data-theme="dark"] {
  --color-background: #0f172a;
  --color-surface: #1e293b;
  --color-text-primary: #f1f5f9;
  --color-text-secondary: #cbd5e1;
  --color-text-tertiary: #94a3b8;
  --color-border: #334155;
  --color-divider: #1e293b;
}

/* ============================================
   UTILITY CLASSES (optional)
   ============================================ */

.text-primary { color: var(--color-text-primary); }
.text-secondary { color: var(--color-text-secondary); }
.bg-surface { background: var(--color-surface); }
.rounded-base { border-radius: var(--radius-base); }
.shadow-base { box-shadow: var(--shadow-base); }
```

---

## 模板 2：JSON Design Tokens

适用于设计系统工具（Style Dictionary, Figma Tokens）。

```json
{
  "color": {
    "primary": {
      "50": { "value": "#f0f9ff" },
      "100": { "value": "#e0f2fe" },
      "500": { "value": "#0ea5e9" },
      "900": { "value": "#0c4a6e" }
    },
    "semantic": {
      "success": { "value": "{color.green.500}" },
      "error": { "value": "{color.red.500}" },
      "warning": { "value": "{color.yellow.500}" }
    }
  },
  "typography": {
    "fontFamily": {
      "primary": {
        "value": "'Inter', -apple-system, sans-serif"
      },
      "code": {
        "value": "'JetBrains Mono', monospace"
      }
    },
    "fontSize": {
      "xs": { "value": "0.75rem" },
      "sm": { "value": "0.875rem" },
      "base": { "value": "1rem" },
      "lg": { "value": "1.125rem" }
    },
    "fontWeight": {
      "normal": { "value": 400 },
      "medium": { "value": 500 },
      "semibold": { "value": 600 },
      "bold": { "value": 700 }
    }
  },
  "spacing": {
    "0": { "value": "0" },
    "1": { "value": "0.25rem" },
    "2": { "value": "0.5rem" },
    "4": { "value": "1rem" },
    "8": { "value": "2rem" }
  },
  "borderRadius": {
    "sm": { "value": "0.25rem" },
    "base": { "value": "0.375rem" },
    "md": { "value": "0.5rem" },
    "lg": { "value": "0.75rem" },
    "full": { "value": "9999px" }
  },
  "shadow": {
    "sm": {
      "value": {
        "offsetX": "0",
        "offsetY": "1px",
        "blur": "2px",
        "spread": "0",
        "color": "rgba(0, 0, 0, 0.05)"
      }
    },
    "md": {
      "value": [
        {
          "offsetX": "0",
          "offsetY": "4px",
          "blur": "6px",
          "spread": "-1px",
          "color": "rgba(0, 0, 0, 0.1)"
        },
        {
          "offsetX": "0",
          "offsetY": "2px",
          "blur": "4px",
          "spread": "-1px",
          "color": "rgba(0, 0, 0, 0.06)"
        }
      ]
    }
  }
}
```

---

## 模板 3：Tailwind Config

如果使用 Tailwind CSS。

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: {
          50: '#f0f9ff',
          100: '#e0f2fe',
          200: '#bae6fd',
          300: '#7dd3fc',
          400: '#38bdf8',
          500: '#0ea5e9',
          600: '#0284c7',
          700: '#0369a1',
          800: '#075985',
          900: '#0c4a6e',
        },
        secondary: {
          // ...
        },
        // Semantic colors
        success: '#22c55e',
        warning: '#f59e0b',
        error: '#ef4444',
        info: '#3b82f6',
      },
      fontFamily: {
        sans: ['Inter', 'system-ui', 'sans-serif'],
        serif: ['Georgia', 'serif'],
        mono: ['JetBrains Mono', 'monospace'],
      },
      fontSize: {
        'xs': '0.75rem',     // 12px
        'sm': '0.875rem',    // 14px
        'base': '1rem',      // 16px
        'lg': '1.125rem',    // 18px
        'xl': '1.25rem',     // 20px
        '2xl': '1.5rem',     // 24px
        '3xl': '1.875rem',   // 30px
        '4xl': '2.25rem',    // 36px
        '5xl': '3rem',       // 48px
      },
      spacing: {
        '0': '0',
        '1': '0.25rem',  // 4px
        '2': '0.5rem',   // 8px
        '3': '0.75rem',  // 12px
        '4': '1rem',     // 16px
        '6': '1.5rem',   // 24px
        '8': '2rem',     // 32px
        '12': '3rem',    // 48px
        '16': '4rem',    // 64px
        '24': '6rem',    // 96px
      },
      borderRadius: {
        'none': '0',
        'sm': '0.25rem',
        'DEFAULT': '0.375rem',
        'md': '0.5rem',
        'lg': '0.75rem',
        'xl': '1rem',
        '2xl': '1.5rem',
        'full': '9999px',
      },
      boxShadow: {
        'sm': '0 1px 2px 0 rgba(0, 0, 0, 0.05)',
        'DEFAULT': '0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06)',
        'md': '0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06)',
        'lg': '0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05)',
        'xl': '0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04)',
      },
    },
  },
  plugins: [],
}
```

---

## 模板 4：SCSS Variables

适用于 SCSS/Sass 项目。

```scss
// _variables.scss

// ============================================
// COLOR SYSTEM
// ============================================

// Primary Colors
$color-primary-50: #f0f9ff;
$color-primary-100: #e0f2fe;
$color-primary-500: #0ea5e9;
$color-primary-900: #0c4a6e;

// Semantic Colors
$color-success: #22c55e;
$color-warning: #f59e0b;
$color-error: #ef4444;

// ============================================
// TYPOGRAPHY
// ============================================

$font-primary: 'Inter', -apple-system, sans-serif;
$font-code: 'JetBrains Mono', monospace;

$text-xs: 0.75rem;
$text-sm: 0.875rem;
$text-base: 1rem;
$text-lg: 1.125rem;

$font-normal: 400;
$font-medium: 500;
$font-semibold: 600;
$font-bold: 700;

// ============================================
// SPACING
// ============================================

$space-1: 0.25rem;
$space-2: 0.5rem;
$space-4: 1rem;
$space-8: 2rem;

// ============================================
// BORDER RADIUS
// ============================================

$radius-sm: 0.25rem;
$radius-base: 0.375rem;
$radius-md: 0.5rem;
$radius-lg: 0.75rem;

// ============================================
// SHADOWS
// ============================================

$shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
$shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);

// ============================================
// BREAKPOINTS
// ============================================

$breakpoint-sm: 640px;
$breakpoint-md: 768px;
$breakpoint-lg: 1024px;
$breakpoint-xl: 1280px;

// Mixin for media queries
@mixin respond-to($breakpoint) {
  @if $breakpoint == 'sm' {
    @media (min-width: $breakpoint-sm) { @content; }
  }
  @else if $breakpoint == 'md' {
    @media (min-width: $breakpoint-md) { @content; }
  }
  @else if $breakpoint == 'lg' {
    @media (min-width: $breakpoint-lg) { @content; }
  }
}
```

---

## 模板 5：Component Specification Document

详细的组件规范文档模板。

```markdown
# Component Specification: Button

## Overview
Buttons are interactive elements that trigger actions when clicked.

## Variants

### Primary Button
**Purpose:** Main call-to-action
**Usage:** Use sparingly, typically one per screen

**Visual Specs:**
- Background: `var(--color-primary-500)` (#0ea5e9)
- Text: White (#ffffff)
- Font: Inter, 14px, weight 500
- Padding: 12px 24px
- Border radius: 6px
- Box shadow: 0 1px 2px rgba(0, 0, 0, 0.05)

**States:**
- Default: As above
- Hover: Background darkens to `--color-primary-600`, shadow increases to `--shadow-md`
- Active: Background darkens to `--color-primary-700`, shadow reduces
- Focus: 2px outline in `--color-primary-500` with 2px offset
- Disabled: Opacity 0.5, cursor not-allowed, no hover effects

**Code Example:**
```css
.button-primary {
  background: var(--color-primary-500);
  color: white;
  font-family: var(--font-primary);
  font-size: var(--text-sm);
  font-weight: var(--font-medium);
  padding: var(--space-3) var(--space-6);
  border-radius: var(--radius-base);
  box-shadow: var(--shadow-sm);
  transition: all var(--transition-fast);
}

.button-primary:hover {
  background: var(--color-primary-600);
  box-shadow: var(--shadow-md);
}

.button-primary:active {
  background: var(--color-primary-700);
  box-shadow: var(--shadow-sm);
}

.button-primary:focus-visible {
  outline: 2px solid var(--color-primary-500);
  outline-offset: 2px;
}

.button-primary:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
```

### Secondary Button
**Purpose:** Secondary actions
**Usage:** Multiple per screen allowed

**Visual Specs:**
- Background: Transparent
- Border: 1px solid `--color-border` (#e5e7eb)
- Text: `--color-text-primary` (#1f2937)
- Font: Inter, 14px, weight 500
- Padding: 12px 24px
- Border radius: 6px

**States:**
- Hover: Background `--color-neutral-50`, border `--color-neutral-300`
- Active: Background `--color-neutral-100`
- Focus: Same as primary
- Disabled: Same as primary

## Sizes

### Small
- Font size: 12px
- Padding: 8px 16px

### Medium (Default)
- Font size: 14px
- Padding: 12px 24px

### Large
- Font size: 16px
- Padding: 16px 32px

## Accessibility

- **Minimum target size:** 44x44px (WCAG 2.1)
- **Color contrast:** 4.5:1 minimum for text (WCAG AA)
- **Keyboard:** Accessible via Tab, activated with Space/Enter
- **Screen reader:** Uses semantic `<button>` element with descriptive text

## Responsive Behavior

- Mobile (<768px): Full width by default
- Tablet/Desktop (≥768px): Inline width (auto)

## Usage Guidelines

**Do:**
- Use clear, action-oriented labels (e.g., "Save Changes", "Download Report")
- Place primary action on the right in Western layouts
- Maintain consistent spacing between buttons (16px minimum)

**Don't:**
- Don't use more than one primary button per section
- Don't use vague labels like "Click Here" or "Submit"
- Don't disable buttons without explanation
```

---

## 模板 6：Style Guide Document

完整的风格指南文档。

```markdown
# [Project Name] Style Guide

## Introduction

This style guide documents the visual design system for [Project Name]. It ensures consistency across all touchpoints and provides clear guidance for designers and developers.

**Source:** Extracted from [URL or description]
**Version:** 1.0
**Last Updated:** [Date]

---

## Design Principles

1. **Clarity Over Cleverness**
   - Prioritize user understanding over visual complexity
   - Use familiar patterns where possible

2. **Consistency Breeds Trust**
   - Maintain visual consistency across all screens
   - Reuse components and patterns

3. **Accessibility First**
   - Meet WCAG 2.1 AA standards minimum
   - Design for all users, all abilities

---

## Color Palette

### Primary Colors
[Color swatch image]

- **Primary 500:** #0ea5e9
- **Usage:** Primary actions, links, brand emphasis
- **Accessibility:** Passes WCAG AA for text on white (4.57:1)

### Semantic Colors

- **Success:** #22c55e (Green) - Confirmations, positive outcomes
- **Warning:** #f59e0b (Amber) - Cautions, attention needed
- **Error:** #ef4444 (Red) - Errors, destructive actions
- **Info:** #3b82f6 (Blue) - Informational messages

### Usage Examples

```
✅ Correct: Use primary color for main CTA buttons
❌ Incorrect: Use primary color for body text

✅ Correct: Use error color sparingly for actual errors
❌ Incorrect: Use red/error color for all important information
```

---

## Typography

### Font Stack

**Primary:** Inter
- **Weights used:** 400 (Regular), 500 (Medium), 600 (Semibold), 700 (Bold)
- **Fallback:** -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif

**Monospace:** JetBrains Mono
- **Usage:** Code blocks, technical data
- **Fallback:** 'Courier New', monospace

### Type Scale

| Element | Size | Weight | Line Height | Usage |
|---------|------|--------|-------------|-------|
| H1 | 48px | 700 | 1.2 | Page titles |
| H2 | 36px | 700 | 1.25 | Section headers |
| H3 | 28px | 600 | 1.3 | Subsections |
| Body Large | 18px | 400 | 1.6 | Intro paragraphs |
| Body | 16px | 400 | 1.5 | Main content |
| Body Small | 14px | 400 | 1.5 | Secondary content |
| Caption | 12px | 400 | 1.4 | Labels, metadata |

### Responsive Typography

```
Desktop (>1024px): Use full scale
Tablet (768-1024px): Reduce headings by 15%
Mobile (<768px): Reduce headings by 25%, body text stable
```

---

## Spacing System

Based on 8px grid system.

**Scale:** 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 96

### Common Patterns

- **Card padding:** 24px
- **Button padding:** 12px 24px (vertical horizontal)
- **Section margin:** 64px (desktop), 48px (mobile)
- **Element gap:** 16px (default)

---

## Components

### Buttons
[See Component Specification document]

### Input Fields
[Specifications...]

### Cards
[Specifications...]

---

## Layout

### Grid System

- **Columns:** 12-column grid
- **Gutter:** 24px
- **Max width:** 1280px
- **Breakpoints:**
  - Mobile: <640px
  - Tablet: 640px - 1024px
  - Desktop: >1024px

### Container

```css
.container {
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 16px; /* Mobile */
}

@media (min-width: 768px) {
  .container {
    padding: 0 32px; /* Desktop */
  }
}
```

---

## Motion & Animation

### Principles

- **Purposeful:** Animations should serve a function
- **Fast:** Keep durations under 300ms for UI interactions
- **Natural:** Use easing functions that feel organic

### Duration

- **Fast:** 150ms - Hover states, tooltips
- **Medium:** 250ms - Dropdowns, modals appearing
- **Slow:** 350ms - Page transitions, complex animations

### Easing

- **Ease-out:** For elements entering (cubic-bezier(0, 0, 0.2, 1))
- **Ease-in:** For elements exiting (cubic-bezier(0.4, 0, 1, 1))
- **Ease-in-out:** For elements moving (cubic-bezier(0.4, 0, 0.2, 1))

---

## Accessibility Guidelines

### Color Contrast

- **Normal text:** Minimum 4.5:1 (WCAG AA)
- **Large text (18px+):** Minimum 3:1
- **UI components:** Minimum 3:1

### Interactive Elements

- **Minimum touch target:** 44x44px
- **Keyboard navigation:** All interactive elements focusable via Tab
- **Focus indicators:** 2px outline with 2px offset

### Screen Readers

- Use semantic HTML (`<button>`, `<nav>`, `<main>`, etc.)
- Provide alt text for images
- Include ARIA labels where needed

---

## Implementation Notes

### CSS Architecture

Using CSS Custom Properties for theming:

```css
/* Import design tokens */
@import 'tokens.css';

/* Use in components */
.button {
  background: var(--color-primary-500);
  padding: var(--space-3) var(--space-6);
  border-radius: var(--radius-base);
}
```

### Dark Mode

Toggle dark mode by setting `data-theme="dark"` on root element:

```html
<html data-theme="dark">
```

All color tokens automatically update via CSS custom properties.

---

## Resources

- **Design Tokens:** [Link to tokens file]
- **Component Library:** [Link to Storybook/Figma]
- **Brand Assets:** [Link to logo, illustrations]
- **Accessibility Checker:** [Link to tools]

---

## Changelog

### Version 1.0 (2024-01-15)
- Initial style guide creation
- Extracted from [source]
- Documented all core components
```

---

## 使用建议

### 选择合适的模板

| 项目类型 | 推荐模板 |
|---------|---------|
| 原生 HTML/CSS | CSS Custom Properties |
| React/Vue/Angular | CSS Custom Properties + Component Specs |
| Tailwind 项目 | Tailwind Config |
| Sass/SCSS 项目 | SCSS Variables |
| 设计系统 | JSON Tokens + Style Guide |
| 团队协作 | Complete Style Guide Document |

### 实施步骤

1. **选择主模板**：根据技术栈选择
2. **提取数值**：使用 extraction-patterns.md 的方法
3. **填充模板**：将提取的值填入模板
4. **验证应用**：在实际组件中测试
5. **文档化**：添加使用说明和示例

### 最佳实践

- **保持更新**：随着设计演进更新 tokens
- **版本控制**：记录每次修改
- **命名规范**：使用一致的命名约定
- **注释说明**：关键决策加注释

---

有了这些模板，你可以快速将提取的风格应用到任何项目中，确保设计的一致性和可维护性。
