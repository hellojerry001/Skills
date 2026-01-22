# Stage 2: Enhanced Prompt for Gemini

**目标：** 生成设计师个人网站的第一版代码
**使用平台：** Gemini
**预期输出：** 完整的 HTML/CSS/JavaScript 代码

---

## 🚀 复制以下 Prompt 发送给 Gemini

```
Create a modern designer portfolio website with the following specifications:

## Overview
A minimalist portfolio website for a designer showcasing Prompt templates, Skills projects, and Blog articles. The site features masonry (waterfall) layouts for visual appeal and easy browsing.

## Core Functionality

### 1. Navigation System
- **Sticky Header:** Remains visible on scroll
- **Logo:** Left side, links to home
- **Menu Items:** Prompts, Skills, Blog, More
- **Mobile:** Hamburger menu (appears < 768px)
- **Active State:** Highlight current page

### 2. Prompts Page (Default/Home)
- **Masonry Layout:** Waterfall grid showing Prompt cards
- **Card Content:**
  - Title (24px, semibold)
  - Short description (2-3 lines)
  - Category tag (small pill badge)
  - Optional thumbnail image
- **Interaction:**
  - Click card → Open modal with full Prompt content
  - "Copy" button to copy Prompt text to clipboard
  - Close modal with X button or clicking outside
- **Grid:**
  - Desktop (>1024px): 3 columns
  - Tablet (768-1024px): 2 columns
  - Mobile (<768px): 1 column

### 3. Skills Page
- **Masonry Layout:** Similar to Prompts
- **Card Content:**
  - Skill name (title)
  - Description
  - Screenshot or icon placeholder
  - "Download" button
- **Interaction:**
  - Click card → Show detailed modal
  - Download button → Trigger file download (.skill file)

### 4. Blog Page
- **List Layout:** Chronological order (newest first)
- **Article Card:**
  - Title
  - Publish date
  - Summary (3-4 lines)
  - Read time estimate
  - "Read More" button
- **Interaction:**
  - Click → Navigate to article detail page
  - Article page: Full content with back button

### 5. More Page
- **Sections:**
  - About Me: Brief bio (2-3 paragraphs)
  - Skills Stack: Visual list of technologies
  - Contact: Email, Twitter, GitHub links
  - Resume: Download button

## Design Requirements

### Visual Style
- **Aesthetic:** Modern Minimalist (inspired by Apple, Linear)
- **Mood:** Clean, professional, focused
- **Approach:** Content-first, generous whitespace

### Color Scheme
```css
/* Primary Colors */
--color-primary: #5B8DEF;      /* Brand blue */
--color-primary-dark: #4A7BD8; /* Hover state */

/* Neutral Colors */
--color-background: #FFFFFF;
--color-surface: #FAFAFA;      /* Card backgrounds */
--color-text-primary: #1A1A1A;
--color-text-secondary: #6E6E6E;
--color-border: #E5E5E5;

/* Ensure WCAG AA contrast ratios (4.5:1 minimum) */
```

### Typography
```css
/* Font Stack */
--font-primary: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;

/* Type Scale */
--text-hero: 56px;   /* Page titles */
--text-h1: 48px;     /* Section headers */
--text-h2: 36px;     /* Subsections */
--text-h3: 24px;     /* Card titles */
--text-body: 16px;   /* Main content */
--text-small: 14px;  /* Metadata */

/* Weights */
--font-regular: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;

/* Line Heights */
--leading-tight: 1.2;   /* Headlines */
--leading-normal: 1.6;  /* Body text */
```

### Spacing System
```css
/* 8px base unit */
--space-1: 4px;
--space-2: 8px;
--space-3: 12px;
--space-4: 16px;
--space-6: 24px;
--space-8: 32px;
--space-12: 48px;
--space-16: 64px;
--space-24: 96px;
```

### Layout
- **Container:** max-width 1200px, centered, padding 32px horizontal
- **Section Spacing:** 96px between major sections
- **Card Padding:** 24px internal
- **Card Gap:** 24px in masonry grid

### Components

#### Navigation Bar
```css
- Height: 64px
- Background: rgba(255, 255, 255, 0.95) with backdrop-filter: blur(10px)
- Border bottom: 1px solid #E5E5E5
- Logo: 24px font size, bold
- Menu links: 16px, medium weight, 32px gap between items
- Hover: Color transition to primary blue
```

#### Card (Prompt/Skill)
```css
- Background: #FFFFFF
- Border radius: 12px
- Box shadow: 0 2px 8px rgba(0, 0, 0, 0.08)
- Padding: 24px
- Transition: all 250ms ease
- Hover: transform translateY(-4px), shadow increase
```

#### Button
```css
- Primary: Blue background (#5B8DEF), white text
- Secondary: White background, blue border
- Padding: 12px 24px
- Border radius: 8px
- Font size: 14px, medium weight
- Hover: Darken by 10%, slight lift effect
```

#### Modal
```css
- Backdrop: rgba(0, 0, 0, 0.5)
- Content: White box, max-width 700px, centered
- Border radius: 16px
- Padding: 32px
- Close button: Top right corner
- Animation: Fade in, scale from 0.95 to 1
```

## Technical Requirements

### Structure
- **Format:** Single HTML file OR separate files (index.html, styles.css, script.js)
- **Approach:** Vanilla JavaScript (no frameworks)
- **Routing:** Hash-based routing (#prompts, #skills, #blog, #more)
- **Data:** Embedded JavaScript arrays for content (can be replaced with JSON later)

### Masonry Implementation
Use JavaScript to calculate and position cards:
```javascript
// Pseudo-code
function masonryLayout(containerSelector) {
  // Calculate column positions
  // Distribute cards to shortest column
  // Apply transforms or positions
  // Update on window resize
}
```

OR use CSS Grid approach:
```css
.masonry {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 24px;
  grid-auto-rows: 10px; /* Small row height for precise placement */
}
.card {
  grid-row-end: span X; /* Calculated based on content height */
}
```

### Copy to Clipboard
```javascript
function copyToClipboard(text) {
  navigator.clipboard.writeText(text)
    .then(() => alert('Copied!'))
    .catch(err => console.error('Copy failed:', err));
}
```

### Download Functionality
```javascript
function downloadFile(filename, content) {
  const blob = new Blob([content], { type: 'application/octet-stream' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = filename;
  a.click();
  URL.revokeObjectURL(url);
}
```

### Responsive Design
```css
/* Mobile First */
/* Base styles for mobile */

@media (min-width: 768px) {
  /* Tablet adjustments */
  .masonry { grid-template-columns: repeat(2, 1fr); }
}

@media (min-width: 1024px) {
  /* Desktop full layout */
  .masonry { grid-template-columns: repeat(3, 1fr); }
}
```

### Browser Support
- Modern browsers (Chrome, Firefox, Safari, Edge - latest versions)
- Mobile browsers (iOS Safari, Chrome Mobile)

### Performance
- Optimize images (use placeholders or small thumbnails)
- Lazy load images below the fold
- Debounce window resize events
- Smooth 60fps animations (use transform, opacity only)

## User Experience

### Interactions
- **Immediate feedback:** Button press animations, hover effects
- **Clear states:** Loading, success, error
- **Smooth transitions:** 250ms for cards, 150ms for buttons
- **Keyboard accessible:** Tab navigation, Enter/Space to activate

### Feedback Mechanisms
- Copy success: Brief "Copied!" notification (toast or inline)
- Download: Browser's native download notification
- Modal open/close: Smooth animations
- Page transitions: Fade effect when switching routes

### Error Handling
- Graceful degradation if features fail
- Clear error messages (not technical jargon)
- Fallbacks for unsupported features

## Sample Data Structure

### Prompts Array
```javascript
const prompts = [
  {
    id: 1,
    title: "UI Design Analysis Prompt",
    description: "Deeply analyze UI designs to extract design patterns and principles",
    category: "Design",
    thumbnail: "images/prompt1.jpg",
    content: `Full prompt text here...
    This is a multi-line prompt that will be displayed in the modal.
    Users can copy this entire text.`
  },
  {
    id: 2,
    title: "Style Cloning Prompt",
    description: "Extract visual style from websites for replication",
    category: "Development",
    thumbnail: "images/prompt2.jpg",
    content: `Another prompt...`
  }
  // More prompts...
];
```

### Skills Array
```javascript
const skills = [
  {
    id: 1,
    name: "Professional Prompt Writer",
    description: "Generate high-quality, structured prompts",
    screenshot: "images/skill1.png",
    downloadUrl: "downloads/professional-prompt-writer.skill",
    details: `Full description of the skill...`
  }
  // More skills...
];
```

### Blog Posts Array
```javascript
const blogPosts = [
  {
    id: 1,
    title: "Building a Design System from Scratch",
    date: "2024-01-15",
    readTime: "8 min",
    summary: "Learn the process of creating a comprehensive design system...",
    content: `<h2>Introduction</h2>
    <p>Full article content in HTML...</p>`
  }
  // More posts...
];
```

## Code Quality

### Standards
- **HTML:** Semantic HTML5 elements
- **CSS:** Organized by component, BEM naming or similar
- **JavaScript:** Clean, commented, DRY principle
- **Comments:** Explain complex logic, not obvious code

### Accessibility
- **WCAG AA:** Minimum standard
- **Semantic HTML:** Use proper heading hierarchy, landmarks
- **Keyboard Navigation:** All interactive elements focusable
- **Alt Text:** Descriptive text for images
- **ARIA Labels:** Where semantic HTML isn't enough
- **Color Contrast:** 4.5:1 for text, 3:1 for UI components

## Output Format

**Provide complete, working code in one of these formats:**

**Option 1 (Recommended):** Single HTML file
- All CSS in <style> tag
- All JavaScript in <script> tag
- Inline sample data
- Can be saved and opened directly in browser

**Option 2:** Separate files
- index.html
- styles.css
- script.js
- data.js (with sample data)
- Brief README explaining file structure

Include:
- Clean, well-commented code
- Sample data (3-5 items for each section)
- All functionality working
- Responsive design implemented
- Professional appearance matching the minimalist aesthetic

## Success Criteria

The generated code should:
✅ Run without errors in modern browsers
✅ Display all sections (Prompts, Skills, Blog, More)
✅ Implement working masonry layouts
✅ Include copy and download functionality
✅ Be fully responsive (mobile, tablet, desktop)
✅ Match the minimalist modern design aesthetic
✅ Have smooth animations and transitions
✅ Be accessible (keyboard navigable, good contrast)

---

**Please generate the complete code now. Thank you!**
```

---

## 📋 使用说明

1. **复制上面的整个 Prompt**（从 "Create a modern designer..." 到最后）
2. **打开 Gemini**（gemini.google.com）
3. **粘贴 Prompt** 并发送
4. **等待生成**（可能需要 1-2 分钟）
5. **保存代码**：
   - 如果是单文件：保存为 `index.html`
   - 如果是多文件：按 Gemini 的指示保存

## ⏱️ 预计时间

- Gemini 生成：5-10 分钟
- 测试代码：5 分钟
- **然后我们进入 Stage 4 优化！**

---

**准备好了吗？复制 Prompt 发送给 Gemini，然后把生成的代码发回来，我会帮你进行后续优化！** 🚀
