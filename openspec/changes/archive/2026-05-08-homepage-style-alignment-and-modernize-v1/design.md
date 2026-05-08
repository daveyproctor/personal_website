## Context

The homepage is currently a single static `/home/dproctor/github/personal_website/index.html` file with embedded CSS and JavaScript. It uses a dark body background, cyan links and buttons, a single-active-image carousel, and inline English copy. The requested target style comes from `/home/dproctor/abgit/go-to-market/web/metadata_wide_record/` and the related web-designer guidance: warm ivory/stone base, sky and amber accents, refined serif display typography, modern sans body typography, rounded editorial surfaces, soft shadows, uppercase metadata labels, and a centralized English/German language treatment.

The change should preserve the existing homepage content and static deployment model while modernizing the presentation and adding bilingual behavior.

## Goals / Non-Goals

**Goals:**
- Replace the dark theme with one warm light visual system using reusable CSS custom properties.
- Present the opening photos as a modern hero/photo rail rather than a dated single-image carousel.
- Refresh article and publication cards into a light editorial card system with consistent visual hierarchy.
- Centralize user-facing copy in an English/German JavaScript copy map.
- Provide a keyboard-operable EN/DE toggle that persists via `localStorage` and updates document language semantics.
- Keep all existing outbound links and core content available in both languages.
- Maintain a static, dependency-free homepage that can be opened directly or served by the existing site host.

**Non-Goals:**
- Rewriting the homepage in React, TypeScript, Tailwind, or a Vite route.
- Adding a backend, translation service, analytics, or external runtime dependency.
- Replacing the existing homepage content strategy or adding new publications beyond the current set.
- Adding a site-wide dark mode or theme switcher.
- Changing deployment topology or domain routing.

## Decisions

1. **Use static HTML/CSS/JavaScript instead of introducing the referenced web stack.**
   - Rationale: the current site is static and the requested change is stylistic/interaction-level, so adding a build pipeline would increase maintenance without being necessary.
   - Alternative considered: port the homepage to a Vite/Tailwind route. That would improve component organization, but it is disproportionate for one homepage edit and would change the deployment shape.

2. **Create a single light token palette in `:root`.**
   - Rationale: tokens such as `--bg`, `--surface`, `--text`, `--muted`, `--accent-sky`, and `--accent-amber` make the homepage style explicit and remove scattered dark/cyan values.
   - Alternative considered: keep dark mode and add a light override. The user explicitly wants dark mode removed, and the target reference is light-first.

3. **Rebuild the top section as an editorial hero with a photo rail.**
   - Rationale: a hero frame with gradient atmosphere, layered photo cards/strip, controls, and chips better matches the referenced `metadata_wide_record` composition while keeping the personal photos prominent.
   - Alternative considered: keep the current carousel and restyle arrows. That would improve colors but not address the dated presentation.

4. **Represent translatable content with a centralized `copy` object.**
   - Rationale: a single map (`copy.en`, `copy.de`) keeps translation coverage auditable and avoids inline conditionals scattered through markup.
   - Alternative considered: duplicate full HTML blocks per language. That would be simple initially but risks content drift and duplicate maintenance.

5. **Render language-specific content by `data-copy` attributes and small targeted render functions.**
   - Rationale: simple text nodes can be updated declaratively by key, while repeated content such as cards and chips can be rebuilt from structured arrays.
   - Alternative considered: manually update every DOM node by selector. That is more brittle as the homepage grows.

6. **Preserve native links and assets.**
   - Rationale: existing LinkedIn, GitHub, article, and publication URLs are part of the content the user likes. The redesign should not create link regressions.
   - Alternative considered: consolidate links into fewer CTAs. That could simplify the page but would remove discoverability of current content.

## Risks / Trade-offs

- **Risk: German translations may subtly change tone or claims.** → Mitigation: keep translated copy close to the existing factual meaning, preserve names/titles in canonical form, and make language switching easy to compare.
- **Risk: a static copy renderer can miss a newly added text node.** → Mitigation: keep the copy map centralized and use `data-copy` keys or structured arrays consistently for all user-facing visible text.
- **Risk: hero photo rail controls may regress accessibility if implemented as decorative buttons only.** → Mitigation: use real buttons with labels, focus states, visible active state, and preserve swipe support where practical.
- **Risk: large photos can cause layout shifts.** → Mitigation: use stable dimensions, `aspect-ratio`, `object-fit`, and bounded responsive constraints for image cards.
- **Trade-off: the static file will contain more JavaScript than before.** → This is acceptable because it avoids a build dependency while still enabling bilingual rendering and modern controls.

## Migration Plan

1. Replace the embedded dark CSS with light design tokens, base typography, layout, hero, control, and card styles.
2. Restructure the body markup into a hero section, about section, featured article section, and publication section using semantic containers.
3. Add the centralized `copy` map and language state management with `localStorage` fallback.
4. Render language-aware text, chips, link labels, and card content from structured data.
5. Preserve existing photo and publication assets, updating alt text to be meaningful in the current language.
6. Verify the static page in a browser at desktop and mobile widths, including EN/DE toggle persistence, photo controls, links, and responsive layout.

Rollback is a normal Git revert of `/home/dproctor/github/personal_website/index.html` because no schema, dependency, or deployment migration is introduced.

## Open Questions

- Whether the German copy should be idiomatic marketing/editorial German or a close translation of the English source. The implementation should default to close factual translation unless directed otherwise.
- Whether all current top photos should remain in the hero rail or whether one should be held back for a later about/signature section. The implementation can start with the current three-photo set.
