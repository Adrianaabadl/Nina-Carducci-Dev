# Intervention Report

**Client:** Nina Carducci

## I - Lighthouse Score

### Lighthouse score before optimisation
**Initial Results:**
- Performance: 65/100
- Accessibility: 68/100
- Best Practices: 100/100
- SEO: 70/100
- **Average Score: 75.75/100**

![alt text](original-report.png)

### Lighthouse score after optimisation
**Final Results:**
- Performance: 99/100 ✅ (+34 points improvement)
- Accessibility: 100/100 ✅ (+32 points improvement)
- Best Practices: 100/100 ✅ (maintained)
- SEO: 100/100 ✅ (+30 points improvement)
- **Average Score: 99.75/100** ✅ (+24 points overall improvement)

![alt text](optimzed-report.png)

## II - Details of optimisations and interventions carried out

### 1 - Images
- Optimized project contains 39 images in `assets/images`.
- Current total image size: 4.4 MB.
- Original project contains 15 images in `assets/images` with a total size of 30 MB.

**Changes performed:**
- Converted images from JPEG/PNG to `WebP` format to reduce file size.
- Added responsive versions using `srcset` and `sizes` for the gallery and slider.
- Used `loading="lazy"` on gallery images so they load only when they enter the viewport.
- Added `decoding="async"`, fixed `width`/`height`, and `fetchpriority="high"` on the hero slider image to improve LCP.
- Preloaded critical CSS (`bootstrap.min.css`, `style.css`) and the main slider image.

**After modifications:**
- Total image weight: 4.4 MB.
- Size reduction gain: 85.3% (30 MB → 4.4 MB, saving 25.6 MB)

### Comparison with the original project
| Metric | Original | Optimized | Gain |
|--------|----------|-----------|------|
| **Performance Score** | 65 | 99 | +34 (52% improvement) |
| **Accessibility Score** | 68 | 100 | +32 (47% improvement) |
| **Best Practices Score** | 100 | 100 | — (maintained) |
| **SEO Score** | 70 | 100 | +30 (43% improvement) |
| **Lighthouse Average** | 75.75 | 99.75 | +24 (32% improvement) |
| **Total Image Size** | 30 MB | 4.4 MB | -25.6 MB (85.3% reduction) |
| **Image Files** | 15 | 39 | +24 (responsive variants) |
| **CSS** | Unminified | Minified | Render-blocking eliminated |
| **JavaScript** | Synchronous | Defer loading | Parse-blocking eliminated |
| **Wave Errors** | Multiple | 0 | 100% compliant |

**Key improvements documented:**
- Original project used 15 image files totaling 30 MB; optimized version uses 39 responsive WebP variants totaling 4.4 MB
- Original assets were full-size JPEG/PNG without responsive `srcset` and without lazy loading
- Original project used unminified `bootstrap.css` and `bootstrap.bundle.js` with synchronous script loading
- Optimized project uses `bootstrap.min.css`, `bootstrap.bundle.min.js`, `maugallery.min.js`, with `defer` and proper preload strategy
- Original project had accessibility gaps (missing alt text, no aria-labels, inconsistent heading hierarchy)
- All accessibility issues were corrected in the optimized version (WCAG compliant)

### 2 - Code and resource optimisation
- Switched to `bootstrap.min.css` instead of the unminified `bootstrap.css` used in the original project.
- Loaded scripts with `defer` to avoid render-blocking, while the original project loaded its scripts synchronously:
  - `bootstrap.bundle.min.js`
  - `jquery-3.4.1.min.js`
  - `maugallery.min.js`
  - `scripts.js`
- Optimized font loading with `preconnect` and `preload` for `fonts.googleapis.com`.
- Reduced JavaScript and kept external dependencies lightweight.
- Added a minified `maugallery.min.js` file in the optimized project; the original used the unminified `maugallery.js`.
- Main current assets:
  - `assets/bootstrap/bootstrap.min.css` — 164 KB
  - `assets/bootstrap/bootstrap.bundle.min.js` — 80 KB
  - `assets/maugallery.min.js` — 8 KB
  - `assets/scripts.js` — 4 KB
  - `assets/style.css` — 8 KB

### 3 - SEO and structured data
- Optimized meta description present and properly formatted in `<head>`.
- Implemented Schema.org `LocalBusiness` markup using JSON-LD for professional photography:
  - business name: Nina Carducci - Photographe
  - address: 68 avenue Alsace-Lorraine, Bordeaux, 33200, FR
  - phone number: +33 5 56 67 78 89
  - URL: https://nina-carducci-dev-sigma.vercel.app/
  - services offered: Photography, Portrait Photography, Wedding Photography, Corporate Photography
  - social links: Instagram profile included
- Added descriptive `alt` attributes to all key images with relevant keywords.
- Used semantic HTML5 headings and sectioning (`<main>`, `<h1>`, `<h2>`, `<h3>`) for proper document structure.
- **SEO Score Improvement:** 70/100 → 100/100 (+30 points, 43% improvement)

### 4 - Accessibility improvements
- Added descriptive alternative text to all images (no generic "image" labels).
- The Instagram social link includes `aria-label="Instagram Nina Carducci"` for accessible external linking.
- Carousel controls include proper `aria-label` attributes and hidden text (`visually-hidden` for screen reader support).
- Contact form fields use `<label>` elements correctly associated with inputs via `for` and `id` attributes.
- Maintained consistent heading structure (H1 → H2 → H3) to support screen reader navigation and semantic flow.
- Added language declaration: `lang="fr"` on the HTML element for proper regional markup.
- **Accessibility Score Improvement:** 68/100 → 100/100 (+32 points, 47% improvement)
- **Wave Audit Result:** 0 errors detected (100% WCAG compliant)

## III - Site accessibility

### Accessibility before optimisation

![alt text](<acceessibility-original.png>)

### Accessibility after optimisation

![alt text](<acceessibility-optimized.png>)

### Changes made
- Added alt text to all key images.
- Added `aria-label` to the Instagram link.
- Improved the semantic heading structure and content grouping.
- Ensured carousel controls are keyboard accessible and screen reader friendly.
- Verified the contact form labels are correctly connected to each field.

## IV - Details of additional work carried out at the customer's request
- No additional customer-requested work was included in this deliverable.
- If requested, additional improvements can be made such as:
  - further mobile bandwidth optimisation,
  - implementation of a functional contact form backend,
  - adding structured data for reviews or events.

## V - Acceptance log

| ID | Action | Initial result | Expected result | Status | Remarks and comments |
| --- | --- | --- | --- | --- | --- |
| 1 | Image optimisation | 30 MB, 15 files, JPEG/PNG | 4.4 MB WebP responsive | ✅ | 85.3% size reduction, 39 responsive variants |
| 2 | CSS/JS optimisation | Unminified/render-blocking | Minified, defer scripts | ✅ | Bootstrap and critical resources preloaded |
| 3 | Accessibility improvement | 68/100, multiple errors | 100/100, 0 errors | ✅ | WCAG compliant, all alt text added, semantic structure fixed |
| 4 | Technical SEO | Missing structured data, 70/100 | Schema.org + 100/100 | ✅ | JSON-LD LocalBusiness implemented, rich snippets valid |
| 5 | Performance optimization | 65/100 Lighthouse score | 99/100 Lighthouse score | ✅ | +34 points improvement, fastest page render |

**Lighthouse Scores Achieved:**
- ✅ Performance: 99/100 (Target: 90+ EXCEEDED)
- ✅ Accessibility: 100/100 (Target: 90+ EXCEEDED)  
- ✅ Best Practices: 100/100 (Target: 90+ EXCEEDED)
- ✅ SEO: 100/100 (Target: 90+ EXCEEDED)
- ✅ Average Score: 99.75/100 (+24 points improvement from original 75.75)

### To do / Solved
- [✅] Lighthouse scores documented: All 4 metrics exceed 90% target
- [✅] Wave accessibility audit: 0 errors verified
- [✅] Image optimization: 85.3% reduction achieved (30 MB → 4.4 MB)
- [✅] Schema.org LocalBusiness: JSON-LD implemented and validated
- [✓] Pending: Add Lighthouse PDF report screenshot to Appendix

## Appendix
- [Full Lighthouse audit report](https://github.com/Adrianaabadl/Nina-Carducci-Dev/blob/development/lighthouse-report.pdf)
