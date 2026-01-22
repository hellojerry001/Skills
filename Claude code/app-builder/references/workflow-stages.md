# Workflow Stages - Detailed Guide

This document provides in-depth guidance for each stage of the app-builder workflow.

---

## Stage 1: Requirement Gathering {#stage-1}

**Duration:** 10-30 minutes
**Goal:** Transform vague ideas into concrete, actionable specifications

### Step-by-Step Process

#### 1.1 Initial Capture
Ask yourself (or the stakeholder):

```
What problem does this app solve?
Who will use it?
What's the core action users will take?
```

**Example:**
```
Problem: People struggle to stay focused while working
Users: Students, remote workers, freelancers
Core Action: Start a timed focus session
```

#### 1.2 Feature Breakdown

Use the MoSCoW method:

**Must Have** (Critical for V1):
- [ ] Feature 1
- [ ] Feature 2

**Should Have** (Important but not blocking):
- [ ] Feature 3
- [ ] Feature 4

**Could Have** (Nice additions):
- [ ] Feature 5

**Won't Have** (Out of scope):
- [ ] Feature 6

**Example: Pomodoro Timer**
```
Must Have:
- 25-minute countdown timer
- Start/pause/reset controls
- Audio notification when complete

Should Have:
- Adjustable timer duration
- Visual progress indicator

Could Have:
- Statistics tracking
- Multiple timer presets

Won't Have:
- User accounts
- Cloud sync
```

#### 1.3 User Stories

Format: "As a [user type], I want to [action], so that [benefit]"

**Template:**
```
As a [role],
I want to [feature],
So that [outcome].

Acceptance Criteria:
- [ ] Criterion 1
- [ ] Criterion 2
```

**Example:**
```
As a remote worker,
I want to start a focus session with one click,
So that I can quickly get into deep work without friction.

Acceptance Criteria:
- Timer starts immediately on button click
- Default duration is 25 minutes
- I can see time remaining at a glance
```

#### 1.4 Technical Constraints

Document limitations and requirements:

```
Platform: Web (desktop + mobile) / Mobile app / Desktop app
Technology: HTML/CSS/JS / React / Native / etc.
Browser Support: Modern browsers / IE11+ / etc.
Performance: Load time < 2s / 60fps animations / etc.
Offline: Required / Optional / Not needed
Data: No storage / localStorage / Backend required
```

#### 1.5 Design Direction

Provide visual guidance:

```
Style: Minimalist / Modern / Playful / Professional / etc.
Inspiration: [App name], [Website URL]
Colors: Preference or none
Layout: Single page / Multi-page / Dashboard
```

#### 1.6 Success Criteria

Define what "done" looks like:

```
Functional Success:
- [ ] All "Must Have" features work
- [ ] No critical bugs
- [ ] Runs on target platforms

Design Success:
- [ ] Matches design direction
- [ ] Professional appearance
- [ ] Responsive on all targets

User Success:
- [ ] Users can complete core action in < 3 clicks
- [ ] Intuitive without instructions
- [ ] Delightful to use
```

### Output Document Template

```markdown
# [App Name] - Requirements

## Problem Statement
[What problem does this solve?]

## Target Users
- User Type 1: [Description]
- User Type 2: [Description]

## Core Features (MoSCoW)

### Must Have
1. [Feature]: [Brief description]
2. [Feature]: [Brief description]

### Should Have
1. [Feature]: [Brief description]

### Could Have
1. [Feature]: [Brief description]

### Won't Have
1. [Feature]: [Reason]

## User Stories

### Story 1
As a [user],
I want to [action],
So that [benefit].

Acceptance Criteria:
- [ ] Criterion
- [ ] Criterion

## Technical Constraints
- Platform: [Web/Mobile/Desktop]
- Technology: [Stack]
- Browser Support: [Requirements]
- Performance: [Targets]
- Offline: [Yes/No]
- Data Storage: [Type]

## Design Direction
- Style: [Aesthetic]
- Inspiration: [References]
- Colors: [Palette]
- Layout: [Structure]

## Success Criteria
### Functional
- [ ] Criterion 1
- [ ] Criterion 2

### Design
- [ ] Criterion 1
- [ ] Criterion 2

### User Experience
- [ ] Criterion 1
- [ ] Criterion 2
```

---

## Stage 2: Prompt Enhancement {#stage-2}

**Duration:** 15-45 minutes
**Goal:** Create a prompt that generates high-quality first version

### Why This Stage Matters

Poor prompt → Mediocre output → More revisions
Great prompt → Strong foundation → Faster completion

**Time investment here = Time saved later**

### Enhancement Process

#### 2.1 Structure the Prompt

Use clear sections:

```
[App Name and Type]

Core Functionality:
- [Feature 1 with details]
- [Feature 2 with details]

Design Requirements:
- [Visual specifications]
- [Layout requirements]

Technical Requirements:
- [Tech stack]
- [Constraints]

User Experience:
- [Interaction patterns]
- [Quality expectations]

Output Format:
- [What you expect to receive]
```

#### 2.2 Add Specificity

**❌ Vague:** "Make it look good"
**✅ Specific:** "Use a soft blue color scheme (#5B8DEF), Inter font, and 16px border radius on all buttons"

**❌ Vague:** "Timer display"
**✅ Specific:** "Large centered timer display, 64px font size, showing MM:SS format, with a circular progress ring around it"

#### 2.3 Include Examples

When helpful, provide:
- Visual references: "Like the layout of [app name]"
- Code snippets: "Use this pattern for the timer logic"
- Color codes: "Primary: #5B8DEF, Background: #F7F9FC"

#### 2.4 Define Quality Standards

```
Code Quality:
- Clean, commented code
- Semantic HTML
- CSS organized by component
- DRY JavaScript

Accessibility:
- WCAG AA compliant
- Keyboard navigable
- Screen reader friendly

Performance:
- No external dependencies (if possible)
- Optimized images
- Fast load time (< 2s)
```

#### 2.5 Specify Output Format

```
Output Format:
- Single HTML file with embedded CSS and JavaScript
OR
- Separate HTML, CSS, and JS files
OR
- React component with TypeScript
OR
- [Your preferred format]

Include:
- All necessary code
- Comments explaining key sections
- Usage instructions if needed
```

### Prompt Template

```
Create a [type] application called "[name]" with the following specifications:

## Overview
[1-2 sentence description of what the app does]

## Core Functionality
1. [Feature 1]
   - [Detail]
   - [Detail]
2. [Feature 2]
   - [Detail]

## Design Requirements

### Layout
- [Structure description]
- [Component placement]

### Visual Style
- Style: [Minimalist/Modern/etc.]
- Colors:
  - Primary: [hex]
  - Secondary: [hex]
  - Background: [hex]
  - Text: [hex]
- Typography:
  - Font: [name]
  - Sizes: [specification]
- Spacing: [Guidelines]
- Borders/Radius: [Specifications]

### Components
- [Component 1]: [Description and styling]
- [Component 2]: [Description and styling]

## Technical Requirements
- Stack: [Technologies]
- Browser: [Support requirements]
- Responsive: [Yes/No, breakpoints]
- Offline: [Yes/No]
- Storage: [Type if needed]
- Performance: [Targets]

## User Experience
- [Interaction pattern 1]
- [Interaction pattern 2]
- [Feedback mechanisms]
- [Error handling]

## Quality Standards
- Code: [Clean, commented, semantic HTML]
- Accessibility: [WCAG level, keyboard nav]
- Performance: [No external deps, fast load]

## Output Format
[Specify exactly what files/format you want]

## Inspiration
[Optional: Reference apps or websites]
```

---

## Stage 3: Initial Generation {#stage-3}

**Duration:** 5-15 minutes (mostly waiting)
**Goal:** Get a working first version from Gemini

### Process

#### 3.1 Send to Gemini

1. Copy your enhanced prompt from Stage 2
2. Open Gemini (gemini.google.com)
3. Paste the entire prompt
4. Wait for generation

**Tips:**
- Use Gemini Pro for better results
- If output is truncated, ask: "Continue from where you left off"
- Save the conversation URL for reference

#### 3.2 Extract the Code

1. Copy the generated code
2. Save to appropriate files (HTML, CSS, JS)
3. If single file, save as `index.html`

#### 3.3 Test Immediately

```
Testing Checklist:
- [ ] Open in browser (double-click HTML file)
- [ ] Check: Does it load without errors?
- [ ] Test: Do all core features work?
- [ ] Try: Click all buttons/interactions
- [ ] Verify: Responsive on mobile (Dev Tools)
- [ ] Note: Any console errors?
```

#### 3.4 Document Initial State

Create a simple assessment:

```markdown
# V1.0 Initial Assessment

## What Works ✅
- [Feature that works]
- [Feature that works]

## What Doesn't Work ❌
- [Issue 1]
- [Issue 2]

## Visual Impressions
- [What looks good]
- [What needs improvement]

## Priority Fixes
1. [Critical fix]
2. [Important improvement]
3. [Nice to have]
```

### Common Issues & Solutions

**Issue 1: Code is truncated**
```
Solution: Reply with "Please continue the code from where you stopped"
```

**Issue 2: Console errors**
```
Solution: Copy error message, ask Gemini:
"I'm getting this error: [error]. Please fix it."
```

**Issue 3: Features don't work**
```
Solution: Be specific:
"The [feature] doesn't work. When I click [button], nothing happens.
Expected: [behavior]. Actual: [behavior]."
```

**Issue 4: Design is ugly**
```
Solution: Don't fix in Stage 3! Note it for Stage 4.
Stage 3 = functionality. Stage 4 = beauty.
```

### Red Flags (Stop and Revise Prompt)

🚩 **Code doesn't run at all**
→ Prompt might be too complex. Simplify and regenerate.

🚩 **Core features completely missing**
→ Prompt wasn't clear enough. Enhance and try again.

🚩 **Wrong technology used**
→ Technical requirements weren't specific. Clarify and regenerate.

### Green Lights (Proceed to Stage 4)

✅ Core features work (even if buggy)
✅ Basic structure is correct
✅ Code runs without critical errors
✅ Foundation is solid for optimization

---

## Stage 4: UI/UX Optimization {#stage-4}

**Duration:** 30-90 minutes
**Goal:** Transform functional into beautiful

### Focus Areas

#### 4.1 Color Scheme

**Process:**
1. Choose a primary color (or use style-cloning skill)
2. Generate a palette:
   - Primary: [Main brand color]
   - Primary Light: [Lighter variant]
   - Primary Dark: [Darker variant]
   - Background: [Usually off-white or light gray]
   - Surface: [Card/component backgrounds]
   - Text Primary: [Dark for main text]
   - Text Secondary: [Medium gray for secondary text]
   - Border: [Light gray]

**Tools:**
- Coolors.co (palette generator)
- Adobe Color
- Style-cloning skill (extract from references)

**Optimization Prompt Template:**
```
"Refine the color scheme with this palette:
- Primary: #[hex]
- Background: #[hex]
- Text: #[hex]
- Borders: #[hex]

Apply consistently across all components. Ensure WCAG AA contrast."
```

#### 4.2 Typography

**Improvements:**
- Consistent font stack
- Clear size hierarchy
- Appropriate line heights
- Letter spacing for large text

**Optimization Prompt:**
```
"Update typography:
- Font: [Name] or system font stack
- H1: [size]px, [weight], [line-height]
- Body: [size]px, [weight], [line-height]
- Small: [size]px, [weight], [line-height]
- All text should have good contrast and readability"
```

#### 4.3 Spacing & Layout

**Principles:**
- Consistent spacing scale (4px, 8px, 16px, 24px, 32px...)
- Generous white space
- Proper padding/margins
- Aligned elements

**Optimization Prompt:**
```
"Improve spacing and layout:
- Use 8px base spacing unit
- Add more breathing room (increase padding by 50%)
- Center main content with max-width: 1200px
- Align all elements to a visual grid"
```

#### 4.4 Component Polish

For each component:
- Buttons: Hover states, consistent sizing, clear affordance
- Inputs: Focus states, clear labels, validation feedback
- Cards: Shadows, hover effects, proper hierarchy
- Modals: Backdrop, animations, close buttons

**Optimization Prompt:**
```
"Polish all interactive components:
- Buttons: Add hover and active states, subtle shadows
- Inputs: Clear focus rings, proper spacing
- Add smooth transitions (200-300ms)
- Ensure all states are visually distinct"
```

#### 4.5 Responsive Design

**Breakpoints:**
- Mobile: < 640px
- Tablet: 640px - 1024px
- Desktop: > 1024px

**Optimization Prompt:**
```
"Make fully responsive:
- Mobile (<640px): Single column, larger touch targets, stack elements
- Tablet (640-1024px): 2-column where appropriate
- Desktop (>1024px): Full layout, max-width 1200px
- Test all breakpoints and ensure no horizontal scroll"
```

### Iterative Process

Don't try to fix everything at once. Instead:

**Iteration 1: Colors**
Focus only on color scheme. Test. Move on.

**Iteration 2: Typography**
Focus only on fonts and sizes. Test. Move on.

**Iteration 3: Spacing**
Focus only on layout and white space. Test. Move on.

**Iteration 4: Components**
Polish individual components. Test. Move on.

**Iteration 5: Responsive**
Ensure mobile/tablet work. Test. Done.

---

## Stage 5: Logo & Branding {#stage-5}

**Duration:** 20-60 minutes
**Goal:** Add visual identity

### Process

#### 5.1 Logo Creation

**Option A: Text Logo**
```
"Add a text-based logo:
- Text: '[App Name]'
- Font: [Specify, or 'bold sans-serif']
- Size: [pixels]
- Color: [hex]
- Position: Top left of navigation"
```

**Option B: Icon + Text**
```
"Create a simple icon logo:
- Icon: [Description, e.g., 'Stylized clock made of two circles']
- Style: Minimalist, single color
- Size: 32px x 32px
- Text: '[App Name]' next to icon
- Position: Top left"
```

**Option C: Use External**
If you have a logo file:
```
"Add the logo image:
- File: logo.svg (I'll provide)
- Size: 40px height, auto width
- Position: Top left of navbar
- Link: Clicking logo returns to home"
```

#### 5.2 Favicon

```
"Create and add a favicon:
- Same as logo icon or simplified version
- 32x32px
- Save as favicon.ico or favicon.svg
- Add to HTML <head>"
```

#### 5.3 Brand Colors Application

Ensure brand colors appear:
- Primary CTA buttons
- Logo
- Key highlights
- Interactive states

```
"Apply brand color [#hex] as the primary accent:
- All CTA buttons
- Links
- Active states
- Logo (if applicable)
- Progress indicators"
```

#### 5.4 Meta Tags

```html
<!-- Add to <head> -->
<meta name="description" content="[App description]">
<meta name="theme-color" content="[brand color hex]">
<meta property="og:title" content="[App Name]">
<meta property="og:description" content="[Description]">
<meta property="og:image" content="[preview-image.png]">
```

---

## Stage 6: Detail Refinement {#stage-6}

**Duration:** 1-3 hours
**Goal:** Perfect every interaction and add polish

### 6.1 Immersive Design

**Fullscreen Mode:**
```
"Add a fullscreen mode:
- Button in top right corner
- Clicking enters fullscreen (requestFullscreen API)
- ESC exits fullscreen
- Show exit hint for 3 seconds on entry"
```

**Focus Mode:**
```
"Add a focus mode toggle:
- Hides non-essential UI elements
- Shows only [core component]
- Dimmed background or blur effect
- Easy exit with ESC or toggle button"
```

**Dark Mode:**
```
"Implement dark mode:
- Toggle button in [location]
- Dark colors:
  - Background: #1a1a1a
  - Surface: #2d2d2d
  - Text: #e0e0e0
  - Borders: #404040
- Save preference to localStorage
- Smooth transition between modes (300ms)"
```

### 6.2 Animations

**Micro-Interactions:**
```
"Add micro-interactions:
- Buttons: Scale down on click (transform: scale(0.95))
- Hover: Lift effect on cards (translateY(-2px))
- Success: Checkmark animation when [action completes]
- Loading: Spinner or skeleton screen while [loading]
- All transitions: 200-300ms ease-out"
```

**Page Transitions:**
```
"Add entrance animations:
- Fade in content on page load (opacity 0 to 1, 500ms)
- Stagger elements (each 100ms delay)
- Use CSS animations or @keyframes
- Respect prefers-reduced-motion for accessibility"
```

**Progress Indicators:**
```
"Animate progress indicators:
- Smooth transitions between values
- Easing function for natural feel
- Color changes based on progress (green when complete)
- Confetti or celebration effect on 100%"
```

### 6.3 Performance Optimization

**Code:**
```
"Optimize code:
- Minify CSS and JavaScript (or provide minified version)
- Remove unused styles and functions
- Combine similar functions
- Add comments for complex logic"
```

**Assets:**
```
"Optimize assets:
- Compress images (use WebP if possible)
- Lazy load images below the fold
- Use SVG for icons (smaller file size)
- Inline critical CSS"
```

**Loading:**
```
"Improve perceived performance:
- Show skeleton screens while loading
- Progressive enhancement (core content first)
- Defer non-critical scripts
- Add loading indicators for async operations"
```

### 6.4 Error Handling

```
"Add comprehensive error handling:
- Validate user inputs before submission
- Show clear error messages (not technical jargon)
- Error states for all components
- Graceful degradation if features fail
- Clear recovery actions ('Try Again' button)"
```

### 6.5 Feature Additions

This is where you add "Could Have" features:

```
"Add [new feature]:
- [Specification]
- [Integration points]
- [UI requirements]
- Ensure it fits the existing design language"
```

**Common Additions:**
- Keyboard shortcuts
- Export/Import functionality
- Settings panel
- Notifications
- Statistics/Analytics
- Sharing capabilities

### Polish Checklist

Before moving to Stage 7:

**Visual Polish:**
- [ ] All animations smooth (60fps)
- [ ] No visual glitches or jank
- [ ] Consistent styling across all components
- [ ] Perfect alignment and spacing
- [ ] Beautiful on all screen sizes

**Functional Polish:**
- [ ] All features work flawlessly
- [ ] Error handling comprehensive
- [ ] Loading states for async operations
- [ ] Keyboard navigation works
- [ ] No console errors or warnings

**User Experience:**
- [ ] Intuitive without instructions
- [ ] Immediate feedback on all actions
- [ ] Delightful interactions
- [ ] Smooth and responsive
- [ ] Accessible (WCAG AA)

---

## Stage 7: Review & Documentation {#stage-7}

**Duration:** 30-60 minutes
**Goal:** Reflect, document, and learn

### Process

#### 7.1 Generate Review Document

Use the [review-template.md](review-template.md) to create:

1. **Project Overview**
2. **Technical Decisions**
3. **What Went Well**
4. **What Could Improve**
5. **Lessons Learned**
6. **Future Enhancements**

#### 7.2 Code Documentation

Ensure code includes:
- File structure explanation
- Function/component comments
- Setup instructions
- Dependencies list
- Browser support notes

#### 7.3 User Documentation (Optional)

If needed, create:
- README.md
- Usage guide
- FAQ
- Troubleshooting

#### 7.4 Archive & Tag

- Save final version with date
- Tag in version control (if using Git)
- Export review document as PDF
- Share with team if applicable

---

## Time Estimates Summary

| Stage | Minimum | Typical | Complex |
|-------|---------|---------|---------|
| 1. Requirements | 10 min | 20 min | 30 min |
| 2. Prompt Enhancement | 15 min | 30 min | 45 min |
| 3. Initial Generation | 5 min | 10 min | 15 min |
| 4. UI/UX Optimization | 30 min | 60 min | 90 min |
| 5. Logo & Branding | 20 min | 40 min | 60 min |
| 6. Detail Refinement | 60 min | 120 min | 180 min |
| 7. Review & Documentation | 30 min | 45 min | 60 min |
| **TOTAL** | **2.8 hrs** | **5.4 hrs** | **8 hrs** |

**Simple project:** 2-3 hours
**Typical project:** 4-6 hours
**Complex project:** 6-10 hours

---

**Next:** Proceed to [prompt-templates.md](prompt-templates.md) for ready-to-use templates, or [optimization-patterns.md](optimization-patterns.md) for specific improvement techniques.
