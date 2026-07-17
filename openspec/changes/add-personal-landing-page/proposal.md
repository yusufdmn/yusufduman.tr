# Proposal: Add Personal Landing Page

## Why

Yusuf Duman needs an online presence now, but the full personal website (portfolio + blog) is out of scope for the moment. A one-page maintenance/landing page provides immediate visibility — who he is, how to reach him — while signaling that a fuller site is coming.

## What Changes

- Add a single static landing page (`index.html`) with a dark, minimal, modern design — no framework, no build step.
- Page content (English):
  - Photo, name ("Yusuf Duman"), and title (Software Engineer).
  - A brief, human-sounding intro (1–2 sentences) reflecting: .NET/backend engineering, curiosity, constant self-development, and interest in AI/agentic systems.
  - Contact links: GitHub (https://github.com/yusufdmn), LinkedIn (https://www.linkedin.com/in/yusuf-duman-094397203/), email (yusufveduman@gmail.com).
  - An under-maintenance notice stating the site is being built and will later host his personal works and blog — with an explicit note that the blog posts will be 100% human-written to preserve human authenticity.
- Responsive layout (mobile through desktop).

## Capabilities

### New Capabilities

- `landing-page`: The one-page personal maintenance site — its content, links, visual style, and responsive behavior.

### Modified Capabilities

<!-- None — this is a greenfield project with no existing specs. -->

## Impact

- New files: `index.html`. No existing code is affected — the repository currently contains no site code.
- No dependencies, no backend, no build tooling. Deployable to any static host (e.g., GitHub Pages) as-is.
- The future full website will replace this page; nothing here should constrain that beyond keeping the URLs/contact info stable.
