# Website Deployment Checklist

## Pre-Upload Checklist

- [ ] All images are properly placed in `images/new_gallery/` folder
- [ ] Logo file exists at `images/logo.png`
- [ ] Both `index.html` and `gallery.html` are present
- [ ] `css/main.css` stylesheet is included
- [ ] Test the site locally first using a local web server

## Local Testing (Before Upload)

**Using Python:**
```bash
cd checkout
python -m http.server 8000
# Visit: http://localhost:8000
```

**Test on:**
- [ ] Desktop browsers (Chrome, Firefox, Safari, Edge)
- [ ] Mobile device or mobile browser emulator
- [ ] Test splash screen auto-redirect (5 seconds)
- [ ] Test gallery image loading and zoom feature
- [ ] Test keyboard navigation (arrow keys, ESC)

## Server Upload Steps

1. **Connect to Web Host**
   - [ ] Use FTP/SFTP client (FileZilla, WinSCP, etc.)
   - [ ] Connect with server credentials
   - [ ] Navigate to public_html or www folder

2. **Upload Files**
   - [ ] Upload entire `checkout` folder contents
   - [ ] OR upload to subdirectory (e.g., `school-gallery/`)
   - [ ] Ensure all files preserve structure

3. **Set Permissions** (via terminal or host cPanel)
   ```bash
   # Directory permissions
   chmod 755 .
   chmod 755 images/
   chmod 755 images/new_gallery/
   chmod 755 css/
   
   # File permissions
   chmod 644 *.html
   chmod 644 *.txt
   chmod 644 .htaccess
   chmod 644 css/*.css
   chmod 644 images/*.png
   chmod 644 images/new_gallery/*.jpeg
   ```

4. **Verify Upload**
   - [ ] Visit your domain/website URL
   - [ ] Splash screen loads properly
   - [ ] Auto-redirect works (5 seconds)
   - [ ] Gallery page loads all images
   - [ ] Zoom feature works on hover and click
   - [ ] Mobile version looks correct

## Post-Upload Configuration

### If Using cPanel:
1. [ ] File Manager → Upload files
2. [ ] Set proper permissions
3. [ ] Test website functionality

### If Using SSH/Terminal:
```bash
# Navigate to web root
cd public_html

# Upload files (via SCP or FTP)
scp -r checkout/* user@server:/public_html/

# Set permissions
chmod -R 755 .
find . -type f -exec chmod 644 {} \;
find . -type d -exec chmod 755 {} \;
```

### Domain Setup:
- [ ] Point domain to correct server
- [ ] Wait for DNS propagation (24-48 hours)
- [ ] Test with domain name
- [ ] Verify SSL certificate (if using HTTPS)

## Optional Enhancements

- [ ] Set up HTTPS/SSL certificate
- [ ] Enable GZIP compression (via .htaccess)
- [ ] Configure browser caching
- [ ] Set up email for inquiries
- [ ] Add Google Analytics
- [ ] Create XML sitemap
- [ ] Submit to search engines (Google, Bing)

## Troubleshooting

**Issue: Images not loading**
- [ ] Check file paths are correct
- [ ] Verify image files uploaded successfully
- [ ] Check file permissions (should be 644)
- [ ] Check browser console for error messages

**Issue: Styles not applied**
- [ ] Verify css/main.css uploaded
- [ ] Hard refresh browser (Ctrl+F5 or Cmd+Shift+R)
- [ ] Check file permissions for CSS file

**Issue: Gallery zoom not working**
- [ ] Check JavaScript console for errors
- [ ] Ensure gallery.html uploaded correctly
- [ ] Try different browser

**Issue: Splash screen not redirecting**
- [ ] Check gallery.html exists and is uploadable
- [ ] Verify link in index.html points to gallery.html
- [ ] Check browser console for errors

## Support Resources

- **FTP Clients**: FileZilla, WinSCP, Transmit
- **DNS Checker**: whatsmydns.net
- **Performance Test**: PageSpeed Insights, GTmetrix
- **SSL Checker**: sslchecker.com

## Important Notes

⚠️ **Backup**: Always keep a backup of the original files
⚠️ **Updates**: If updating images, clear browser cache after upload
⚠️ **Permissions**: Never set folder permissions to 777 (security risk)
⚠️ **Testing**: Always test locally before uploading to production

---

**Deployment Date:** _______________
**Server:** _______________
**Domain:** _______________
**Notes:** _______________________________________________________________
