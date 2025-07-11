# Hostinger Deployment Guide - UPDATED

## 🚀 Complete Steps to Deploy on Hostinger:

### 1. Build the Project
```bash
npm run build:hostinger
```
This command builds the project and copies the .htaccess file to the dist folder.

### 2. Upload Files to Hostinger
1. **Go to your Hostinger control panel**
2. **Open File Manager**
3. **Navigate to public_html folder**
4. **Delete any existing files** (if this is a fresh install)
5. **Upload ALL contents** from the `dist` folder to `public_html`

### 3. Required File Structure on Hostinger:
```
public_html/
├── index.html
├── .htaccess
├── vite.svg
└── assets/
    ├── [name].js
    ├── [name].css
    └── [other assets]
```

### 4. ⚠️ CRITICAL STEPS for Hostinger:

#### A. Check .htaccess File
- Make sure `.htaccess` is uploaded to the root of `public_html`
- If you can't see it, enable "Show Hidden Files" in File Manager
- The .htaccess file handles routing and prevents 404 errors

#### B. File Permissions
- Set folder permissions to 755
- Set file permissions to 644
- This can be done in File Manager → Right-click → Permissions

#### C. PHP Version (if applicable)
- Go to Hostinger control panel
- Set PHP version to 8.0 or higher (if your plan supports it)

### 5. 🔧 Troubleshooting Common Issues:

#### Issue: "This site can't be reached" or blank page
**Solution:**
1. Check if all files are uploaded correctly
2. Verify .htaccess file is present
3. Clear browser cache
4. Wait 5-10 minutes for DNS propagation

#### Issue: CSS/JS not loading
**Solution:**
1. Check file paths in index.html
2. Ensure assets folder is uploaded
3. Check file permissions (644 for files, 755 for folders)

#### Issue: 404 errors on navigation
**Solution:**
1. Verify .htaccess file is in the root directory
2. Check if mod_rewrite is enabled (contact Hostinger support if needed)

#### Issue: Fonts not loading
**Solution:**
1. The fonts are loaded from Google Fonts CDN
2. Check internet connection
3. Fallback fonts are included

### 6. 📋 Pre-Upload Checklist:
- [ ] Run `npm run build:hostinger`
- [ ] Check dist folder contains index.html
- [ ] Check dist folder contains .htaccess
- [ ] Check dist folder contains assets folder
- [ ] Clear public_html folder (if fresh install)
- [ ] Upload all files from dist to public_html
- [ ] Set correct file permissions
- [ ] Test the website

### 7. 🎯 After Upload Testing:
1. **Visit your domain**
2. **Test navigation** (Home, About, Services, etc.)
3. **Test Admin panel** (click Admin button)
4. **Test responsive design** (mobile/tablet view)
5. **Check browser console** for any errors

### 8. 📞 If Still Not Working:
1. **Contact Hostinger Support** and mention:
   - "Need mod_rewrite enabled for React SPA"
   - "Having issues with .htaccess file"
   - "Single Page Application routing not working"

2. **Alternative Solution** (if .htaccess doesn't work):
   - Ask Hostinger to enable "Apache mod_rewrite"
   - Or use their "Single Page Application" hosting option

### 9. 🔄 Updating Content:
- Use the Admin panel on your live site
- Changes are saved locally in browser
- For major updates, rebuild and re-upload

---

## 📝 Quick Upload Steps:
1. `npm run build:hostinger`
2. Go to Hostinger File Manager
3. Clear public_html folder
4. Upload everything from dist folder
5. Set permissions (755 for folders, 644 for files)
6. Visit your domain

Your website should now work perfectly on Hostinger! 🎉