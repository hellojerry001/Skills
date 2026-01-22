---
name: app-builder
description: A systematic workflow for building high-quality applications from concept to completion. Guides you through requirement gathering, prompt enhancement, iterative development with Gemini, multi-stage optimization (UI, logo, animations, features), and generates comprehensive review documentation. Use when you want to build web applications, mobile apps, or tools following a structured, quality-focused development process.
---

# App Builder

A systematic, SOP-driven workflow for building high-quality applications with AI assistance.

## Overview

This skill provides a structured approach to application development, ensuring consistent quality through standardized processes. It guides you from initial concept through to final delivery, with built-in optimization stages and quality checkpoints.

## When to Use This Skill

**Perfect for:**
- Building web applications from scratch
- Creating interactive tools and utilities
- Developing landing pages or product sites
- Prototyping new product ideas
- Learning structured development workflows

**Not suitable for:**
- Simple text generation tasks
- Complex backend infrastructure (focus on frontend/UI)
- Projects requiring specialized frameworks (unless specified)

## Core Workflow: 7-Stage Development Process

### Stage 1: Requirement Gathering
**Goal:** Clearly define what you want to build

**Process:**
1. Describe your application idea
2. Identify target users
3. List core features (must-have vs nice-to-have)
4. Define success criteria
5. Specify technical constraints

See detailed guide: [workflow-stages.md](references/workflow-stages.md#stage-1)

### Stage 2: Prompt Enhancement
**Goal:** Transform raw requirements into optimized prompts

**Process:**
1. Use the professional-prompt-writer patterns
2. Structure requirements into clear sections
3. Add technical specifications
4. Define output format expectations
5. Include quality criteria

**Key principle:** A well-crafted prompt = better first version

See templates: [prompt-templates.md](references/prompt-templates.md)

### Stage 3: Initial Generation (Gemini)
**Goal:** Get the first working version

**Process:**
1. Send enhanced prompt to Gemini
2. Receive generated code
3. Test functionality
4. Document initial observations
5. Identify improvement areas

**Important:** Don't expect perfection. This is iteration 1.

### Stage 4: UI/UX Optimization
**Goal:** Enhance visual design and user experience

**Focus areas:**
- Layout and spacing
- Color scheme and consistency
- Typography and readability
- Component design
- Responsive behavior

See patterns: [optimization-patterns.md](references/optimization-patterns.md#ui-ux)

### Stage 5: Logo & Branding
**Goal:** Add visual identity and polish

**Process:**
1. Design or integrate logo
2. Establish brand colors
3. Apply consistent styling
4. Add favicon and meta tags
5. Ensure brand cohesion

### Stage 6: Detail Refinement
**Goal:** Perfect the experience through micro-optimizations

**Focus areas:**
- Immersive design (fullscreen, focus modes)
- Smooth animations and transitions
- Micro-interactions
- Loading states
- Error handling
- Performance optimization
- New feature additions

See patterns: [optimization-patterns.md](references/optimization-patterns.md#details)

### Stage 7: Review & Documentation
**Goal:** Reflect, document, and learn

**Deliverables:**
1. Final codebase
2. Review document analyzing:
   - What went well
   - What could improve
   - Technical decisions
   - Lessons learned
   - Future enhancements

See template: [review-template.md](references/review-template.md)

## Workflow Diagram

```
┌─────────────────────────────────────────────────────────────┐
│  Stage 1: Requirement Gathering                             │
│  Input: User idea/needs                                     │
│  Output: Structured requirements doc                        │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│  Stage 2: Prompt Enhancement                                │
│  Tool: professional-prompt-writer skill                     │
│  Output: Optimized generation prompt                        │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│  Stage 3: Initial Generation                                │
│  Platform: Gemini                                           │
│  Output: Version 1.0 (working prototype)                    │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│  Stage 4: UI/UX Optimization                                │
│  Focus: Layout, colors, typography, components              │
│  Output: Version 2.0 (polished UI)                          │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│  Stage 5: Logo & Branding                                   │
│  Focus: Visual identity, brand consistency                  │
│  Output: Version 3.0 (branded)                              │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│  Stage 6: Detail Refinement                                 │
│  Focus: Animations, immersive design, features, polish      │
│  Output: Version 4.0 (production-ready)                     │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│  Stage 7: Review & Documentation                            │
│  Output: Review doc + lessons learned                       │
│  Final: Ready for deployment                                │
└─────────────────────────────────────────────────────────────┘
```

## Key Principles

### 1. Iterative Over Perfect

Don't aim for perfection in stage 3. Embrace iteration:
- V1 = Working functionality
- V2 = Good design
- V3 = Brand identity
- V4 = Polished experience

### 2. Structured Prompts Win

Time spent on stage 2 (prompt enhancement) pays off exponentially:
- Clear prompts → Better first version
- Specific requirements → Fewer revisions
- Quality criteria → Measurable success

### 3. Optimize in Layers

Don't try to fix everything at once:
- First: Make it work (Stage 3)
- Second: Make it look good (Stage 4)
- Third: Make it yours (Stage 5)
- Fourth: Make it amazing (Stage 6)

### 4. Document Everything

The review document (Stage 7) is not optional:
- Captures learning
- Improves future projects
- Builds institutional knowledge
- Helps team alignment

### 5. User-Centric Focus

Every stage should ask: "Does this serve the user?"
- Stage 1: Who are they?
- Stage 4: Can they use it easily?
- Stage 6: Is it delightful?

## Usage Example

**User Input:**
> "I want to build a Pomodoro timer app with a clean, minimalist design."

**Workflow:**

**Stage 1 - Requirements:**
```
App: Pomodoro Timer
Target Users: Students, remote workers, productivity enthusiasts
Core Features:
- 25-minute work timer
- 5-minute break timer
- Start/pause/reset controls
- Visual progress indicator
- Sound notification when complete
Technical: Single-page web app, HTML/CSS/JS, works offline
```

**Stage 2 - Enhanced Prompt:**
```
Create a Pomodoro timer web application with the following specifications:

Core Functionality:
- Work session: 25 minutes
- Short break: 5 minutes
- Large, centered circular timer display
- Controls: Start, Pause, Reset buttons
- Audio notification on completion

Design Requirements:
- Minimalist aesthetic inspired by apps like "Be Focused"
- Color scheme: Soft blues and whites
- Large, readable typography (Inter or SF Pro font)
- Circular progress indicator showing time remaining
- Smooth animations for transitions

Technical Requirements:
- Single HTML file with embedded CSS and JavaScript
- No external dependencies (no libraries/frameworks)
- Responsive design (mobile-first)
- Works offline (no API calls)
- Clean, commented code

User Experience:
- Immediate visual feedback on all interactions
- Clear indication of current state (work/break)
- Subtle sound for timer completion (can be toggled)
- Keyboard shortcuts (Space = start/pause, R = reset)

Output Format:
Complete, working HTML file ready to open in a browser
```

**Stage 3 - Generation:**
- Send to Gemini → Receive V1.0
- Test basic functionality
- Note: "Timer works but design is plain, colors are too bright"

**Stage 4 - UI Optimization:**
```
Optimization prompt:
"Refine the UI with these changes:
- Use softer colors: background #F7F9FC, primary #5B8DEF
- Add more spacing (padding: 3rem)
- Make timer display larger (font-size: 4rem)
- Round all buttons (border-radius: 50px)
- Add subtle shadows for depth"
```

**Stage 5 - Logo/Branding:**
```
"Add a simple logo at the top: A minimalist clock icon using only circles.
Color: Match primary blue. Make it 48px. Add app name 'Focus Time' in
Helvetica Neue, light weight below the logo."
```

**Stage 6 - Details:**
```
"Final polish:
- Add fade-in animation on page load
- Smooth progress ring animation (CSS transition)
- Add subtle pulse effect when timer is running
- Implement fullscreen mode (button in corner)
- Add dark mode toggle
- Save user preferences to localStorage"
```

**Stage 7 - Review:**
Generate review document capturing the journey, decisions, and learnings.

## Quality Checkpoints

After each stage, verify:

**Stage 1:**
- [ ] Requirements are specific, not vague
- [ ] Success criteria are measurable
- [ ] All stakeholders aligned

**Stage 2:**
- [ ] Prompt includes all requirements
- [ ] Technical specs are clear
- [ ] Output format is defined

**Stage 3:**
- [ ] Code runs without errors
- [ ] Core features work
- [ ] Ready for optimization

**Stage 4:**
- [ ] Visually appealing
- [ ] Consistent styling
- [ ] Responsive on all devices

**Stage 5:**
- [ ] Brand elements present
- [ ] Visual identity cohesive
- [ ] Professional appearance

**Stage 6:**
- [ ] Smooth interactions
- [ ] No visual glitches
- [ ] Performance is good
- [ ] All features polished

**Stage 7:**
- [ ] Review document complete
- [ ] Lessons documented
- [ ] Code is clean and commented

## Advanced Usage

### Skipping Stages

Not every project needs all stages:
- **Quick prototype:** Stages 1-3 only
- **Design focus:** Skip Stage 5 if no branding needed
- **Rapid iteration:** Combine Stages 4-6

### Parallel Optimization

For faster iteration:
- Optimize UI and branding simultaneously (Stages 4+5)
- Prepare multiple refinement prompts for Stage 6

### Custom Stages

Add stages for your needs:
- **Stage 4.5:** Accessibility audit
- **Stage 6.5:** User testing
- **Stage 7.5:** Deployment prep

## Common Pitfalls

### ❌ Pitfall 1: Vague Requirements
**Problem:** "Build me a nice app"
**Solution:** Use Stage 1 checklist, be specific

### ❌ Pitfall 2: Skipping Prompt Enhancement
**Problem:** Sending raw ideas to Gemini
**Solution:** Always go through Stage 2

### ❌ Pitfall 3: Over-Optimizing Too Early
**Problem:** Tweaking animations before core features work
**Solution:** Follow stage order strictly

### ❌ Pitfall 4: No Review Document
**Problem:** No learning captured
**Solution:** Make Stage 7 non-negotiable

### ❌ Pitfall 5: Expecting Perfection in V1
**Problem:** Disappointed with initial output
**Solution:** Embrace iteration mindset

## Integration with Other Skills

This skill works well with:

**professional-prompt-writer** (Stage 2)
- Use for crafting better generation prompts
- Reference their patterns for structure

**style-cloning** (Stage 4-5)
- Extract styles from reference sites
- Apply to your app for professional look

**Custom skills:**
- Insert domain-specific skills at any stage
- Example: "accessibility-checker" after Stage 4

## Resources

### [workflow-stages.md](references/workflow-stages.md)
Detailed breakdown of each stage with:
- Step-by-step instructions
- Decision trees
- Time estimates
- Common issues

### [prompt-templates.md](references/prompt-templates.md)
Ready-to-use templates for:
- Initial generation prompts
- Optimization prompts
- Refinement prompts
- Review prompts

### [optimization-patterns.md](references/optimization-patterns.md)
Proven patterns for:
- UI/UX improvements
- Performance optimization
- Animation techniques
- Feature additions

### [review-template.md](references/review-template.md)
Structured template for:
- Project retrospective
- Technical documentation
- Lessons learned
- Future roadmap

### [examples.md](references/examples.md)
Complete case studies:
- Pomodoro timer
- Weather dashboard
- Portfolio site
- Task manager

## Success Metrics

A successful app-builder session produces:

**Functional:**
- ✅ App works without errors
- ✅ All core features implemented
- ✅ Responsive and accessible

**Visual:**
- ✅ Professional appearance
- ✅ Consistent design language
- ✅ Smooth interactions

**Process:**
- ✅ Clear documentation
- ✅ Review document complete
- ✅ Learnings captured

**User-Centric:**
- ✅ Solves user problem
- ✅ Intuitive to use
- ✅ Delightful experience

---

**Remember:** Great apps aren't built in one step. They're refined through structured iteration. This workflow ensures you don't miss critical steps while maintaining creative freedom within each stage.

Ready to build something amazing? Start with Stage 1: What do you want to create?
