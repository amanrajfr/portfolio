# Aman Raj - Portfolio Website

A modern, responsive portfolio website showcasing projects and skills.

## 🚀 Live Demo

Visit: [amanraj.online](https://amanraj.online)

## ✨ Features

- **Modern Design**: Sleek dark theme with gradient accents
- **Fully Responsive**: Works perfectly on all devices
- **Smooth Animations**: Engaging user experience with scroll animations
- **Project Showcase**: Links to live projects via subdomains
- **Fast Loading**: Optimized for performance
- **SEO Friendly**: Proper meta tags and semantic HTML

## 🛠️ Built With

- HTML5
- CSS3 (Modern features: Grid, Flexbox, CSS Variables)
- Vanilla JavaScript
- Font Awesome Icons
- Google Fonts (Inter)

## 📂 Project Structure

```
portfolio/
├── index.html      # Main HTML file
├── styles.css      # Stylesheet
├── script.js       # JavaScript for interactivity
└── README.md       # This file
```

## 🚀 Deployment

### Cloudflare Pages

1. Push code to GitHub
2. Go to [Cloudflare Dashboard](https://dash.cloudflare.com)
3. Navigate to Pages
4. Click "Create a project"
5. Connect to GitHub repository
6. Configure:
   - Build command: (leave empty)
   - Build output directory: `/portfolio`
7. Deploy!

### Custom Domain Setup

1. In Cloudflare Pages, go to Custom domains
2. Add `amanraj.online`
3. Cloudflare will automatically configure DNS

## 📝 Customization

### Update Content

Edit `index.html` to update:
- Personal information
- Project details
- Social media links
- Contact information

### Change Colors

Modify CSS variables in `styles.css`:

```css
:root {
    --primary-color: #6366f1;    /* Main brand color */
    --secondary-color: #8b5cf6;  /* Accent color */
    --dark-bg: #0f172a;          /* Background */
}
```

### Add Projects

Add new project cards in the projects section of `index.html`:

```html
<div class="project-card">
    <div class="project-image">
        <i class="fas fa-icon-name"></i>
    </div>
    <div class="project-content">
        <h3 class="project-title">Project Name</h3>
        <p class="project-description">Description...</p>
        <div class="project-tags">
            <span class="tag">Tech 1</span>
            <span class="tag">Tech 2</span>
        </div>
        <div class="project-links">
            <a href="url" class="project-link">
                <i class="fas fa-external-link-alt"></i> Live Demo
            </a>
        </div>
    </div>
</div>
```

## 📱 Responsive Breakpoints

- Desktop: > 968px
- Tablet: 640px - 968px
- Mobile: < 640px

## 🔗 Subdomain Projects

- [medicheck.amanraj.online](https://medicheck.amanraj.online) - Medical platform
- [ragchat.amanraj.online](https://ragchat.amanraj.online) - RAG PDF Chat (deploying soon)

## 📄 License

MIT License - feel free to use this template for your own portfolio!

## 🤝 Contributing

This is a personal portfolio, but suggestions are welcome!

## 📧 Contact

- Email: contact@amanraj.online
- GitHub: [@amanrajfr](https://github.com/amanrajfr)
- LinkedIn: [Aman Raj](https://linkedin.com/in/amanrajfr)

---

Made with ❤️ by Aman Raj
