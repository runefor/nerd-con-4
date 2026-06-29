# NerdCon Notes Design System

## 1. Atmosphere & Identity

A quiet review desk for post-seminar synthesis. The signature is a split between event facts and session learning notes: schedule details stay compact, while each session gets enough breathing room to scan key ideas without rereading raw Markdown.

## 2. Color

### Palette

| Role | Token | Light | Dark | Usage |
|------|-------|-------|------|-------|
| Surface/primary | --surface-primary | #F6F7F4 | #121411 | Page background |
| Surface/secondary | --surface-secondary | #FFFFFF | #1A1D18 | Panels and notes |
| Surface/elevated | --surface-elevated | #EEF1EA | #23271F | Callouts |
| Text/primary | --text-primary | #151813 | #F4F6F1 | Headings and body |
| Text/secondary | --text-secondary | #536055 | #B8C0B4 | Secondary copy |
| Text/tertiary | --text-tertiary | #7D887B | #899284 | Metadata |
| Border/default | --border-default | #D8DED3 | #3A4236 | Dividers |
| Border/subtle | --border-subtle | #E8ECE3 | #2B3128 | Soft separations |
| Accent/primary | --accent-primary | #2F6F4E | #7ED8A4 | Links and active states |
| Accent/hover | --accent-hover | #24573D | #A0E5BC | Link hover |
| Status/info | --status-info | #355C7D | #9CC2E5 | Tooling notes |
| Status/warning | --status-warning | #91650D | #E8C56F | Caveats |
| Status/error | --status-error | #A63A3A | #F2A0A0 | Errors |

### Rules

- Use the green accent only for links, focus, and key facts.
- Keep body surfaces neutral. No decorative gradients.
- Extend this table before introducing any new color.

## 3. Typography

### Scale

| Level | Size | Weight | Line Height | Tracking | Usage |
|-------|------|--------|-------------|----------|-------|
| Display | clamp(34px, 5vw, 58px) | 750 | 1.05 | 0 | Page title |
| H1 | 34px | 720 | 1.15 | 0 | Major sections |
| H2 | 26px | 680 | 1.25 | 0 | Session titles |
| H3 | 20px | 650 | 1.35 | 0 | Card titles |
| Body/lg | 18px | 450 | 1.75 | 0 | Lead text |
| Body | 16px | 430 | 1.72 | 0 | Default Korean body |
| Body/sm | 14px | 430 | 1.55 | 0 | Metadata |
| Caption | 12px | 650 | 1.45 | 0.04em | Labels |

### Font Stack

- Primary: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif
- Mono: "Cascadia Mono", "SFMono-Regular", Consolas, monospace

### Rules

- Keep Korean notes readable with generous line height.
- Body text never goes below 14px.
- Letter spacing is 0 except compact labels.

## 4. Spacing & Layout

### Base Unit

All spacing derives from 4px.

| Token | Value | Usage |
|-------|-------|-------|
| --space-1 | 4px | Tight inline gaps |
| --space-2 | 8px | Compact controls |
| --space-3 | 12px | Small card padding |
| --space-4 | 16px | Default gaps |
| --space-6 | 24px | Panel padding |
| --space-8 | 32px | Section inner spacing |
| --space-10 | 40px | Major card groups |
| --space-12 | 48px | Section breaks |
| --space-16 | 64px | Page rhythm |

### Grid

- Max content width: 1180px
- Column system: single column on mobile, 12-column grid on desktop
- Breakpoints: 640px, 768px, 1024px, 1280px

### Rules

- Use native CSS grid and details elements before adding JavaScript.
- Keep repeated session cards stable with consistent padding and headings.

## 5. Components

### Source Card
- **Structure**: label, title, metadata list, optional links
- **Variants**: default, warning
- **Spacing**: --space-4 and --space-6
- **States**: link hover, focus outline
- **Accessibility**: semantic headings, visible links
- **Motion**: none

### Session Note
- **Structure**: session number, title, speaker, key points, questions
- **Variants**: standard, reflection
- **Spacing**: --space-6 and --space-8
- **States**: details open/closed for long notes
- **Accessibility**: native details summary keyboard support
- **Motion**: none

## 6. Motion & Interaction

### Timing

| Type | Duration | Easing | Usage |
|------|----------|--------|-------|
| Micro | 120ms | ease-out | Link and details affordances |
| Standard | 220ms | ease-in-out | Focus outline changes |

### Rules

- Prefer no motion for reading surfaces.
- Every link has hover and focus states.
- Respect `prefers-reduced-motion`.

## 7. Depth & Surface

### Strategy

Borders-only.

| Type | Value | Usage |
|------|-------|-------|
| Default | 1px solid var(--border-default) | Cards and panels |
| Subtle | 1px solid var(--border-subtle) | Internal dividers |

