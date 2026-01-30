# Ali Beddiaf - Personal Academic Website

A clean, professional academic webpage featuring publications, research interests, and contact information.

## Features

- **Responsive Design**: Works beautifully on all devices (desktop, tablet, mobile)
- **Smooth Animations**: Elegant scroll animations and transitions
- **Clean Typography**: Uses Crimson Pro (serif) and Fira Sans (sans-serif) for a refined academic look
- **Easy to Update**: Simple HTML structure for quick content updates
- **Modern CSS**: Uses CSS Grid, Flexbox, and custom properties for maintainable styling

## Setup on GitHub Pages

1. **Create a new repository** on GitHub named `yourusername.github.io` (replace with your actual GitHub username)

2. **Upload these files** to your repository:
   - `index.html`
   - `style.css`
   - `script.js`
   - `README.md`

3. **Enable GitHub Pages**:
   - Go to your repository Settings
   - Scroll to "Pages" section
   - Under "Source", select "main" branch
   - Click Save

4. Your website will be live at `https://yourusername.github.io`

## Customization Guide

### Adding Your Photo

Replace the placeholder div in `index.html` (around line 60):

```html
<!-- Current placeholder -->
<div class="image-placeholder">
    <div class="placeholder-text">Photo</div>
</div>

<!-- Replace with your photo -->
<img src="images/photo.jpg" alt="Ali Beddiaf" style="width: 300px; height: 300px; object-fit: cover; border: 3px solid var(--accent-color);">
```

Create an `images` folder in your repository and upload your photo there.

### Updating Contact Information

Edit the contact section in `index.html` (around line 235):
- Change email address
- Update institutional address
- Add phone number if desired

### Updating Social Links

Edit the social links in `index.html` (around line 40):
- Change GitHub username: `https://github.com/YOUR_USERNAME`
- Change LinkedIn URL: `https://linkedin.com/in/YOUR_PROFILE`
- Add more social links by duplicating the structure

### Adding More Publications

Copy a publication item block and paste it in the appropriate category. Example:

```html
<article class="publication-item">
    <div class="pub-thumbnail">
        <div class="pub-icon">C</div> <!-- J for Journal, C for Conference, N for National -->
    </div>
    <div class="pub-content">
        <h4 class="pub-title">Your Paper Title</h4>
        <p class="pub-authors"><strong>A. Beddiaf</strong>, Co-Authors</p>
        <p class="pub-venue"><em>Conference Name</em>, Location, Year</p>
        <span class="pub-citations">Citations: X</span> <!-- Optional -->
    </div>
</article>
```

### Changing Colors

Edit CSS variables in `style.css` (around line 1):

```css
:root {
    --primary-color: #1a1a2e;        /* Main dark color */
    --accent-color: #c7956d;         /* Gold/brown accent */
    --secondary-accent: #8b7355;     /* Secondary brown */
    --text-color: #2d2d2d;           /* Main text */
    --bg-color: #fdfbf7;             /* Background cream */
}
```

### Adding a CV Download Link

Add this button in the hero section after the social links:

```html
<a href="cv.pdf" class="social-link" download>
    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
        <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
        <polyline points="7 10 12 15 17 10"></polyline>
        <line x1="12" y1="15" x2="12" y2="3"></line>
    </svg>
    Download CV
</a>
```

Upload your CV as `cv.pdf` to the repository.

## File Structure

```
yourusername.github.io/
├── index.html          # Main HTML file
├── style.css           # All styling
├── script.js           # JavaScript interactions
├── README.md           # This file
└── images/             # (optional) Folder for images
    └── photo.jpg       # Your profile photo
```

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Credits

Template design inspired by academic portfolio layouts.
Fonts: Google Fonts (Crimson Pro, Fira Sans)

## License

Feel free to use this template for your own academic website!

---

**Note**: Remember to update your GitHub repository URL in the social links and add your actual photo to complete the personalization.
