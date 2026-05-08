## Why

The current homepage content is strong, but its dark-first presentation, generic typography, and dated single-image carousel no longer match the warmer editorial-product visual language used in the referenced `metadata_wide_record` work. This change modernizes the homepage while preserving the existing professional, travel, article, and publication content.

## What Changes

- Remove the dark theme entirely and move the homepage to a single warm light palette using shared CSS design tokens.
- Rebuild the top section into a modern hero composition with soft gradient atmosphere, a rounded hero frame, photo rail/card treatment, compact controls, and small thematic chips.
- Replace the monolingual inline copy with a centralized English/German copy map.
- Add an EN/DE toggle pill that persists the selected language in `localStorage` and updates page language semantics.
- Refresh links, article cards, and publication cards to use light editorial surfaces, stone borders, soft shadows, uppercase micro-labels, and restrained hover movement.
- Keep the site as a static homepage without introducing a build pipeline or framework dependency.

## Capabilities

### New Capabilities
- `homepage-editorial-presentation`: Covers the single light visual system, modern hero/photo presentation, and refreshed card/link styling for the static homepage.
- `homepage-bilingual-content`: Covers the English/German copy scaffold, language toggle behavior, persistence, and semantic language handling.

### Modified Capabilities
- None.

## Impact

- Affected code: `/home/dproctor/github/personal_website/index.html`.
- Affected assets: existing `photos/` assets are reused for the hero rail and cards.
- APIs/dependencies: no external runtime API or package dependency is expected.
- Behavior: existing outbound links remain intact; visible copy becomes language-aware through client-side JavaScript.
