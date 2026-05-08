## ADDED Requirements

### Requirement: Centralized English and German copy map
The homepage SHALL define user-facing translatable copy in a centralized JavaScript copy map with English and German entries.

#### Scenario: Developer audits language coverage
- **WHEN** a developer inspects the homepage source
- **THEN** primary visible text for the hero, about section, social links, featured articles, publications, controls, badges, and chips is available through `copy.en` and `copy.de` or structured data referenced by those language keys
- **AND** proper nouns, publication titles, and canonical external names may remain unchanged where translation would reduce clarity

### Requirement: Language toggle control
The homepage SHALL provide an EN/DE toggle pill that lets visitors switch between English and German without leaving the page.

#### Scenario: Visitor switches to German
- **WHEN** a visitor activates the DE option
- **THEN** homepage copy updates to German
- **AND** the active DE state is visually and semantically indicated
- **AND** no duplicate or overlapping language toggle hit targets are visible

### Requirement: Persisted language preference
The homepage SHALL persist the selected language in `localStorage` and restore it on later visits when the saved value is valid.

#### Scenario: Visitor reloads after selecting German
- **WHEN** a visitor selects DE and reloads the homepage
- **THEN** the homepage initializes in German
- **AND** the DE toggle state remains active

#### Scenario: Saved language value is invalid
- **WHEN** the saved language value is missing or not one of the supported language codes
- **THEN** the homepage initializes in English

### Requirement: Semantic language handling
The homepage SHALL update document language semantics when the visible language changes.

#### Scenario: Language semantics update
- **WHEN** the active language changes between English and German
- **THEN** the document language reflects the active language code
- **AND** language toggle controls expose accessible names and pressed states

### Requirement: Bilingual card rendering
The homepage SHALL render featured article and publication metadata from structured bilingual data while preserving each card's image and outbound URL.

#### Scenario: Visitor switches language while viewing cards
- **WHEN** a visitor changes the active language
- **THEN** card headings, descriptions, labels, and image alt text update where translated copy is provided
- **AND** every card continues to link to the same destination as in the English view
