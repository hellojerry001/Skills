# Prompt Templates Library

Ready-to-use prompts for each stage of the app-builder workflow.

---

## Stage 2: Initial Generation Prompts

### Template 1: Web Application (HTML/CSS/JS)

```
Create a [app type] called "[App Name]" with the following specifications:

## Overview
[1-2 sentence description]

## Core Functionality
1. [Feature 1]: [Detailed description]
2. [Feature 2]: [Detailed description]
3. [Feature 3]: [Detailed description]

## Design Requirements

### Visual Style
- Style: [Minimalist/Modern/Playful/Professional]
- Color Scheme:
  - Primary: #[hex]
  - Secondary: #[hex]
  - Background: #[hex]
  - Text: #[hex]
- Typography:
  - Font: [Font name] or system fonts
  - H1: [size]px, [weight]
  - Body: [size]px, [weight]

### Layout
- Structure: [Description]
- Main components: [List]
- Responsive: Yes/No

### Components
- [Component 1]: [Specifications]
- [Component 2]: [Specifications]

## Technical Requirements
- Format: Single HTML file with embedded CSS and JavaScript
- Browser Support: Modern browsers (Chrome, Firefox, Safari, Edge)
- No External Dependencies: Use vanilla JavaScript, no libraries
- Offline Capable: All resources embedded
- Performance: Fast load time, smooth interactions

## User Experience
- [Key interaction 1]
- [Key interaction 2]
- Feedback: [How users get feedback]
- Error Handling: [How errors are shown]

## Code Quality
- Clean, well-commented code
- Semantic HTML5
- CSS organized by component
- DRY JavaScript
- Accessible (WCAG AA): Keyboard navigable, ARIA labels where needed

## Output Format
Provide a complete, working HTML file that can be saved and opened directly in a browser.
Include all CSS and JavaScript inline.
```

### Template 2: React Application

```
Create a React application for [purpose] with the following specifications:

## Project Structure
- Components: [List key components]
- State Management: [useState/Context/Redux/none]
- Routing: [React Router/none]

## Core Features
1. [Feature]: [Implementation details]
2. [Feature]: [Implementation details]

## Component Breakdown

### Component 1: [Name]
- Purpose: [What it does]
- Props: [List props and types]
- State: [Local state needed]
- Styling: [CSS modules/styled-components/Tailwind]

### Component 2: [Name]
- Purpose: [What it does]
- Props: [List props and types]
- State: [Local state needed]

## Design System
- Colors: [Palette]
- Typography: [Font and sizes]
- Spacing: [Scale]
- Components: [Button, Input, Card, etc. specifications]

## Technical Requirements
- React: [Version, if specific]
- TypeScript: Yes/No
- Build Tool: Vite/CRA/Next.js
- CSS: [Method - CSS Modules/Tailwind/Styled Components]
- Testing: [Jest/React Testing Library/None]

## Code Structure
```
src/
  components/
    [Component1].jsx
    [Component2].jsx
  App.jsx
  index.jsx
  styles/
    App.css
```

## Output
Provide complete code for all components, properly structured and ready to run.
Include package.json with dependencies.
Include setup instructions.
```

---

## Stage 4: UI/UX Optimization Prompts

### Prompt: Color Scheme Refinement

```
Refine the color scheme of [app name] with this improved palette:

**New Color System:**
- Primary: #[hex] (Main brand color)
- Primary Light: #[hex] (Hover states)
- Primary Dark: #[hex] (Active states)
- Background: #[hex] (Page background)
- Surface: #[hex] (Card/component backgrounds)
- Text Primary: #[hex] (Main text)
- Text Secondary: #[hex] (Secondary text)
- Border: #[hex] (Borders and dividers)
- Error: #[hex] (Error states)
- Success: #[hex] (Success states)

**Apply consistently:**
1. Replace all existing colors with this palette
2. Ensure WCAG AA contrast ratios (4.5:1 for text)
3. Use Primary for all CTAs and key actions
4. Use Surface for cards, modals, and elevated components
5. Update hover/active states to use Light/Dark variants

**Update these components:**
- Buttons: Primary color background
- Links: Primary color text
- Inputs: Border color for default, Primary for focus
- Headers: Text Primary for titles
- Body: Text Secondary for paragraphs
- Backgrounds: Use Background and Surface appropriately
```

### Prompt: Typography Enhancement

```
Enhance the typography system of [app name]:

**Font System:**
- Primary Font: '[Font Name]', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif
- Monospace Font: 'Monaco', 'Courier New', monospace (for code/numbers)

**Type Scale:**
- H1: [size]px / [weight] / line-height [ratio] (Page titles)
- H2: [size]px / [weight] / line-height [ratio] (Section headers)
- H3: [size]px / [weight] / line-height [ratio] (Subsections)
- Body Large: [size]px / [weight] / line-height [ratio] (Intro text)
- Body: [size]px / [weight] / line-height [ratio] (Main content)
- Body Small: [size]px / [weight] / line-height [ratio] (Captions)

**Spacing & Details:**
- Paragraph spacing: [size]px between paragraphs
- Letter spacing: [em value] for headings, normal for body
- Text color: Use Text Primary for headings, Text Secondary for body

**Apply to:**
- All heading elements (h1-h6)
- Paragraph text
- Button labels
- Input labels
- Navigation items

Ensure consistent hierarchy and improved readability.
```

### Prompt: Spacing & Layout Improvement

```
Improve the spacing and layout of [app name]:

**Spacing System:**
Use an 8px base unit with this scale:
- space-1: 4px (tight spacing)
- space-2: 8px (default gap)
- space-3: 12px (small padding)
- space-4: 16px (medium padding)
- space-6: 24px (large padding)
- space-8: 32px (section padding)
- space-12: 48px (large sections)
- space-16: 64px (page sections)

**Apply to:**
1. Container padding: space-6 on mobile, space-8 on desktop
2. Component padding: space-4 minimum for all cards/buttons
3. Element gaps: space-4 between related elements
4. Section spacing: space-12 between major sections
5. Button padding: space-3 vertical, space-6 horizontal

**Layout Improvements:**
- Center main content with max-width: 1200px
- Add generous white space (increase padding by 50%)
- Align elements to an 8px grid
- Use consistent margins between sections
- Ensure proper visual hierarchy through spacing

**Responsive:**
- Mobile: Reduce spacing by 25-30%
- Tablet: Slightly reduced spacing
- Desktop: Full spacing scale
```

### Prompt: Component Polish

```
Polish all interactive components in [app name]:

**Buttons:**
- Add distinct hover state: [specification]
- Add pressed/active state: [specification]
- Add focus ring for keyboard navigation: 2px solid primary color, 2px offset
- Smooth transitions: all 200ms ease-out
- Disabled state: opacity 0.5, cursor not-allowed

**Input Fields:**
- Border: 1px solid [border color]
- Focus state: 2px solid [primary color], slight scale (1.02)
- Error state: Red border, error message below
- Placeholder: [text secondary color], italic
- Padding: [space-3] vertical, [space-4] horizontal

**Cards:**
- Background: [surface color]
- Border radius: [size]px
- Shadow: 0 2px 8px rgba(0,0,0,0.1)
- Hover: Lift effect (translateY(-4px)), stronger shadow
- Transition: all 250ms cubic-bezier(0.4, 0, 0.2, 1)

**General:**
- All transitions should be smooth and natural
- Ensure all states are visually distinct
- Add subtle animations where appropriate
- Maintain consistency across all components
```

### Prompt: Responsive Design

```
Make [app name] fully responsive across all devices:

**Breakpoints:**
- Mobile: < 640px
- Tablet: 640px - 1024px
- Desktop: > 1024px

**Mobile (<640px):**
- Single column layout
- Stack all elements vertically
- Larger touch targets (minimum 44x44px)
- Font sizes: Reduce headings by 20-30%, keep body at 16px
- Padding: Use smaller spacing scale (reduce by 30%)
- Navigation: Hamburger menu or bottom tab bar
- Hide non-essential elements
- Full-width buttons

**Tablet (640-1024px):**
- 2-column layout where appropriate
- Slightly reduced font sizes from desktop
- Adequate spacing
- Hybrid navigation (visible but compact)

**Desktop (>1024px):**
- Multi-column layouts
- Full navigation bar
- Maximum content width: 1200px, centered
- Larger typography
- Full spacing scale

**Testing:**
- Ensure no horizontal scroll at any size
- All content readable at all sizes
- All interactions work on touch and mouse
- Images scale properly
- Tables scroll or adapt on mobile
```

---

## Stage 5: Logo & Branding Prompts

### Prompt: Add Simple Logo

```
Add a simple, modern logo to [app name]:

**Logo Design:**
- Type: [Text-only / Icon + Text / Icon-only]
- Icon: [Description if applicable, e.g., "Minimalist clock icon made of two overlapping circles"]
- Text: "[App Name]"
- Style: Clean, modern, minimal
- Colors: Use primary brand color (#[hex])

**Specifications:**
- Size: 40px height (auto width)
- Position: Top left of navigation bar
- Font: [Bold sans-serif / Match app font]
- Icon + Text: Icon 32px, text 18px, gap 8px

**Behavior:**
- Clicking logo returns to home/main view
- Hover: Subtle opacity change (0.8)
- Mobile: Slightly smaller (32px) if needed

**Implementation:**
- Use SVG for icon (scalable, crisp)
- CSS for text styling
- Flexbox for alignment

Create the logo and integrate it into the existing navigation.
```

### Prompt: Favicon

```
Create and add a favicon for [app name]:

**Design:**
- Match the main logo or create a simplified version
- Size: 32x32px (will scale to 16x16px automatically)
- Style: Simple, recognizable at small sizes
- Colors: Brand colors on [background color]

**Format:**
- SVG (preferred for modern browsers)
- Or PNG (32x32px and 16x16px versions)
- Or ICO file (multi-resolution)

**Implementation:**
Add to HTML <head>:
```html
<link rel="icon" type="image/svg+xml" href="favicon.svg">
<link rel="icon" type="image/png" sizes="32x32" href="favicon-32x32.png">
<link rel="icon" type="image/png" sizes="16x16" href="favicon-16x16.png">
```

**Include:**
- Favicon code (SVG or base64 PNG)
- HTML link tags
- Ensure it displays in browser tab
```

### Prompt: Brand Integration

```
Integrate brand identity throughout [app name]:

**Brand Colors:**
Apply [primary color] consistently:
- All CTA buttons
- Links and interactive elements
- Active states in navigation
- Progress indicators
- Selection highlights
- Focus rings

**Brand Elements:**
- Logo in navigation (top left)
- Favicon in browser tab
- Loading spinner uses brand color
- Success messages use brand color
- Illustrations/graphics match brand style

**Consistency:**
- Brand color appears in key moments
- Secondary colors complement, don't compete
- Neutral colors for backgrounds/text
- Brand creates visual anchors throughout UI

**Meta Tags:**
Update with brand info:
```html
<meta name="theme-color" content="#[brand color]">
<meta name="apple-mobile-web-app-title" content="[App Name]">
<meta property="og:title" content="[App Name]">
<meta property="og:description" content="[Description]">
```

Apply these branding elements cohesively.
```

---

## Stage 6: Detail Refinement Prompts

### Prompt: Add Smooth Animations

```
Add smooth animations and micro-interactions to [app name]:

**Button Interactions:**
```css
/* Hover */
button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  transition: all 200ms ease-out;
}

/* Click */
button:active {
  transform: translateY(0);
  transition: all 100ms ease-in;
}
```

**Card Hover Effects:**
```css
.card {
  transition: all 250ms cubic-bezier(0.4, 0, 0.2, 1);
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 24px rgba(0,0,0,0.15);
}
```

**Page Load Animation:**
```css
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-in {
  animation: fadeInUp 600ms ease-out;
}
```

**Stagger Elements:**
```css
.stagger-1 { animation-delay: 0ms; }
.stagger-2 { animation-delay: 100ms; }
.stagger-3 { animation-delay: 200ms; }
```

**Micro-Interactions:**
- Success checkmark animation
- Loading spinner
- Input focus glow
- Toggle switches
- Progress bar fill

**Accessibility:**
```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

Implement these animations throughout the app.
```

### Prompt: Fullscreen & Immersive Mode

```
Add fullscreen and immersive viewing mode to [app name]:

**Fullscreen Mode:**

1. Add fullscreen button (top right corner):
```html
<button id="fullscreen-btn" aria-label="Toggle fullscreen">
  <svg><!-- Fullscreen icon --></svg>
</button>
```

2. JavaScript implementation:
```javascript
function toggleFullscreen() {
  if (!document.fullscreenElement) {
    document.documentElement.requestFullscreen();
  } else {
    document.exitFullscreen();
  }
}
```

3. Visual feedback:
- Show "Press ESC to exit" message for 3 seconds on entry
- Change icon when in fullscreen
- Smooth transitions

**Focus/Immersive Mode:**

1. Toggle to hide non-essential UI:
```javascript
function toggleFocusMode() {
  document.body.classList.toggle('focus-mode');
}
```

2. CSS for focus mode:
```css
.focus-mode .sidebar { display: none; }
.focus-mode .header { opacity: 0.3; }
.focus-mode .main-content { max-width: 100%; }
```

3. Features:
- Keyboard shortcut (F key)
- Smooth transitions (300ms)
- Easy exit (button or ESC)
- Remember preference (localStorage)

Implement both modes with smooth transitions.
```

### Prompt: Dark Mode Implementation

```
Add a dark mode toggle to [app name] with smooth transitions:

**Dark Mode Colors:**
```css
[data-theme="dark"] {
  --color-background: #1a1a1a;
  --color-surface: #2d2d2d;
  --color-text-primary: #e0e0e0;
  --color-text-secondary: #b0b0b0;
  --color-border: #404040;
  /* Adjust other colors */
}
```

**Toggle Implementation:**

1. Toggle button in header:
```html
<button id="theme-toggle" aria-label="Toggle dark mode">
  <svg class="sun-icon"><!-- Sun icon --></svg>
  <svg class="moon-icon"><!-- Moon icon --></svg>
</button>
```

2. JavaScript:
```javascript
function toggleTheme() {
  const html = document.documentElement;
  const current = html.getAttribute('data-theme');
  const next = current === 'dark' ? 'light' : 'dark';
  html.setAttribute('data-theme', next);
  localStorage.setItem('theme', next);
}

// Load saved preference
const saved = localStorage.getItem('theme') || 'light';
document.documentElement.setAttribute('data-theme', saved);
```

3. Smooth transition:
```css
* {
  transition: background-color 300ms ease, color 300ms ease, border-color 300ms ease;
}
```

**Requirements:**
- Respect system preference on first load
- Save user preference
- Smooth color transitions
- Update all colors appropriately
- Icon changes with mode

Implement complete dark mode support.
```

### Prompt: Performance Optimization

```
Optimize [app name] for better performance:

**Code Optimization:**
1. Remove unused CSS and JavaScript
2. Minify CSS and JS (or provide minified versions)
3. Combine duplicate functions
4. Use event delegation for multiple elements
5. Debounce expensive operations (scroll, resize)

**Asset Optimization:**
1. Compress images (use tools like TinyPNG)
2. Use WebP format for images (with PNG fallback)
3. Use SVG for icons and illustrations
4. Lazy load images below the fold

**Loading Optimization:**
1. Inline critical CSS
2. Defer non-critical JavaScript
3. Preload important assets
4. Use skeleton screens for loading states

**Runtime Optimization:**
1. Use CSS transforms instead of position changes
2. Avoid layout thrashing
3. Use requestAnimationFrame for animations
4. Implement virtual scrolling for long lists

**Example Code:**
```html
<!-- Lazy loading images -->
<img src="placeholder.jpg" data-src="image.jpg" loading="lazy" alt="">

<!-- Preload critical assets -->
<link rel="preload" as="font" href="font.woff2" type="font/woff2" crossorigin>

<!-- Defer scripts -->
<script src="app.js" defer></script>
```

Apply these optimizations throughout the app.
```

---

## Stage 7: Review Documentation Prompt

```
Generate a comprehensive review document for [app name]:

**Document Structure:**

# [App Name] - Project Review

## Executive Summary
- Brief project description
- Development timeline
- Final outcome

## Technical Overview
### Technology Stack
- [List all technologies used]

### Architecture Decisions
- [Key decision 1]: Why we chose this approach
- [Key decision 2]: Trade-offs considered

### File Structure
```
[Show final file structure]
```

## Development Journey

### Stage 1: Requirements
- Initial concept: [Description]
- Target users: [Who]
- Core features: [List]

### Stage 2: Prompt Engineering
- Challenges: [What was difficult to specify]
- Learnings: [What worked well in prompts]

### Stage 3: Initial Generation
- First version quality: [Assessment]
- Major issues: [Problems encountered]
- Quick wins: [What worked immediately]

### Stage 4-6: Optimization
- UI/UX improvements: [Key changes]
- Branding additions: [What was added]
- Detail refinements: [Polish applied]

## What Went Well ✅
1. [Success 1]: [Why it worked]
2. [Success 2]: [Why it worked]
3. [Success 3]: [Why it worked]

## Challenges & Solutions ⚠️
1. **Challenge:** [Problem]
   **Solution:** [How we solved it]
   **Learning:** [Takeaway]

2. **Challenge:** [Problem]
   **Solution:** [How we solved it]
   **Learning:** [Takeaway]

## Key Learnings 💡
### Technical Learnings
- [Learning 1]
- [Learning 2]

### Process Learnings
- [Learning 1]
- [Learning 2]

### Prompt Engineering Learnings
- [What made prompts effective]
- [What to avoid in future]

## Code Quality Assessment
- **Maintainability:** [Rating/Notes]
- **Performance:** [Rating/Notes]
- **Accessibility:** [Rating/Notes]
- **Responsive Design:** [Rating/Notes]

## Future Enhancements 🚀

### Priority 1 (Next Sprint)
- [ ] [Enhancement]
- [ ] [Enhancement]

### Priority 2 (Future)
- [ ] [Enhancement]
- [ ] [Enhancement]

### Nice to Have
- [ ] [Enhancement]
- [ ] [Enhancement]

## Metrics & Impact
- Development time: [Hours]
- Iterations: [Number]
- Lines of code: [Approximate]
- File size: [KB]
- Load time: [Seconds]

## Recommendations for Similar Projects
1. [Recommendation]: [Explanation]
2. [Recommendation]: [Explanation]
3. [Recommendation]: [Explanation]

## Conclusion
[Summary paragraph about the project's success and key takeaways]

---
**Generated:** [Date]
**Developer:** [Name]
**Version:** [1.0]
```

---

## Quick Reference: Common Fixes

### Fix: Console Errors
```
"I'm getting this error: [paste error message]

Please identify the issue and provide the corrected code."
```

### Fix: Feature Not Working
```
"The [feature name] doesn't work. When I [action], [what happens] instead of [expected behavior].

Please debug and fix this issue."
```

### Fix: Style Issues
```
"The [element] looks wrong on [device/size]:
- Current: [description]
- Expected: [description]

Please fix the responsive styling."
```

### Fix: Performance Issues
```
"The app feels slow when [action].

Please optimize this interaction and ensure smooth 60fps performance."
```

---

Use these templates as starting points. Customize them for your specific needs and preferences.
