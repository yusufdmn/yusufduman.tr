## ADDED Requirements

### Requirement: Identity section
The page SHALL display Yusuf Duman's photo, name, and title ("Software Engineer") as the primary content, and a brief intro of one to two sentences. The intro MUST read as human-written (no corporate boilerplate) and convey: .NET/backend engineering focus, curiosity and constant self-development, and interest in AI/agentic systems.

#### Scenario: Visitor opens the page
- **WHEN** a visitor loads the page
- **THEN** they see the photo, the name "Yusuf Duman", the title "Software Engineer", and the 1–2 sentence intro without scrolling on a typical desktop viewport

#### Scenario: Photo fails to load
- **WHEN** the photo asset is missing or fails to load
- **THEN** the layout does not break and a meaningful `alt` text ("Yusuf Duman") is shown

### Requirement: Contact links
The page SHALL provide three contact links: GitHub (`https://github.com/yusufdmn`), LinkedIn (`https://www.linkedin.com/in/yusuf-duman-094397203/`), and email (`mailto:yusufveduman@gmail.com`). External links MUST open in a new tab with `rel="noopener noreferrer"`.

#### Scenario: Visitor clicks GitHub or LinkedIn
- **WHEN** a visitor clicks the GitHub or LinkedIn link
- **THEN** the corresponding profile opens in a new browser tab

#### Scenario: Visitor clicks email
- **WHEN** a visitor clicks the email link
- **THEN** their mail client opens a compose window addressed to yusufveduman@gmail.com

### Requirement: Maintenance notice
The page SHALL display a notice stating that the website is under maintenance/construction and that, when complete, it will host Yusuf's personal works and blog. The notice MUST state that the blog posts will be 100% human-written to preserve and reflect human authenticity.

#### Scenario: Visitor reads the notice
- **WHEN** a visitor loads the page
- **THEN** they see the under-maintenance text, the mention of upcoming personal works and blog, and the statement that blog content will be 100% human-written

### Requirement: Visual style
The page SHALL use a dark, minimal, modern design: dark background, centered single-column layout, a single accent color, and a system font stack. It MUST be implemented as static HTML and CSS with no JavaScript frameworks, CSS frameworks, external CDNs, or build step.

#### Scenario: Page loads offline-independent
- **WHEN** the page is served from any static host with no network access to third parties
- **THEN** it renders fully styled, since all CSS is local and no external resources are referenced

### Requirement: Responsive layout
The page SHALL render legibly and without horizontal scrolling from small mobile viewports (~360px wide) through desktop.

#### Scenario: Mobile visitor
- **WHEN** the page is viewed at a 360px-wide viewport
- **THEN** all content (photo, text, links, notice) remains readable and the body does not scroll horizontally

### Requirement: Page metadata
The page SHALL include a proper `<title>` ("Yusuf Duman"), a meta description, UTF-8 charset, and a responsive viewport meta tag.

#### Scenario: Link shared or indexed
- **WHEN** the page URL is shared or crawled
- **THEN** the title "Yusuf Duman" and the meta description are available to the consumer
