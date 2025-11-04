# Dicka Tech - Modern Agency Website Landing Page

Website landing page profesional untuk agency jasa pembuatan website dengan desain modern, menggunakan Astro, Vue.js, dan TypeScript.

## ✨ Fitur Terbaru

- **Modern Hero Section**: Gambar tim dengan floating cards & statistics
- **Enhanced UI/UX**: Gradient backgrounds, glassmorphism, smooth animations
- **Process Workflow**: Visual timeline proses kerja
- **Tech Stack Showcase**: Display teknologi yang dikuasai dengan rating
- **Call-to-Action Section**: Section khusus untuk konversi
- **Lucide Icons**: Icon library modern di seluruh website
- **Landing Page**: Hero, stats, services, process, tech stack, portfolio, testimonials, CTA, contact
- **Blog Page**: Artikel dan tutorial dengan kategori
- **Responsive Design**: Tampilan optimal di semua ukuran layar
- **SEO Friendly**: Optimized untuk mesin pencari
- **Fast Performance**: Built dengan Astro untuk loading cepat

## 🛠️ Tech Stack

- **[Astro](https://astro.build)** - Static Site Generator
- **[Vue.js 3](https://vuejs.org)** - Progressive JavaScript Framework
- **[TypeScript](https://www.typescriptlang.org)** - Type Safety
- **[Tailwind CSS](https://tailwindcss.com)** - Utility-first CSS Framework
- **[Lucide Vue Next](https://lucide.dev)** - Beautiful & Consistent Icon Library

## 📦 Installation

1. Clone repository ini
```bash
git clone <repository-url>
cd agency-website
```

2. Install dependencies
```bash
yarn install
# atau
npm install
```

3. Jalankan development server
```bash
yarn dev
# atau
npm run dev
```

4. Buka browser di `http://localhost:4321`

## 🏗️ Build untuk Production

```bash
yarn build
# atau
npm run build
```

File production akan di-generate di folder `dist/`

## 🎬 Preview Production Build

```bash
yarn preview
# atau
npm run preview
```

## 📁 Struktur Project

```
agency-website/
├── public/              # Static assets
├── src/
│   ├── components/      # Vue.js & Astro components
│   │   ├── Header.vue          # Navigation bar
│   │   ├── Footer.astro        # Footer section
│   │   ├── Hero.vue            # Hero with team image
│   │   ├── Stats.vue           # Statistics cards
│   │   ├── Services.vue        # Services grid
│   │   ├── Process.vue         # 🆕 Workflow timeline
│   │   ├── TechStack.vue       # 🆕 Technology showcase
│   │   ├── Portfolio.vue       # Portfolio gallery
│   │   ├── Testimonials.vue    # Client testimonials
│   │   ├── CTA.vue             # 🆕 Call-to-action
│   │   ├── Contact.vue         # Contact form
│   │   └── BlogList.vue        # Blog listings
│   ├── content/         # Blog content (Markdown)
│   │   └── blog/
│   ├── layouts/         # Layout components
│   │   └── BaseLayout.astro
│   └── pages/           # Pages (routes)
│       ├── index.astro         # Landing page
│       ├── blog.astro          # Blog listing
│       └── blog/[slug].astro   # Blog detail
├── astro.config.mjs     # Astro configuration
├── tailwind.config.mjs  # Tailwind configuration
├── tsconfig.json        # TypeScript configuration
├── package.json
└── IMPROVEMENTS.md      # 📄 Detailed improvements log
```

## 🎨 Customization

### Warna
Edit `tailwind.config.mjs` untuk mengubah color palette:

```js
colors: {
  primary: {
    // Your custom colors
  }
}
```

### Konten
- Edit data di masing-masing component untuk mengubah konten
- Tambah/edit artikel blog di `src/pages/blog.astro`

## 📝 Layanan yang Ditampilkan

- Website Development
- SEO Optimization
- WordPress Development
- React Development
- Laravel Development
- Mobile App Development

## 🤝 Contributing

Contributions, issues, dan feature requests welcome!

## 📄 License

MIT License

## 🎨 Design Features

### Modern UI Elements
- ✨ Gradient backgrounds & text
- 🎭 Glassmorphism effects (backdrop-blur)
- 💫 Smooth animations & transitions
- 🎯 Floating elements with animations
- 📊 Interactive progress bars
- 🎪 Hover effects & micro-interactions
- 🖼️ High-quality images from Unsplash

### UX Enhancements
- Clear visual hierarchy
- Trust indicators (ratings, client count)
- Process workflow visualization
- Technology showcase with ratings
- Strategic CTAs placement
- Mobile-optimized views
- Smooth scrolling experience

## 📊 Performance

- Optimized bundle size with Astro
- Lazy loading with `client:visible`
- Efficient CSS with Tailwind
- Minimal JavaScript
- Fast Time to Interactive (TTI)

## 🔄 Recent Updates

See [IMPROVEMENTS.md](./IMPROVEMENTS.md) for detailed changelog of recent UI improvements.

## 👤 Author

**Dicka Tech Team**
- Website: https://dickatech.com
- Email: info@dickatech.com

---

Built with ❤️ using Astro + Vue.js + TypeScript + Lucide Icons

