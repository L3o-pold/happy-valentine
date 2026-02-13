# AGENTS.md

## Project Overview

This is a Valentine's Day themed fake CAPTCHA website. It's a single-page static HTML file with embedded CSS and JavaScript.

## Project Structure

```
.
├── index.html          # Main file - contains HTML, CSS, and JavaScript
├── .github/
│   └── workflows/
│       └── deploy.yml  # GitHub Actions workflow for GitHub Pages
├── images/             # Directory for photos (currently empty)
├── README.md           # Project documentation
└── AGENTS.md           # This file
```

## Key Components

### HTML Structure
- `captcha-widget`: The main reCAPTCHA-like checkbox
- `modal-overlay`: The image selection modal
- `image-grid`: 3x3 grid of selectable photos
- `valentine-page`: The final Valentine's Day landing page
- `error-message`: Popup for incomplete selections

### CSS Classes
- `.checkbox`: The CAPTCHA checkbox (morphs square → circle → checkmark)
- `.checkbox.spinning`: Circle loader state with rotation animation
- `.checkbox.checked`: Green checkmark state
- `.image-cell`: Grid photo cells with selection states
- `.valentine-page`: Full-screen Valentine's landing

### JavaScript Functions
- `createParticles()`: Creates explosion effect on verification
- `createFloatingHearts()`: Generates floating heart animations
- `resetSelection()`: Clears all selections when modal closes

## Development Guidelines

### Making Changes

1. **Styling**: All CSS is in the `<style>` tag in `index.html`
2. **Logic**: All JavaScript is in the `<script>` tag at the bottom of `index.html`
3. **Photos**: Add images to the `images/` folder and update the JavaScript to reference them

### Animation Timing

- Checkbox morph: 100ms (fast transition)
- Spinner rotation: 600ms per cycle
- Modal open: 300ms with bounce easing
- Success page: 800ms delay after verification

### Color Scheme

- Primary blue: `#4285f4` (Google blue)
- Success green: `#4caf50`
- Valentine's gradient: `#ffecd2` → `#fcb69f` → `#ff9a9e`
- Heart color: `#e91e63`

## Common Tasks

### Adding Real Photos

Replace the placeholder color blocks in the JavaScript:

```javascript
// Find this section and update:
placeholderColors.forEach((color, index) => {
    const cell = document.createElement('div');
    cell.className = 'image-cell';
    // Replace the SVG with an img tag
    cell.innerHTML = `<img src="images/photo${index + 1}.jpg" alt="Photo ${index + 1}">`;
    // ... rest of the code
});
```

### Modifying the Valentine's Message

Look for the `.valentine-message` div in the HTML and edit the poem/text.

### Changing Required Selections

Currently requires all 9 photos. To change this, modify the check in the verify button handler:

```javascript
if (selectedCount !== totalImages) {
    // Change totalImages or use a different condition
}
```

## Testing

1. Open `index.html` in a browser
2. Test the checkbox morphing animation
3. Verify the modal opens
4. Test selecting/deselecting photos
5. Try clicking verify without all photos selected (should show error)
6. Select all photos and verify (should show Valentine's page)
7. Close modal and reopen (should reset selections)

## Deployment

The site auto-deploys to GitHub Pages when pushing to `main` or `master`. No build step required.

## Notes

- This is a **fake** CAPTCHA for entertainment purposes only
- No actual verification or security is performed
- All animations are CSS-based for performance
- Mobile-responsive design included
