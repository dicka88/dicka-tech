# Cloudflare Pages Deployment Guide

## 🚀 Cara Deploy ke Cloudflare Pages

### Metode 1: Via Cloudflare Dashboard (Recommended)

1. **Push code ke GitHub/GitLab/Bitbucket**
   ```bash
   git add .
   git commit -m "Prepare for Cloudflare deployment"
   git push origin main
   ```

2. **Login ke Cloudflare Dashboard**
   - Buka https://dash.cloudflare.com
   - Login dengan akun Cloudflare Anda

3. **Buat Project Baru**
   - Klik **"Workers & Pages"** di sidebar
   - Klik **"Create application"**
   - Pilih **"Pages"** tab
   - Klik **"Connect to Git"**

4. **Connect Repository**
   - Pilih Git provider (GitHub/GitLab/Bitbucket)
   - Authorize Cloudflare
   - Pilih repository `agency-website`
   - Klik **"Begin setup"**

5. **Configure Build Settings**
   - **Project name**: `dicka-tech` (atau sesuai keinginan)
   - **Production branch**: `main` (atau `master`)
   - **Framework preset**: `Astro`
   - **Build command**: `yarn build`
   - **Build output directory**: `dist`
   - **Root directory**: `/` (leave empty)

6. **Environment Variables** (Optional)
   - Jika ada environment variables, tambahkan di bagian **"Environment variables"**
   - Untuk development: `NODE_VERSION=20`

7. **Deploy**
   - Klik **"Save and Deploy"**
   - Cloudflare akan mulai build dan deploy website Anda

8. **Custom Domain** (Optional)
   - Setelah deploy selesai, klik project
   - Pergi ke **"Custom domains"**
   - Klik **"Set up a custom domain"**
   - Masukkan domain: `dickatech.com` (atau sesuai domain Anda)
   - Ikuti instruksi untuk setup DNS

### Metode 2: Via Wrangler CLI

1. **Install Wrangler CLI**
   ```bash
   npm install -g wrangler
   # atau
   yarn global add wrangler
   ```

2. **Login ke Cloudflare**
   ```bash
   wrangler login
   ```

3. **Deploy**
   ```bash
   yarn build
   wrangler pages deploy dist
   ```

### Metode 3: Via GitHub Actions (CI/CD)

1. **Buat file `.github/workflows/deploy.yml`**
   ```yaml
   name: Deploy to Cloudflare Pages
   
   on:
     push:
       branches:
         - main
   
   jobs:
     deploy:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v3
         - uses: actions/setup-node@v3
           with:
             node-version: '20'
         - run: yarn install
         - run: yarn build
         - uses: cloudflare/pages-action@v1
           with:
             apiToken: ${{ secrets.CLOUDFLARE_API_TOKEN }}
             accountId: ${{ secrets.CLOUDFLARE_ACCOUNT_ID }}
             projectName: dicka-tech
             directory: dist
   ```

2. **Setup Secrets di GitHub**
   - Go to repository Settings → Secrets and variables → Actions
   - Add `CLOUDFLARE_API_TOKEN`
   - Add `CLOUDFLARE_ACCOUNT_ID`

## 📋 Build Configuration

- **Build Command**: `yarn build`
- **Output Directory**: `dist`
- **Node Version**: 20 (configured in `.nvmrc`)

## 🔧 Post-Deployment

1. **Update `astro.config.mjs` site URL**
   - Pastikan `site: 'https://dickatech.com'` sesuai dengan domain Anda
   - Atau gunakan domain Cloudflare Pages: `https://your-project.pages.dev`

2. **Verify Deployment**
   - Check sitemap: `https://your-domain.com/sitemap-index.xml`
   - Check robots.txt: `https://your-domain.com/robots.txt`
   - Test all pages functionality

3. **SSL/TLS**
   - Cloudflare Pages automatically provides SSL certificate
   - Make sure SSL/TLS mode is set to "Full" or "Full (strict)"

## 🐛 Troubleshooting

### Build Fails
- Check Node version (should be 20)
- Verify all dependencies are in `package.json`
- Check build logs in Cloudflare Dashboard

### 404 Errors
- Verify `output: 'static'` in `astro.config.mjs`
- Check that all routes are properly configured

### Assets Not Loading
- Check `_headers` file in `public/` directory
- Verify CORS settings if needed

## 📚 Resources

- [Cloudflare Pages Docs](https://developers.cloudflare.com/pages/)
- [Astro Deployment Guide](https://docs.astro.build/en/guides/deploy/cloudflare/)
- [Cloudflare Pages Pricing](https://developers.cloudflare.com/pages/platform/pricing/)

