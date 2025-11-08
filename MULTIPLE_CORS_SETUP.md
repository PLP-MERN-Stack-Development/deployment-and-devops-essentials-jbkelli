# 🌐 Multiple CORS Origins Setup

## ✅ CORS Configuration Updated!

Your backend now supports **multiple frontend URLs** for CORS.

---

## 📝 How to Set Multiple Origins

### On Render Dashboard:

**Environment Variable Format:**
```
CLIENT_URL=url1,url2,url3
```

**Example:**
```
CLIENT_URL=https://task-manager-8dze75jf5-akim-mainas-projects.vercel.app,http://localhost:3000,https://task-manager.vercel.app
```

⚠️ **Important:**
- **Separate URLs with commas**
- **NO spaces after commas**
- **Each URL must be complete** (include https://)
- **NO trailing slashes**

---

## 🎯 Common Configurations

### For Development + Production:
```
CLIENT_URL=http://localhost:3000,https://your-app.vercel.app
```

### For Multiple Vercel Deployments:
```
CLIENT_URL=https://your-app-main.vercel.app,https://your-app-preview.vercel.app,http://localhost:3000
```

### For Your Current Setup:
```
CLIENT_URL=https://task-manager-8dze75jf5-akim-mainas-projects.vercel.app,http://localhost:3000
```

---

## 🔧 How It Works

The updated code in `server.js`:
1. Splits the `CLIENT_URL` by commas
2. Trims whitespace from each URL
3. Checks if the requesting origin is in the allowed list
4. Allows the request if it matches

**Code snippet:**
```javascript
const allowedOrigins = process.env.CLIENT_URL 
  ? process.env.CLIENT_URL.split(',').map(url => url.trim())
  : ['http://localhost:3000'];
```

---

## ✅ Benefits

- ✅ **Development:** Test locally (localhost:3000)
- ✅ **Staging:** Preview deployments on Vercel
- ✅ **Production:** Main Vercel deployment
- ✅ **Flexibility:** Add/remove URLs anytime
- ✅ **Security:** Only specified origins allowed

---

## 🚀 Next Steps

1. **Commit the changes:**
   ```bash
   git add server/server.js server/.env.example
   git commit -m "Add support for multiple CORS origins"
   git push origin main
   ```

2. **Wait for Render to auto-deploy** (2-3 minutes)

3. **Update CLIENT_URL on Render:**
   - Go to Render dashboard
   - Environment tab
   - Update CLIENT_URL with comma-separated URLs
   - Save changes

4. **Test from both origins:**
   - http://localhost:3000 ✅
   - https://task-manager-8dze75jf5-akim-mainas-projects.vercel.app ✅

---

## 📋 Example Render Configuration

**Name:** `CLIENT_URL`

**Value:**
```
https://task-manager-8dze75jf5-akim-mainas-projects.vercel.app,http://localhost:3000
```

This will allow CORS from:
- Your deployed Vercel app
- Your local development environment

---

## 🐛 Troubleshooting

### Still getting CORS errors?

**Check:**
1. URLs are comma-separated (no spaces)
2. Each URL includes protocol (https:// or http://)
3. No trailing slashes
4. Render has redeployed
5. Browser cache cleared (Ctrl+Shift+R)

### Need to add a new origin?

1. Go to Render → Environment
2. Edit CLIENT_URL
3. Add new URL with comma: `,https://new-url.com`
4. Save and wait for redeploy

---

## ✨ Your Setup Is Ready!

**Current Configuration:**
- ✅ Multiple origins supported
- ✅ Localhost for development
- ✅ Vercel for production
- ✅ Easy to add more origins

**Commit and push the changes to deploy!** 🚀
