# 🚀 Quick Reference: Full Stack Project 1

## 📱 Responsive Breakpoints

| Device | Width | Layout | Nav |
|--------|-------|--------|-----|
| **Mobile** | < 768px | Single column, stacked | Hamburger menu |
| **Tablet** | 768px - 1023px | 2-column grids | Horizontal nav |
| **Desktop** | 1024px+ | 3-column grids | Full nav bar |

## 🎨 Color Palette

```
🟤 Mocha Mousse   #A6856F  (Primary - Stability)
🔵 Ethereal Blue  #A0D4E0  (Secondary - Trust)
⚪ Moonlit Grey   #F2F0EA  (Background - Refinement)
⚫ Dark Text      #2B2B2B  (Foreground)
```

## 🔤 Typography

**Headlines:** Montserrat or Inter (Geometric)
**Body:** Roboto or Open Sans (Readable)

| Size | Mobile | Desktop |
|------|--------|---------|
| H1 | 2.5rem | 3.5rem |
| H2 | 2rem | 2.5rem |
| Body | 1rem | 1rem |

## 🧩 Page Sections

1. **Header/Nav** (Sticky, responsive)
2. **Hero** (Full-width, centered CTA)
3. **Features** (3-column card grid)
4. **Showcase** (2-column content + image)
5. **Testimonials** (2-4 column grid)
6. **CTA** (Call-to-action section)
7. **Footer** (3-column links)

## ⌨️ JavaScript Features

### Mobile Menu Toggle
```javascript
// Hamburger click handler
hamburger.addEventListener('click', () => {
  mobileMenu.classList.toggle('active');
});

// Escape key closes menu
document.addEventListener('keydown', (e) => {
  if (e.key === 'Escape') mobileMenu.classList.remove('active');
});
```

### Scroll Animations
```javascript
// Elements fade in as they appear
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('fade-in');
    }
  });
});
```

### Toast Notifications
```javascript
// Show success/action notifications
showNotification('Action completed!');
```

### Smooth Scroll Navigation
```javascript
// Clicking anchor links scrolls smoothly
a[href="#section"].scrollIntoView({ behavior: 'smooth' });
```

## ♿ Accessibility Highlights

- ✅ Semantic HTML5 (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`)
- ✅ ARIA labels (`aria-label`, `aria-expanded`, `aria-labelledby`)
- ✅ Keyboard navigation (Tab, Enter, Escape)
- ✅ Focus states (2px outline on all interactive elements)
- ✅ Screen reader support (skip links, landmarks)
- ✅ Color contrast (WCAG AA - 4.5:1 minimum)
- ✅ Touch targets (44px × 44px minimum)
- ✅ Reduced motion respected

## 🎯 Button Styles

### Primary Button
```css
.btn-primary {
  background-color: #A6856F;
  color: white;
  padding: 1.5rem 2rem;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 12px 32px rgba(0, 0, 0, 0.15);
}
```

### Secondary Button
```css
.btn-secondary {
  border: 2px solid #A6856F;
  color: #A6856F;
  background: transparent;
}

.btn-secondary:hover {
  background-color: #A6856F;
  color: white;
}
```

## 📐 Spacing System

```
xs: 0.25rem (4px)
sm: 0.5rem  (8px)
md: 1rem    (16px)
lg: 1.5rem  (24px)
xl: 2rem    (32px)
2xl: 3rem   (48px)
3xl: 4rem   (64px)
```

## 🎬 Animations

### Fade-In (On Scroll)
```css
@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}
```

### Hover Effects
- Buttons: `-4px` elevation + shadow
- Cards: `scale(1.02)` + shadow
- Links: Underline width animation

### Reduced Motion Support
```css
@media (prefers-reduced-motion: reduce) {
  * { animation-duration: 0.01ms; }
}
```

## 🔍 CSS Custom Properties (Variables)

```css
/* Colors */
--color-mocha: #A6856F;
--color-blue: #A0D4E0;
--color-grey: #F2F0EA;
--color-dark: #2B2B2B;

/* Typography */
--font-display: 'Montserrat', sans-serif;
--font-body: 'Roboto', sans-serif;

/* Layout */
--nav-height: 60px;
--max-width: 1200px;
--border-radius: 8px;

/* Effects */
--transition: 0.3s ease;
--shadow-md: 0 4px 12px rgba(43, 43, 43, 0.1);
```

## 📱 Mobile Menu

**Hidden by default on mobile, shown on hamburger click:**
```html
<div class="mobile-menu" id="mobile-menu">
  <a href="#features">Features</a>
  <a href="#showcase">Showcase</a>
  <!-- Auto-closes when link clicked -->
</div>
```

**Hamburger Animation:**
- Top bar: `rotate(45deg) translateY(10px)`
- Middle bar: `opacity: 0`
- Bottom bar: `rotate(-45deg) translateY(-10px)`

## 🎯 Grid System

### Feature Cards
```css
/* Mobile */ grid-template-columns: 1fr;
/* Tablet */ grid-template-columns: repeat(2, 1fr);
/* Desktop */ grid-template-columns: repeat(3, 1fr);
```

### Testimonials
```css
/* Mobile */ grid-template-columns: 1fr;
/* Tablet+ */ grid-template-columns: repeat(2, 1fr);
```

### Showcase
```css
/* Mobile */ grid-template-columns: 1fr;
/* Tablet+ */ grid-template-columns: 1fr 1fr;
```

## 🚀 Performance Tips

1. **Single File:** No external dependencies
2. **GPU Acceleration:** Uses `transform` for animations
3. **Efficient Scrolling:** Intersection Observer (lazy animation)
4. **Keyboard Support:** No layout thrashing on keyboard nav
5. **Touch Friendly:** 44px minimum tap targets

## 🔗 Navigation Structure

```
Header (Sticky)
├── Logo
├── Desktop Nav Links
└── Hamburger Menu (Mobile)
    └── Mobile Menu (Hidden)
        ├── Features Link
        ├── Showcase Link
        ├── Testimonials Link
        └── CTA Button

Main Content
├── Hero Section
├── Features Section
├── Showcase Section
├── Testimonials Section
├── CTA Section
└── Footer
```

## ✅ Testing Checklist

- [ ] Test on mobile (320px width)
- [ ] Test on tablet (768px width)
- [ ] Test on desktop (1024px+ width)
- [ ] Test keyboard navigation (Tab, Arrow keys, Enter)
- [ ] Test with screen reader (NVDA/JAWS/VoiceOver)
- [ ] Test Escape key (close mobile menu)
- [ ] Test button clicks (show toast notification)
- [ ] Test anchor link scrolling (smooth behavior)
- [ ] Test hamburger menu toggle
- [ ] Test focus states visibility
- [ ] Test color contrast (use WCAG validator)
- [ ] Test responsive images

## 📊 Lighthouse Metrics Target

- **Performance:** 90+
- **Accessibility:** 95+
- **Best Practices:** 90+
- **SEO:** 100
- **Core Web Vitals:** All Green

## 🎓 Key Learnings

1. **Semantic HTML** prevents divitis
2. **CSS Variables** enable theming and maintenance
3. **Mobile-first** simplifies responsive design
4. **Flexbox + Grid** handle 90% of layouts
5. **Vanilla JS** sufficient for most interactivity
6. **Accessibility** not an afterthought
7. **Performance** comes from smart CSS, not JavaScript
8. **Single file** can be production-quality

## 🛠️ Customization

### Change Primary Color
```css
:root {
  --color-mocha: #YOUR-COLOR;
}
```

### Change Font
```css
:root {
  --font-display: 'Your Font', sans-serif;
  --font-body: 'Your Font', sans-serif;
}
```

### Adjust Spacing
```css
:root {
  --space-lg: 2rem; /* Was 1.5rem */
}
```

### Add New Section
```html
<section id="my-section" class="my-section">
  <div class="section-container">
    <h2>Section Title</h2>
    <!-- Content -->
  </div>
</section>
```

---

**Quick Tip:** Use DevTools to inspect responsive behavior:
1. Press `F12` (DevTools)
2. Click device icon (toggle device toolbar)
3. Choose device or drag to custom width
4. Test at 320px, 768px, 1024px breakpoints

**Pro Tip:** Test keyboard navigation:
1. Disable mouse
2. Use only Tab, Enter, Escape
3. Ensure all interactive elements are reachable
4. Focus states should be clearly visible

---

*Build responsive, accessible, modern websites with confidence!* ✨
