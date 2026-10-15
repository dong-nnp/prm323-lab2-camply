# Camply — Design System

Camply is a mobile campus-events experience for university students. Its design combines the energy of student life with the clarity of an editorial event guide: bold event photography, strong typographic hierarchy, quiet neutral surfaces, and a single confident blue action. The interface should feel youthful and welcoming without looking like a dashboard, gaming app, or generic AI-generated card collection.

**Platform:** Android-first mobile · **Reference frame:** 360 × 800 dp · **Theme:** Light · **Typeface:** Inter (Roboto/system fallback)

## Color Palette

| Role | Hex | Usage |
|---|---|---|
| **Primary** | `#2457F5` | Registration CTAs, active bottom navigation, selected controls, links |
| Primary Pressed | `#1745D5` | Pressed primary buttons |
| Primary Soft | `#EAF0FF` | Selected filter backgrounds, subtle active surfaces |
| **Accent** | `#C9F46A` | Small featured badges and highlights; pair with dark text |
| **Background** | `#F8F9FC` | Main app canvas |
| **Surface** | `#FFFFFF` | Cards, input surfaces, dialogs, navigation |
| Surface Muted | `#F1F3F8` | Quiet section backgrounds |
| **Text Primary** | `#171923` | Headings, event titles, body copy |
| Text Secondary | `#525866` | Dates, locations, supporting descriptions |
| Text Disabled | `#737987` | Disabled text only; check against its actual background |
| **Border** | `#DCE0E8` | Hairline separators, outlined fields |
| **Success** | `#18794E` | Confirmed registration, success messages |
| Success Surface | `#E7F5ED` | Positive status backgrounds |
| **Warning** | `#8A5700` | Warnings, limited availability |
| Warning Surface | `#FFF3D8` | Warning backgrounds |
| **Error** | `#B42336` | Validation errors, destructive actions |
| Error Surface | `#FDECEF` | Error backgrounds |

**Color usage:** Neutral surfaces should dominate. Reserve primary blue for navigation and meaningful actions. Lime is a small accent, never the main CTA. Pair blue buttons with white labels, lime badges with `#171923` labels, and semantic status colors with explicit text or icons. Do not place essential text directly on busy photography.

## Typography

**Font family:** Inter · **Weights:** 400 Regular / 500 Medium / 600 SemiBold / 700 Bold

| Style | Size / Line Height | Weight | Usage |
|---|---|---|---|
| Display | 28 / 36 sp | 700 | Occasional hero statement |
| Headline | 24 / 32 sp | 700 | Screen titles |
| Subhead | 20 / 28 sp | 700 | Section headings |
| Title | 16 / 24 sp | 600 | Event-card titles |
| Body Large | 16 / 24 sp | 400 | Descriptions, forms |
| Body | 14 / 20 sp | 400 | Event metadata, secondary copy |
| Label | 14 / 20 sp | 500 | Input labels, chips, navigation |
| Button | 16 / 24 sp | 600 | Primary and secondary actions |

Use sentence case, natural line wrapping, and generous line height. Keep readable body copy at **14sp minimum**. Event-card titles may be limited to two lines; full titles on Event Detail must be allowed to wrap. Support system text scaling without clipping.

## Corner Radius

| Token | Value | Usage |
|---|---:|---|
| None | 0 dp | Dividers, flat section edges |
| Small | 8 dp | Badges, compact image corners |
| Medium | 12 dp | Buttons, text fields, thumbnails |
| Large | 16 dp | Event cards, featured imagery |
| Extra Large | 20 dp | Dialogs, bottom-sheet top corners |
| Pill | 999 dp | Filter chips and circular indicators only |

Use one radius consistently per component family. Avoid pill-shaped everything and nested rounded panels.

## Spacing

**Base unit:** 4 dp · **Scale:** 4 / 8 / 12 / 16 / 24 / 32 / 40 / 48 dp

| Spacing | Usage |
|---|---|
| 4 dp | Icon-label micro gaps |
| 8 dp | Related text and controls |
| 12 dp | Internal card content gaps |
| 16 dp | Screen gutters, card padding |
| 24 dp | Section separation |
| 32 dp | Major layout breathing room |
| 40 dp | Hero separation when needed |
| 48 dp | Large intentional section breaks |

**Layout:** 16dp horizontal gutters on standard screens; a single-column, scrollable layout; 24dp between major sections. Featured photography favors 16:9; list thumbnails use consistent 1:1 or 4:3 crops within the same card type. Respect safe areas, keyboard overlap, bottom navigation, and sticky CTAs. Verify at 360dp and 412dp widths; preserve flexible content at wider sizes.

## Components

### Buttons

| Variant | Appearance | States |
|---|---|---|
| Primary | `#2457F5` fill, white 16sp semibold label, 12dp radius, min 48dp height | Default / Pressed `#1745D5` / Disabled / Loading |
| Secondary | White or transparent fill, blue label, 1dp visible outline, 12dp radius, min 48dp height | Default / Pressed / Disabled |
| Tertiary | Text-only, blue or neutral label, min 48 × 48dp hit area | Default / Pressed / Disabled |
| Destructive | Error-colored action, explicit destructive label | Default / Pressed / Disabled |

One dominant primary CTA per decision area. Loading replaces or accompanies the label with progress feedback and blocks repeat submission. Disabled controls must remain recognizable without relying solely on color.

### Cards

**Featured Event:** large photo, event title, concise date and venue, clear path to Event Detail. Use editorial imagery rather than multiple stacked colored containers.

**Event List Card:** consistent thumbnail, title, date/time, venue, optional category/status and a separate bookmark target. The card opens Event Detail; tapping the bookmark only changes saved state. Use either a 1dp subtle border or a soft shadow, not both prominently.

**States:** Default / Pressed / Saved / Registered where relevant. Keep the hierarchy **image → title → date/time → venue → status**.

**Date Badge:** A compact month-and-day badge may overlay large featured event imagery. Use a solid, high-contrast surface and legible text. Do not place date badges on small list thumbnails; display dates as regular metadata there.

### Inputs

**Text Field:** persistent 14sp label above the field; 12dp corners; 1dp border; min 48dp control height. Placeholder text supplements, never replaces, the label.

**States:** Default (neutral border) / Focused (primary blue border) / Filled / Error (red border plus explanatory text) / Disabled. Preserve typed values after a validation error. Indicate required and optional fields in words.

**Search Field:** leading search icon, clear input affordance, optional clear-text action. Use on Explore, not Discover.

### Chips & Filters

**Category Badge:** Use the same lime fill (`#C9F46A`) and dark label (`#171923`) for informational event category badges across all event types. Do not assign a different badge color to each category. Keep badges compact and readable. Category badges are informational, not interactive filter controls.

Compact category/date/location controls with readable 14sp labels and at least 48dp interactive height. Selected uses primary or primary-soft background with a visible indicator; unselected uses neutral surface and border. Provide **Clear filters** for no-results recovery.

**States:** Default / Selected / Pressed / Disabled.

### Navigation

**Bottom Navigation:** four destinations only — **Discover / Explore / My Events / Profile**. Each item has an icon and label; active uses primary blue, inactive uses secondary text. Keep tap targets at least 48 × 48dp. Secondary screens use a clear Back action; do not introduce extra bottom tabs for Saved Events or Notifications.

**App Bar:** stable Back/title/action placement, concise screen titles, 48 × 48dp icon targets. The Discover screen emphasizes featured content and category shortcuts rather than a full search field.

### Dialogs

Use a 20dp radius, white surface, dimmed backdrop, clear title and explanation. A destructive confirmation (such as canceling event registration) names the affected event and separates **Keep Registration** from **Cancel Registration**. Dismissing the dialog leaves data unchanged.

**Variants:** Confirmation / Destructive / Error.

### Feedback States

| State | Visual treatment | Required communication |
|---|---|---|
| Loading | Spinner or progress treatment | Short status text; prevent duplicate submission |
| Empty | Quiet illustration/icon and generous spacing | Explain absence and offer a next action |
| Error | Error icon/color and concise text | Explain problem and provide recovery |
| Success | Success icon and calm positive treatment | Confirm outcome and present next step |
| Snackbar | Temporary message on a high-contrast surface above bottom navigation/safe area | Confirm a completed action; offer Undo only when reversible |

**Snackbar behavior:** Keep messages brief and positioned clearly above the bottom navigation. For committed actions like event registration cancellation (after explicit confirmation in T01), do not display an Undo button on the snackbar so the UI does not promise a rollback that the backend slot system cannot guarantee.

**Success celebration:** A few small, nonessential confetti dots may decorate a dedicated success screen. They must not obscure text, controls, or the confirmation message. Avoid full-screen confetti and distracting animation.

A successful registration should visibly progress from **loading → confirmation → View Ticket**. A simulated ticket QR must be identified as a UI demonstration, with readable event and ticket information.

## Elevation & Depth

| Level | Specification | Usage |
|---|---|---|
| Flat | No shadow | Buttons, chips, lists, most cards |
| Subtle | `0 2px 8px rgba(23,25,35,0.06)` | Optional floating card |
| Medium | `0 8px 24px rgba(23,25,35,0.12)` | Dialog, bottom sheet |
| Overlay | Dark translucent backdrop | Modal separation from underlying content |

Prefer whitespace, alignment and dividers over elevation. Do not stack shadows or nest elevated cards. Shadow measurements are visual references for design tools.

## Photography & Iconography

Use authentic-looking campus concerts, workshops, sports, art and student-life photography. Maintain consistent crop ratios and natural color. Different event types should not reuse an identical hero image. Keep event information legible outside imagery when possible.

Use a single consistent outline icon family (such as Lucide) with matching stroke weight. Icons support labels; they do not replace critical navigation or status text. Avoid 3D icons, ornamental gradients and unrelated illustrations.

## Motion & Interaction

Use restrained 150–250ms transitions for taps, selection and overlays. Provide visible pressed feedback, clear focus and form errors, and explicit loading/success states. Motion must not be the only way to convey status. Back navigation should return users to a logical prior screen and preserve search/filter context where practical.

## Accessibility

- Normal text contrast **≥ 4.5:1**; large text and meaningful UI graphics **≥ 3:1**. Verify actual foreground/background combinations.
- Interactive targets **≥ 48 × 48dp**, including bookmarks, bell icons, Back controls and bottom tabs.
- Body text **≥ 14sp**; allow text scaling and wrapping.
- Do not communicate error, selection or registration status through color alone.
- Forms need persistent labels, helpful inline errors and keyboard-aware spacing.
- Test at **360dp** and **412dp** widths; ensure content is not hidden by system UI.

## Do's & Don'ts

### Do

- Let event photography and clear titles create personality.
- Give event title, date, venue and registration status an obvious hierarchy.
- Keep backgrounds light, with consistent 16dp gutters and generous whitespace.
- Reserve primary blue for the clearest actions and active navigation.
- Use lime consistently for small informational category badges; use other accents sparingly.
- Use consistent component states, event data and imagery across the experience.
- Offer understandable empty, loading, error and success feedback.

### Don't

- Fill entire screens with bright blue or lime panels.
- Build cards inside cards or apply thick shadows to every surface.
- Use tiny metadata, low-contrast labels or text over busy images.
- Make every action equally prominent or add multiple competing CTAs.
- Turn the Discover screen into a duplicate of Explore with a full search bar.
- Add decorative 3D icons, glassmorphism, unnecessary gradients or full-screen confetti; only subtle dots on a dedicated success screen are allowed.
- Hide recovery actions or create dead-end interaction states.
- Introduce extra bottom tabs or inconsistent navigation patterns.