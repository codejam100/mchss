# Mother Convent Higher Secondary School - Web Deployment Guide

## Website Structure

This checkout folder contains a complete, production-ready website for Mother Convent Higher Secondary School.

### Folder Structure
```
checkout/
├── index.html          # Splash screen (entry point)
├── gallery.html        # Photo gallery page
├── css/
│   └── main.css        # Website stylesheets
└── images/
    ├── logo.png        # School logo
    └── new_gallery/    # Album of 33 school photos
        ├── Image_0.jpeg through Image_30.jpeg
        └── splash.jpeg
```

## Files Included

| File | Purpose |
|------|---------|
| **index.html** | Beautiful splash screen landing page with auto-redirect to gallery (5 seconds) |
| **gallery.html** | Interactive photo gallery with zoom feature |
| **css/main.css** | Responsive stylesheets for gallery layout |
| **images/logo.png** | School logo (used in splash screen) |
| **images/new_gallery/** | 33 high-quality school photographs |

## Features

### Splash Screen (index.html)
- Full-screen background image (splash.jpeg)
- Animated school logo and name
- Auto-redirect to gallery after 5 seconds
- Skip options: Click button, spacebar, or Enter key
- Countdown timer display
- Responsive design (desktop, tablet, mobile)

### Photo Gallery (gallery.html)
- Responsive grid layout (adapts to screen size)
- Thumbnail preview of all photos
- Click-to-zoom modal viewer
- Image navigation with arrow buttons (< >)
- Keyboard navigation (← → Arrow keys, ESC to close)
- Image counter showing position (e.g., "5 / 33")
- School information header and footer

## Deployment Instructions

### Option 1: Upload to Web Hosting (Recommended)

1. **Connect to your web server** via FTP/SFTP or file manager
2. **Upload the contents** of this checkout folder to your public_html or www directory
3. **Ensure file permissions**: 
   - HTML files: 644
   - Image folders: 755
   - Image files: 644

### Option 2: Local Web Server Testing

#### Using Python (Quick Test)
```bash
# Python 3.x
python -m http.server 8000

# Then open browser: http://localhost:8000
```

#### Using Node.js
```bash
npx http-server
```

#### Using PHP
```bash
php -S localhost:8000
```

## Browser Compatibility

✓ Chrome/Chromium (Latest)
✓ Firefox (Latest)
✓ Safari (Latest)
✓ Edge (Latest)
✓ Mobile browsers (iOS Safari, Chrome Mobile)

## Performance Notes

- All images are optimized JPEG format
- CSS is inline in HTML files for faster loading
- No external dependencies or CDN requirements
- Website works offline after first load

## SEO & Meta Tags

The website includes:
- Proper page title: "Mother Convent Higher Secondary School"
- Meta viewport for responsive design
- Hindi and English content
- School location information in footer

## Customization

To modify content, edit the HTML files directly:

### Change splash screen text (index.html)
Look for the `.text-section` in the HTML and update:
- School name
- Hindi subtitle
- Time before auto-redirect (change `countdown = 5` to desired seconds)

### Add or remove gallery images (gallery.html)
Add new image references in the `.gallery-container` div:
```html
<div class="gallery-item" data-src="images/new_gallery/ImageName.jpeg" onclick="openModal(this)">
    <img src="images/new_gallery/ImageName.jpeg" alt="Description">
</div>
```

### Change colors or styles
Edit the `<style>` section in either HTML file.

## File Sizes (Approximate)

- index.html: ~10 KB
- gallery.html: ~35 KB
- css/main.css: ~5 KB
- logo.png: ~150 KB
- Each gallery image: 500 KB - 2 MB
- **Total folder size: ~40-60 MB** (depends on image compression)

## Support

For any issues:
1. Check browser console (F12) for JavaScript errors
2. Verify all image files uploaded correctly
3. Clear browser cache and reload
4. Test on different browsers
5. Ensure file paths are correct on your server

## License & Copyright

© 2026 Mother Convent Higher Secondary School
( जानकी मेमोरियल ऐजुकेशन सोसायटी द्वारा संचालित )

---

**Ready to upload! All files are production-ready and optimized for web servers.**
