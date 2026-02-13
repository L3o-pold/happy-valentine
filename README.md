# Valentine's Day CAPTCHA

A fun, fake Google reCAPTCHA that reveals a Valentine's Day surprise when completed.

## What is this?

This is a playful static website that mimics Google's reCAPTCHA verification system. When someone clicks the checkbox, they're presented with a 3x3 image grid challenge. To "pass" the CAPTCHA, they must select all 9 photos. Upon successful verification, a cute Valentine's Day landing page appears!

## Features

- **Authentic-looking reCAPTCHA widget** with smooth animations
- **Interactive image grid** - users must select all 9 photos
- **Morphing checkbox** - transforms from square to spinning circle loader
- **Particle effects** on successful verification
- **Beautiful Valentine's Day landing page** with floating hearts and animations
- **Error handling** - shows error if not all images are selected

## How to Use

1. Open `index.html` in a browser
2. Click the "I'm not a robot" checkbox
3. Select all 9 photos in the grid
4. Click "Verify"
5. Enjoy the Valentine's Day surprise!

## Customization

### Adding Your Own Photos

Replace the placeholder SVGs in the JavaScript with your actual images:

```javascript
// In the JavaScript section, replace this:
cell.innerHTML = `
    <svg viewBox="0 0 100 100" style="background: ${color};">
        <text x="50" y="55" text-anchor="middle" fill="white" font-size="20" font-weight="bold">Photo ${index + 1}</text>
    </svg>
`;

// With this:
cell.innerHTML = `<img src="your-photo-${index + 1}.jpg" alt="Photo">`;
```

### Changing the Message

Edit the Valentine's Day message in the HTML:

```html
<div class="valentine-message">
    Your custom message here...
</div>
```

## Deployment

This site is automatically deployed to GitHub Pages via GitHub Actions. See `.github/workflows/deploy.yml`.

To deploy manually, simply host the `index.html` file on any static web server.

## Technologies

- HTML5
- CSS3 (animations, transitions, flexbox, grid)
- Vanilla JavaScript (no dependencies)

## License

Feel free to use this for your own Valentine's Day surprises! 💕
