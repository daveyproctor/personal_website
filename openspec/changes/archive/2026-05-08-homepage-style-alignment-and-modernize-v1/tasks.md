## 1. Homepage Structure

- [x] 1.1 Review `/home/dproctor/github/personal_website/index.html` and list the current content, links, photos, and card data that must be preserved.
- [x] 1.2 Restructure the body markup into semantic homepage regions for hero, about/social links, featured articles, and publications.
- [x] 1.3 Preserve all existing outbound URLs and existing `photos/` asset references while preparing them for structured rendering.

## 2. Light Editorial Styling

- [x] 2.1 Replace the dark CSS baseline with `:root` design tokens for warm light background, surfaces, text, muted text, sky accent, amber accent, borders, radii, and shadows.
- [x] 2.2 Add editorial serif typography for hero and section headings and modern sans-serif typography for body copy, labels, controls, links, and cards.
- [x] 2.3 Restyle social links, featured article cards, and publication cards as light editorial surfaces with stone borders, soft shadows, uppercase micro-labels, and restrained hover/focus states.
- [x] 2.4 Check CSS color usage and remove stale dark-mode or cyan-on-dark styling that conflicts with the target palette.

## 3. Modern Hero And Photo Rail

- [x] 3.1 Rebuild the opening area as a rounded hero composition with layered radial/linear gradients and a polished content frame.
- [x] 3.2 Convert the current top photos into a modern photo rail or card-strip presentation with stable aspect ratios and responsive sizing.
- [x] 3.3 Add compact photo controls with visible active state, accessible labels, keyboard focus states, and mobile-friendly touch/swipe behavior where practical.
- [x] 3.4 Add concise badge and thematic chip treatments tied to the existing professional, language, travel, and publication themes.

## 4. Bilingual Copy System

- [x] 4.1 Create a centralized `copy` map with `en` and `de` entries for homepage sections, controls, badges, chips, social links, featured article cards, and publication cards.
- [x] 4.2 Implement language state initialization with English fallback and valid saved-language restoration from `localStorage`.
- [x] 4.3 Implement an EN/DE toggle pill that updates visible copy, active state, accessible labels, and `document.documentElement.lang`.
- [x] 4.4 Render repeated card content and image alt text from structured bilingual data while preserving URLs and asset paths.

## 5. Responsive And Accessibility Verification

- [x] 5.1 Verify the page at representative desktop and mobile widths for text overflow, control overlap, card grid behavior, and hero photo framing.
- [x] 5.2 Verify EN/DE switching, reload persistence, invalid saved-language fallback, and document language semantics.
- [x] 5.3 Verify hero photo controls, hover/focus states, outbound links, and image alt text.
- [x] 5.4 Run an appropriate static/browser smoke check for `index.html` and document any remaining visual or translation follow-ups.
