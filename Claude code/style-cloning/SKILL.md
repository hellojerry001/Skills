---
name: style-cloning
description: Extract and clone visual styles from screenshots or web pages for style transfer to other projects. Analyzes design elements including colors, typography, layout, spacing, and design principles. Use when the user provides a screenshot or URL and wants to replicate its visual style in another project, or needs detailed style documentation for design system creation.
---

# Style Cloning

Extract comprehensive style characteristics from visual sources and generate actionable style guides for design replication.

## Overview

This skill helps you systematically extract and document visual styles from existing designs, enabling accurate style transfer to new projects. It goes beyond surface-level observation to capture the underlying design principles and systematic choices that define a visual identity.

## When to Use This Skill

**Perfect for:**
- Analyzing a competitor's design style for inspiration
- Extracting design patterns from screenshots
- Creating style guides from existing products
- Replicating a specific visual aesthetic in a new project
- Building design systems based on reference materials
- Understanding the design principles behind successful interfaces

**Input formats:**
- Screenshots (PNG, JPG, WebP)
- Live website URLs
- Design mockups
- UI component libraries
- Brand examples

## Core Workflow

### Phase 1: Visual Analysis

**Step 1.1: Structural Deconstruction**
Break down the design into its fundamental components:
- Layout system (grid, columns, sections)
- Spacing hierarchy (margins, padding, gaps)
- Component organization
- Visual hierarchy patterns

**Step 1.2: Design Elements Extraction**
Identify and catalog:
- **Typography**: Font families, weights, sizes, line heights, letter spacing
- **Colors**: Primary palette, secondary palette, accent colors, gradients
- **Shapes**: Border radius, geometric patterns, icon style
- **Shadows**: Elevation system, shadow values, depth layers
- **Effects**: Transitions, animations, hover states

**Step 1.3: Principle Identification**
Uncover the underlying design principles:
- Design philosophy (minimalist, brutalist, skeuomorphic, etc.)
- Consistency patterns
- Visual rhythm
- Balance and proportion rules

See detailed patterns in [extraction-patterns.md](references/extraction-patterns.md)

### Phase 2: Style Categorization

Classify the extracted style into established categories to better understand its nature and guide replication.

**Major style categories:**
- Modern Minimalist
- Corporate Professional
- Vibrant Creative
- Dark/Neumorphic
- Retro/Vintage
- Technical/Developer-focused

Each category has specific characteristics and implementation patterns.

See complete taxonomy in [style-categories.md](references/style-categories.md)

### Phase 3: Transfer Documentation

Generate actionable documentation that enables accurate style replication:

**Output formats:**
1. **Design Tokens** - CSS variables, design system tokens
2. **Style Guide** - Human-readable documentation
3. **Component Specifications** - Detailed component blueprints
4. **Implementation Code** - Ready-to-use CSS/Tailwind classes

See templates in [transfer-templates.md](references/transfer-templates.md)

## Key Principles

### 1. Look for What's NOT There

The most defining characteristics of a style are often in the constraints:
- What effects are deliberately avoided?
- What colors are NOT used?
- What font weights are missing?

**Example:** Apple's design avoids gradients, heavy shadows, and decorative elements. These absences are as important as what's present.

### 2. Systematize, Don't Itemize

Don't just list "blue button" - identify the system:
- How do colors relate? (60-30-10 rule? Monochromatic?)
- What's the spacing scale? (4px base? 8px base? Golden ratio?)
- How do sizes progress? (Linear? Exponential? Fibonacci?)

### 3. Capture the Decision Logic

A style isn't just values - it's the logic behind them:
- Why this border radius? (Relates to content type? Screen size?)
- Why these font sizes? (Modular scale? Hierarchy levels?)
- Why this color? (Brand alignment? Accessibility? Emotion?)

### 4. Validate Through Variation

Test your understanding by asking:
- How would this style apply to a NEW component not in the original?
- What would a card look like? A modal? A form?
- If you can't answer, your extraction is incomplete.

## Three-Level Extraction Method

### Level 1: Surface (Appearance)
*What you see immediately*
- Specific color values: #1a73e8
- Exact font: Inter, 16px
- Precise spacing: 24px padding

**Use case:** Quick mockup, single-page replication

### Level 2: System (Pattern)
*How elements relate*
- Color relationships: Primary + 20% saturation = accent
- Typography scale: 1.25 ratio between levels
- Spacing system: 8px base unit × multipliers

**Use case:** Multi-page consistency, component library

### Level 3: Principle (Philosophy)
*Why choices were made*
- Design philosophy: "Calm, focused, distraction-free"
- Accessibility: WCAG AAA contrast ratios
- Psychology: Blue = trust, rounded = friendly

**Use case:** Long-term brand consistency, new product lines

## Quality Checklist

Before considering your style extraction complete:

**Completeness:**
- [ ] All major color uses documented (text, backgrounds, borders, states)
- [ ] Full typography system captured (headings, body, captions, code)
- [ ] Spacing system identified (consistent scale or custom values?)
- [ ] Interactive states defined (hover, active, focus, disabled)
- [ ] Responsive behavior noted (mobile, tablet, desktop)

**Accuracy:**
- [ ] Color values verified with color picker tools
- [ ] Font families and weights confirmed
- [ ] Spacing measured precisely (use browser dev tools)
- [ ] Shadow values extracted (x, y, blur, spread, color)

**Usability:**
- [ ] Documentation is clear enough for a designer to implement
- [ ] Examples provided for each major pattern
- [ ] Edge cases considered (dark mode, accessibility, etc.)
- [ ] Implementation code ready to use

**Transferability:**
- [ ] Can apply the style to components not in the original
- [ ] Style guide works for both design and development
- [ ] Tokens are framework-agnostic (when possible)

## Advanced Techniques

### Semantic Analysis
Go beyond visuals to understand semantic meaning:
- How does the style communicate hierarchy?
- What emotional tone does it convey?
- How does it guide user attention?

### Responsive Extraction
Document how the style adapts:
- Breakpoint behaviors
- Component transformations (desktop nav → mobile hamburger)
- Typography scaling strategies

### Motion & Interaction
Capture dynamic characteristics:
- Transition durations and easing functions
- Animation patterns
- Micro-interactions
- Loading states

## Resources

### references/extraction-patterns.md
Detailed methods for extracting each design element:
- Color extraction techniques
- Typography analysis methods
- Layout system reverse-engineering
- Component pattern identification

### references/style-categories.md
Visual style taxonomy with examples:
- Category definitions and characteristics
- Famous examples in each category
- Common patterns and anti-patterns
- Implementation considerations

### references/transfer-templates.md
Ready-to-use templates for style documentation:
- Design token formats (CSS, JSON, YAML)
- Style guide structures
- Component specification templates
- Code implementation examples

### references/examples.md
Real-world style extraction case studies:
- Complete extraction walkthroughs
- Before/after comparisons
- Common pitfalls and solutions
- Transfer success stories

## Usage Example

**User:** "Here's a screenshot of Linear's interface. I want to replicate this style for my project management tool."

**Workflow:**
1. **Analyze** the screenshot (Phase 1)
   - Extract color palette (purple/gray theme)
   - Identify typography (Inter font, tight spacing)
   - Map spacing system (consistent 4px base)

2. **Categorize** the style (Phase 2)
   - Style category: Modern Minimalist + Developer-focused
   - Key characteristics: High contrast, dense information, keyboard-first

3. **Document** for transfer (Phase 3)
   - Generate CSS custom properties
   - Create component specifications
   - Provide implementation examples

**Output:** Complete style guide with design tokens, visual examples, and implementation code ready for your project.

## Tips for Best Results

### For Screenshots:
- Use high-resolution images (at least 1920px wide)
- Capture multiple screens if available (homepage, dashboard, forms)
- Include interactive states if possible (hover, active, error states)

### For Web URLs:
- Provide the most representative page
- Mention specific components to focus on
- Note any dynamic behaviors you want to capture

### For Style Transfer:
- Specify your target framework (React, Vue, plain HTML/CSS)
- Mention any constraints (accessibility requirements, brand colors to preserve)
- Indicate depth of extraction needed (surface, system, or principle level)

---

Remember: Great style cloning isn't about pixel-perfect copying - it's about understanding the systematic design decisions that create a cohesive visual language, then adapting those principles to your own context.
