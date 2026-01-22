# Skills Collection Website with Upload Feature

Create a modern Skills collection website with masonry layout that allows users to both browse and upload Claude Code skills.

## Core Requirements

### Upload Functionality (NEW)

**Upload Interface:**
- Prominent "Upload Skill" button in header/navigation
  - Position: Top-right corner, next to theme toggle
  - Style: Primary button with accent color (#3B82F6)
  - Icon: Upload icon (arrow-up or cloud-upload)
  - Text: "Upload Skill" or "+ Add Skill"

**Upload Modal/Page:**
- Trigger: Click "Upload Skill" button
- Layout: Modal overlay (preferred) or dedicated page
- Modal specs:
  - Max-width: 600px
  - Padding: 32px
  - Border-radius: 16px
  - Backdrop: rgba(0,0,0,0.6) with backdrop-blur

**Upload Form Components:**

1. File Upload Area:
   - Drag-and-drop zone (200px height minimum)
   - Visual states:
     - Default: Dashed border (2px), upload icon, "Drop .skill file here"
     - Hover: Border color changes to accent, background subtle highlight
     - Dragging: Border solid, background accent with 0.1 opacity
     - Uploaded: Show file name, size, checkmark icon, "Change file" option
   - Click to browse alternative
   - File validation: Only accept .skill files (or .zip)
   - Max file size: 10MB (configurable)
   - Error handling: Show error message if invalid file type or size

2. Skill Metadata Form:
   - Auto-extract from .skill file if possible (read SKILL.md frontmatter)
   - Manual input fields:
     - Title (required): Text input, max 100 characters
     - Description (required): Textarea, 3-5 lines, max 300 characters
     - Tags (optional): Tag input with autocomplete
       - Allow adding new tags
       - Show existing tags as suggestions
       - Maximum 5 tags per skill
       - Tag format: lowercase, hyphens for spaces
     - Cover Image (optional):
       - Separate image upload (JPG, PNG, WebP)
       - Or URL input
       - Preview thumbnail (16:9 aspect ratio)
       - "Skip" option if no image

3. Form Actions:
   - "Cancel" button: Secondary style, closes modal
   - "Upload" button: Primary style, disabled until required fields filled
   - Loading state: Show spinner, disable form during upload
   - Success state: Show success message, auto-close after 2s, refresh grid

**Upload Flow:**
```
1. User clicks "Upload Skill"
2. Modal opens with empty form
3. User drags .skill file OR clicks to browse
4. File validates → Show success OR error
5. Form auto-fills from file metadata (if available)
6. User reviews/edits metadata
7. User adds optional cover image
8. User clicks "Upload"
9. Loading indicator shows
10. Success: Modal closes, new skill appears in grid with animation
11. Error: Show error message, allow retry
```

