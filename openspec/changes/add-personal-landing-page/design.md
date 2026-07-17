# Design: Add Personal Landing Page

## Context

The repository is empty (no site code). Yusuf wants a temporary one-page presence: dark minimal look, English content, photo + intro + contact links + under-maintenance notice. The photo already exists at `assets/DEC-IX_my_photo.jpg` (~255 KB JPEG), placed there by Yusuf. The page will eventually be replaced by a full site with portfolio and blog.

## Goals / Non-Goals

**Goals:**
- Ship a single, self-contained, framework-free static page that looks intentional and modern.
- Zero dependencies and zero build step — open `index.html` and it works; deployable to any static host.
- Content that reads as genuinely human, per Yusuf's request.

**Non-Goals:**
- The full personal website, portfolio pages, blog engine, CMS, analytics, dark/light theme toggle, multi-language support.
- Hosting/deployment setup (GitHub Pages etc.) — noted as a follow-up, not part of this change.

## Decisions

1. **Single `index.html` with embedded `<style>`** — over separate CSS file or any framework.
   *Why:* one file is the simplest thing that satisfies "no heavy framework"; at this size a separate stylesheet adds a request and a file with no benefit. Tailwind CDN was considered and rejected: it's an external dependency and violates the self-contained requirement.

2. **Photo used from `assets/DEC-IX_my_photo.jpg` as-is, uncropped** — Yusuf cropped the photo himself (~1467×1515) and decided the full scene should be shown; it is displayed as a rounded-rectangle image (~280px wide, CSS-constrained), not a circular avatar, so nothing is masked off. No web-optimized copy is generated; the ~340 KB weight is accepted for this single-image page.
   *Why:* superseded the original "optimize to a 320px circular avatar" decision at Yusuf's request during implementation — authenticity of the full photo over byte savings.

3. **Design language:** near-black background (`#0d1117`-family), soft light-gray text, one accent color (teal/cyan range, e.g. `#2dd4bf`) used sparingly for links/hover and the maintenance badge. System font stack (`system-ui, -apple-system, Segoe UI, Roboto, ...`). Centered single column, max-width ~40rem, generous whitespace. Subtle touches only (e.g., a faint radial glow behind the avatar, gentle link hover transitions) — no animation libraries, no particle effects.
   *Why:* matches the agreed "dark minimal" direction; system fonts avoid webfont loading and licensing.

4. **Contact links as labeled links with inline SVG icons** (GitHub, LinkedIn, Mail).
   *Why:* inline SVG keeps the page self-contained (no icon font/CDN) and scales crisply. Text labels accompany icons for accessibility and clarity.

5. **Copy (final — Yusuf's wording, use verbatim):**
   - Intro: "I'm a software engineer, building backend systems primarily with C# and .NET. Curious, always learning, both fascinated by and skeptical of AI and agentic systems."
   - Maintenance notice: "This site is under construction. Once it's ready you'll find my projects and my blog here. Every post will be 100% human-written. I value authenticity in this age more than ever."
   *Why:* reworded by Yusuf in his own voice; only grammar corrected. Implementation must use these sentences exactly — no further edits.

6. **Accessibility/semantics:** semantic landmarks (`<main>`, `<footer>`), `alt` text on the photo, visible focus styles, WCAG AA contrast for text on the dark background, `lang="en"` on `<html>`.

## Risks / Trade-offs

- [Embedded CSS makes the future full site start from scratch] → Acceptable: the page is explicitly disposable; contact URLs are the only stable contract.
- [Image tooling may be unavailable on this Windows machine] → Fallback chain in Decision 2; worst case ships the original JPEG with CSS sizing (page still correct, just heavier).
- [Copy drift during implementation] → Copy is finalized in Decision 5; implement it verbatim and don't paraphrase.

## Open Questions

- None blocking. Deployment target (likely GitHub Pages under `yusufdmn.github.io`) deferred to a future change.
