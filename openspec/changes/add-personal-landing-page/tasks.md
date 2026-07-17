# Tasks: Add Personal Landing Page

## 1. Photo asset

- [x] 1.1 Produce a web-optimized avatar `assets/photo.jpg` (~320px square crop, < 50 KB) from `assets/DEC-IX_my_photo.jpg` using ImageMagick or a PowerShell/System.Drawing script; keep the original file untouched. If no tooling works, skip and reference the original directly in 2.2.

## 2. Page implementation

- [x] 2.1 Create `index.html` skeleton: `<html lang="en">`, UTF-8 charset, viewport meta, `<title>Yusuf Duman</title>`, meta description, semantic `<main>`/`<footer>` structure.
- [x] 2.2 Add identity section: circular avatar (with `alt="Yusuf Duman"`), name, "Software Engineer" title, and the intro copy from design.md Decision 5.
- [x] 2.3 Add contact links with inline SVG icons: GitHub (https://github.com/yusufdmn), LinkedIn (https://www.linkedin.com/in/yusuf-duman-094397203/), mailto:yusufveduman@gmail.com — external links with `target="_blank"` and `rel="noopener noreferrer"`.
- [x] 2.4 Add the maintenance notice with the personal-works/blog mention and the "every post 100% human-written" statement, styled as a distinct badge/panel.
- [x] 2.5 Add embedded CSS implementing the dark minimal design (design.md Decision 3): dark background, single accent color, system font stack, centered ~40rem column, subtle avatar glow, link hover transitions, visible focus styles, AA-contrast text.
- [x] 2.6 Make the layout responsive: no horizontal scroll and legible content down to 360px-wide viewports.

## 3. Verification

- [x] 3.1 Open the page in a browser and verify all spec scenarios: content visible without scrolling on desktop, links open correctly (new tab for GitHub/LinkedIn, mail client for email), maintenance notice text complete, fully styled with no external requests.
- [x] 3.2 Verify responsive behavior at ~360px width (devtools) and that a missing photo degrades gracefully (alt text, unbroken layout).
