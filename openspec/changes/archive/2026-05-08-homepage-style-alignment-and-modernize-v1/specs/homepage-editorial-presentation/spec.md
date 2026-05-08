## ADDED Requirements

### Requirement: Single warm light visual system
The homepage SHALL use a single light visual system based on warm ivory, stone neutrals, sky accents, and amber accents, with reusable CSS custom properties for the core palette.

#### Scenario: Homepage loads with light palette
- **WHEN** a visitor opens the homepage
- **THEN** the page background is warm light rather than dark
- **AND** primary text, muted text, surfaces, borders, and accents are derived from the shared light palette tokens
- **AND** there is no dark-mode baseline, dark-mode toggle, or dark alternate theme applied to the homepage

### Requirement: Editorial typography hierarchy
The homepage SHALL use a refined serif voice for major headings and a modern sans-serif voice for body text, links, controls, labels, and cards.

#### Scenario: Visitor scans the homepage
- **WHEN** a visitor views the hero, section headings, body copy, and cards
- **THEN** major headings use editorial serif typography
- **AND** supporting copy and controls use modern sans-serif typography
- **AND** metadata labels, badges, and small category text use uppercase tracking treatment

### Requirement: Modern hero photo presentation
The homepage SHALL present the top photos inside a modern hero composition with a rounded hero frame, layered gradient background, photo rail or card-strip treatment, compact controls, and stable responsive dimensions.

#### Scenario: Visitor navigates hero photos
- **WHEN** a visitor activates the hero photo controls
- **THEN** the visible photo state changes without layout shift
- **AND** the active photo state is visually clear
- **AND** the controls remain reachable and usable on desktop and mobile viewports

### Requirement: Hero thematic framing
The homepage SHALL add small badge and thematic chip treatments around the introductory copy to communicate the personal/professional themes without replacing the existing content.

#### Scenario: Visitor reads the opening section
- **WHEN** a visitor lands on the homepage
- **THEN** the hero presents the existing personal introduction in a polished editorial frame
- **AND** the hero includes concise thematic chips or badges connected to the existing content, such as data, AI, languages, travel, or publications

### Requirement: Light editorial cards and links
The homepage SHALL render social links, featured articles, and publications as light editorial cards or controls with stone borders, soft shadows, consistent corner radii, and restrained hover/focus movement.

#### Scenario: Visitor interacts with links and cards
- **WHEN** a visitor hovers, focuses, or taps a social link, featured article, or publication card
- **THEN** the element provides a clear interaction affordance
- **AND** the interaction remains visually restrained without large scale jumps
- **AND** each existing outbound destination remains available

### Requirement: Responsive layout integrity
The homepage SHALL maintain readable, non-overlapping layout from mobile through desktop widths.

#### Scenario: Visitor views narrow and wide screens
- **WHEN** the homepage is viewed at common mobile and desktop viewport widths
- **THEN** text remains within its containers
- **AND** cards, hero photos, controls, and language UI do not overlap incoherently
- **AND** repeated card grids adapt without horizontal page overflow
