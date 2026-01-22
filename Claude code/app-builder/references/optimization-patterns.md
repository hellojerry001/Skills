# Optimization Patterns Guide

Proven patterns and techniques for optimizing applications at each stage.

---

## UI/UX Optimization Patterns {#ui-ux}

### Pattern 1: Progressive Enhancement

**Concept:** Start with core functionality, layer on enhancements

**Implementation:**
```
Level 1 (Core): Basic HTML structure, works without CSS/JS
Level 2 (Enhanced): CSS for visual design
Level 3 (Rich): JavaScript for interactions
Level 4 (Delightful): Animations and polish
```

**Example:**
```html
<!-- Level 1: Core -->
<form action="/submit" method="POST">
  <input type="text" name="email">
  <button type="submit">Subscribe</button>
</form>

<!-- Level 2: Styled -->
<form class="newsletter-form">
  <input type="email" class="form-input" placeholder="your@email.com">
  <button class="btn-primary">Subscribe</button>
</form>

<!-- Level 3: Interactive -->
<form id="newsletter-form">
  <!-- AJAX submission, validation -->
</form>

<!-- Level 4: Delightful -->
<!-- Add success animation, confetti, smooth transitions -->
```

---

### Pattern 2: Mobile-First Responsive Design

**Concept:** Design for small screens first, enhance for larger

**Implementation:**
```css
/* Base: Mobile styles (no media query) */
.container {
  padding: 16px;
}

.grid {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

/* Tablet: Enhance */
@media (min-width: 640px) {
  .container {
    padding: 24px;
  }

  .grid {
    flex-direction: row;
    flex-wrap: wrap;
  }
}

/* Desktop: Full experience */
@media (min-width: 1024px) {
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 32px;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
  }
}
```

---

### Pattern 3: Consistent Design System

**Concept:** Use CSS variables for maintainable styling

**Implementation:**
```css
:root {
  /* Colors */
  --color-primary: #5B8DEF;
  --color-primary-hover: #4A7BD8;
  --color-text: #1a1a1a;
  --color-background: #ffffff;

  /* Spacing */
  --space-xs: 4px;
  --space-sm: 8px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 32px;

  /* Typography */
  --font-size-sm: 14px;
  --font-size-base: 16px;
  --font-size-lg: 20px;
  --font-size-xl: 24px;

  /* Effects */
  --border-radius: 8px;
  --transition: 200ms ease;
  --shadow: 0 2px 8px rgba(0,0,0,0.1);
}

/* Usage */
.button {
  background: var(--color-primary);
  padding: var(--space-sm) var(--space-md);
  border-radius: var(--border-radius);
  font-size: var(--font-size-base);
  transition: all var(--transition);
}

.button:hover {
  background: var(--color-primary-hover);
  box-shadow: var(--shadow);
}
```

---

### Pattern 4: Accessible Interactive States

**Concept:** All interactive elements need clear states

**Implementation:**
```css
/* Button States */
.button {
  /* Default */
  background: var(--color-primary);
  color: white;
  cursor: pointer;
}

.button:hover {
  /* Hover: Visual change */
  background: var(--color-primary-hover);
  transform: translateY(-2px);
}

.button:active {
  /* Active: Pressed feeling */
  transform: translateY(0);
}

.button:focus-visible {
  /* Focus: Keyboard navigation */
  outline: 2px solid var(--color-primary);
  outline-offset: 2px;
}

.button:disabled {
  /* Disabled: Cannot interact */
  opacity: 0.5;
  cursor: not-allowed;
}
```

---

## Detail Optimization Patterns {#details}

### Pattern 5: Smooth Animations

**Concept:** Use GPU-accelerated properties for 60fps animations

**Best Properties to Animate:**
- ✅ transform (translate, scale, rotate)
- ✅ opacity
- ❌ width, height (causes reflow)
- ❌ top, left (causes reflow)

**Implementation:**
```css
/* ❌ Bad: Causes reflow */
.box:hover {
  width: 200px;
  left: 100px;
}

/* ✅ Good: GPU accelerated */
.box:hover {
  transform: translateX(100px) scale(1.2);
}

/* Smooth transitions */
.box {
  transition: transform 300ms cubic-bezier(0.4, 0, 0.2, 1);
}
```

---

### Pattern 6: Loading States

**Concept:** Never leave users wondering if something is happening

**Implementation:**
```html
<!-- Skeleton Screen -->
<div class="skeleton-card">
  <div class="skeleton-image"></div>
  <div class="skeleton-text"></div>
  <div class="skeleton-text short"></div>
</div>

<style>
.skeleton-card {
  background: #f0f0f0;
  border-radius: 8px;
  padding: 16px;
}

.skeleton-image {
  width: 100%;
  height: 200px;
  background: linear-gradient(
    90deg,
    #e0e0e0 25%,
    #f0f0f0 50%,
    #e0e0e0 75%
  );
  background-size: 200% 100%;
  animation: shimmer 1.5s infinite;
  border-radius: 4px;
}

@keyframes shimmer {
  0% { background-position: -100% 0; }
  100% { background-position: 100% 0; }
}

.skeleton-text {
  height: 16px;
  background: #e0e0e0;
  border-radius: 4px;
  margin-top: 12px;
}

.skeleton-text.short {
  width: 60%;
}
</style>
```

---

### Pattern 7: Error Handling

**Concept:** Provide clear, actionable error messages

**Implementation:**
```javascript
// ❌ Bad: Technical error
alert('Error: POST request failed with status 500');

// ✅ Good: User-friendly error
function showError(message) {
  const errorDiv = document.createElement('div');
  errorDiv.className = 'error-message';
  errorDiv.innerHTML = `
    <svg class="error-icon"><!-- Icon --></svg>
    <div class="error-content">
      <strong>Oops! Something went wrong</strong>
      <p>${message}</p>
      <button onclick="this.closest('.error-message').remove()">
        Dismiss
      </button>
    </div>
  `;
  document.body.appendChild(errorDiv);

  // Auto-dismiss after 5 seconds
  setTimeout(() => errorDiv.remove(), 5000);
}

// Usage
showError('Could not save your changes. Please try again.');
```

```css
.error-message {
  position: fixed;
  bottom: 24px;
  right: 24px;
  background: #fff;
  border-left: 4px solid #ef4444;
  padding: 16px;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  max-width: 400px;
  animation: slideIn 300ms ease-out;
}

@keyframes slideIn {
  from {
    transform: translateX(100%);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}
```

---

### Pattern 8: Micro-Interactions

**Concept:** Small animations that provide feedback

**Examples:**

**Button Click:**
```css
.button {
  transition: transform 100ms ease;
}

.button:active {
  transform: scale(0.95);
}
```

**Success Checkmark:**
```css
@keyframes checkmark {
  0% {
    opacity: 0;
    transform: scale(0) rotate(-45deg);
  }
  50% {
    opacity: 1;
    transform: scale(1.2) rotate(-45deg);
  }
  100% {
    transform: scale(1) rotate(-45deg);
  }
}

.checkmark {
  animation: checkmark 400ms cubic-bezier(0.65, 0, 0.35, 1);
}
```

**Toggle Switch:**
```css
.toggle {
  position: relative;
  width: 50px;
  height: 26px;
  background: #ccc;
  border-radius: 13px;
  transition: background 200ms ease;
}

.toggle::after {
  content: '';
  position: absolute;
  top: 2px;
  left: 2px;
  width: 22px;
  height: 22px;
  background: white;
  border-radius: 50%;
  transition: transform 200ms ease;
}

.toggle.active {
  background: var(--color-primary);
}

.toggle.active::after {
  transform: translateX(24px);
}
```

---

### Pattern 9: Keyboard Shortcuts

**Concept:** Power users appreciate keyboard navigation

**Implementation:**
```javascript
// Global keyboard shortcuts
document.addEventListener('keydown', (e) => {
  // Cmd/Ctrl + K: Open command palette
  if ((e.metaKey || e.ctrlKey) && e.key === 'k') {
    e.preventDefault();
    openCommandPalette();
  }

  // Escape: Close modals/overlays
  if (e.key === 'Escape') {
    closeModal();
  }

  // Space: Play/pause (if applicable)
  if (e.key === ' ' && e.target === document.body) {
    e.preventDefault();
    togglePlayPause();
  }

  // Arrow keys: Navigation
  if (e.key === 'ArrowUp' || e.key === 'ArrowDown') {
    navigateList(e.key);
  }
});

// Show keyboard shortcut hints
function showShortcutHints() {
  const hints = document.createElement('div');
  hints.className = 'shortcut-hints';
  hints.innerHTML = `
    <h3>Keyboard Shortcuts</h3>
    <ul>
      <li><kbd>Cmd</kbd> + <kbd>K</kbd> - Command Palette</li>
      <li><kbd>Esc</kbd> - Close modal</li>
      <li><kbd>Space</kbd> - Play/Pause</li>
      <li><kbd>↑</kbd> / <kbd>↓</kbd> - Navigate</li>
    </ul>
  `;
  document.body.appendChild(hints);
}
```

---

### Pattern 10: Performance Optimization

**Concept:** Fast apps feel better

**Techniques:**

**1. Debouncing:**
```javascript
function debounce(func, wait) {
  let timeout;
  return function executedFunction(...args) {
    clearTimeout(timeout);
    timeout = setTimeout(() => func(...args), wait);
  };
}

// Usage: Search input
const search = debounce((query) => {
  fetchResults(query);
}, 300);

searchInput.addEventListener('input', (e) => {
  search(e.target.value);
});
```

**2. Lazy Loading:**
```javascript
// Lazy load images
const images = document.querySelectorAll('img[data-src]');

const imageObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const img = entry.target;
      img.src = img.dataset.src;
      img.removeAttribute('data-src');
      imageObserver.unobserve(img);
    }
  });
});

images.forEach(img => imageObserver.observe(img));
```

**3. Virtual Scrolling (for long lists):**
```javascript
// Only render visible items
function renderVisibleItems(allItems, scrollTop, containerHeight, itemHeight) {
  const startIndex = Math.floor(scrollTop / itemHeight);
  const endIndex = Math.ceil((scrollTop + containerHeight) / itemHeight);

  const visibleItems = allItems.slice(startIndex, endIndex + 1);

  // Render only visible items
  return visibleItems.map((item, i) => ({
    ...item,
    offset: (startIndex + i) * itemHeight
  }));
}
```

---

## Checklist: Before Moving to Next Stage

### After Stage 4 (UI/UX):
- [ ] Color scheme is consistent and accessible
- [ ] Typography is clear and hierarchical
- [ ] Spacing follows a system
- [ ] All components are polished
- [ ] Responsive on all screen sizes
- [ ] No visual bugs or glitches

### After Stage 5 (Branding):
- [ ] Logo is present and looks professional
- [ ] Favicon is set
- [ ] Brand colors are used consistently
- [ ] Meta tags are updated
- [ ] Visual identity is cohesive

### After Stage 6 (Details):
- [ ] All animations are smooth (60fps)
- [ ] Loading states exist for async operations
- [ ] Error handling is user-friendly
- [ ] Keyboard navigation works
- [ ] Performance is optimized
- [ ] All edge cases handled
- [ ] Code is clean and commented

---

## Anti-Patterns to Avoid

### ❌ Anti-Pattern 1: Premature Optimization
**Problem:** Optimizing before core functionality works
**Solution:** Follow stages strictly - function first, polish later

### ❌ Anti-Pattern 2: Inconsistent Spacing
**Problem:** Random padding/margin values (13px, 17px, 23px...)
**Solution:** Use a spacing system (4, 8, 16, 24, 32...)

### ❌ Anti-Pattern 3: Poor Color Contrast
**Problem:** Light gray text on white background
**Solution:** Use WCAG contrast checker, aim for 4.5:1 minimum

### ❌ Anti-Pattern 4: Heavy Animations
**Problem:** Complex animations that cause lag
**Solution:** Use transform/opacity only, test on low-end devices

### ❌ Anti-Pattern 5: No Loading States
**Problem:** Users don't know if app is working
**Solution:** Always show loading indicators for async operations

### ❌ Anti-Pattern 6: Generic Error Messages
**Problem:** "Error 500" means nothing to users
**Solution:** Translate errors to user-friendly language with actions

### ❌ Anti-Pattern 7: Ignoring Mobile
**Problem:** Designing desktop-only, squishing to mobile
**Solution:** Design mobile-first, enhance for desktop

### ❌ Anti-Pattern 8: No Keyboard Access
**Problem:** Mouse-only interactions
**Solution:** Test tab navigation, add keyboard shortcuts

---

These patterns will help you create professional, polished applications. Apply them iteratively and test thoroughly.
