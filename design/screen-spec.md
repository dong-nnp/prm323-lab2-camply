# Camply — Screen Specification

**Status:** Handoff specification based on `design/DESIGN.md`, the presentation deck, and the supplied Stitch export.  
**Platform:** Android-first mobile · **Reference frame:** 360 × 800 dp · **Theme:** Light · **Typeface:** Inter (Roboto/system fallback)

## 1. Rules that apply to every screen

- Use `design/DESIGN.md` as the source of truth for color, type, spacing, radius, elevation, iconography and accessibility.
- Standard screen gutter: 16 dp; 4 dp spacing scale; body text at least 14 sp; touch targets at least 48 × 48 dp.
- High-level destinations have the Camply brand/app shell and the four-tab bottom navigation: **Discover / Explore / My Events / Profile**. The active tab must match the destination.
- Nested screens use a stable Back control and concise title; do not repeat the full brand header or bottom navigation on registration/detail subflows where it would compete with the task.
- Cards use a single subtle border OR a restrained shadow, not both prominently. No nested cards or extra bottom tabs.
- Use the same event name/date/time/venue across Discover, Explore and Event Detail (`Campus Music Night — October 26, 2026 • 18:00–22:00 — Main Stadium`). Sample event content is treated as prototype data.
- Every state must communicate its meaning with text/icon as well as color. Preserve form values after validation errors.
- Keep content scrollable and clear of status/navigation system areas. Test 360 dp and 412 dp widths; 600 dp+ behavior is documented in `handoff/flutter-handoff.md`.

## 2. Screen inventory

| ID | Screen | Level / shell | Main purpose |
|---|---|---|---|
| **S01** | Discover / Home | Top-level; Discover tab | Find featured and upcoming campus events |
| **S02** | Explore Events | Top-level; Explore tab | Search, filter and scan event results |
| **S03** | Event Detail | Nested | Understand one event and start registration |
| **S04** | Event Registration | Nested | Confirm identity and submit registration |
| **S05** | Registration Success | Nested result | Confirm registration and continue to ticket |
| **S06** | My Events | Top-level; My Events tab | Review upcoming/past registrations and manage them |
| **S07** | My Ticket | Nested | Show event and ticket information at entry |
| **S08** | Saved Events | Nested destination from Profile / save action | Revisit bookmarked events |
| **S09** | Notifications | Nested destination from notification action | Review updates and unread status |
| **S10** | Student Profile | Top-level; Profile tab | Review student identity and account destinations |
| **T01** | Cancel Registration Dialog | Overlay on S06 | Confirm a consequential cancellation |
| **T02** | Registration Validation Error | S04 error state | Correct invalid required data |
| **T03** | Registration Loading | S04 in progress | Prevent duplicate submission while waiting |
| **T04** | Saved Events Empty | S08 empty state | Explain no saved events and recover to Explore |
| **T05** | Notifications Empty | S09 empty state | Explain there are no notifications |
| **T06** | Explore No Results | S02 empty result state | Recover from search/filter combination with no matches |
| **T07** | My Events Cancellation Confirmed (no Undo) | S06 snackbar state | Confirm a committed cancellation; no Undo control |

## 3. Screen specifications

### S01 — Discover / Home
- **Goal:** Let a student discover an event quickly without turning Home into a search page.
- **Layout:** Compact brand header with greeting, notification icon and avatar; welcome heading “What's happening on campus?”; featured event “Campus Music Night”; four category shortcuts (Music, Workshop, Sports, Arts); compact upcoming event previews; fixed bottom navigation with Discover active.
- **Content hierarchy:** Featured image → event title → date/time → venue → action. Upcoming previews use consistent sample event details.
- **Actions:** Featured event/card → S03; category shortcut and “See all” → S02 with relevant category where supported; notification → S09; bottom tabs → S02/S06/S10.
- **States:** Default; loading/placeholder only if event data is actually loading.
- **Constraints:** No full-width search field on Discover; avoid oversized hero that pushes categories/upcoming content below the fold; bottom content must scroll above navigation.
- **Reference:** `assets/stitch/s01_discover_home.png`.

### S02 — Explore Events
- **Goal:** Search and filter events with quick scanning.
- **Layout:** Title; full-width labeled search field; compact category/date/location filters consistent with `DESIGN.md`; clearable selected-filter indicators; vertically scrolling event list; Explore active in bottom navigation.
- **Event row:** Consistent thumbnail crop; title; date/time; venue; optional compact category badge; bookmark target separate from card tap.
- **Actions:** Typing filters results; clear search resets query; filter selection updates results; event card → S03; bookmark toggles saved state only; Discover/My Events/Profile tabs navigate to their top-level destinations.
- **States:** Default results; T06 no results; T08 idle-search state.
- **Constraints:** No subtitle that repeats the title; no competing “Details” link if the entire row is tappable; maintain 48 dp targets.
- **Reference:** `assets/stitch/s02_explore_events.png`, `assets/stitch/t06_explore_no_results.png`, `assets/stitch/t08_explore_idle_search.png`.

### S03 — Event Detail
- **Goal:** Give enough information to decide whether to register.
- **Layout:** Back + title/app-bar action; event hero image; event title; date/time and venue as readable metadata; concise description; key practical information; primary Register CTA.
- **Actions:** Back returns to the originating screen and preserves Explore query/filter context where practical; Register → S04; save/bookmark toggles saved state without navigating away; venue/schedule sections reveal only information supported by the event data.
- **States:** Default; saved/unsaved.
- **Constraints:** Full title wraps; metadata ≥14 sp; primary CTA stays visible in a clear sticky area without covering content.
- **Reference:** `assets/stitch/s03_event_detail.png`.

### S04 — Event Registration
- **Goal:** Submit a registration without retyping information already available in the student profile.
- **Layout:** Back + “Event Registration”; compact event summary; persistent labels for required fields; prefilled name (`Alex Morgan`), student ID (`STU-849201`) and email (`alex.m@university.edu`) when profile data exists; optional phone field; primary Confirm Registration action.
- **Actions:** Confirm validates fields, then transitions to T03 while submission is pending; success → S05; invalid fields → T02; system/network failure → an explicit retryable error.
- **States:** Default/filled, focused, validation error (T02), loading (T03), submission failure, disabled while invalid or submitting.
- **Constraints:** Do not show bottom navigation during the focused registration task; Back returns to S03; preserve entered values after errors; Back target ≥48 dp; mark required and optional fields in words.
- **Reference:** `assets/stitch/s04_event_registration.png`.

### S05 — Registration Success
- **Goal:** Clearly confirm the outcome and provide the next useful action.
- **Layout:** Success icon; explicit “You're Registered!” message; event name/date/venue summary with Confirmed status; primary View My Digital Ticket action; secondary Back to Discover action.
- **Actions:** View My Digital Ticket → S07; Back to Discover → S01.
- **States:** Success only after a successful registration result.
- **Constraints:** Keep confirmation text dominant; restrained decorative celebration only; secondary button uses primary blue outline and label per `DESIGN.md`.
- **Reference:** `assets/stitch/s05_registration_success.png`.

### S06 — My Events
- **Goal:** Review registrations and access ticket/cancellation actions.
- **Layout:** Top-level title; clear Upcoming / Past tabs; registered-event rows with event identity, date/time, venue and explicit `● Registered` status; My Events active in bottom navigation.
- **Actions:** View Ticket → S07; Cancel opens T01 confirmation dialog; after confirmed cancellation in T01, transition to T07 (committed cancellation state without Undo); tabs navigate to top-level destinations.
- **States:** Populated upcoming/past; T01 cancel confirmation overlay; T07 cancellation confirmed state.
- **Constraints:** Do not make a destructive action the dominant row action; avoid color-only status.
- **Reference:** `assets/stitch/s06_my_events.png`.

### S07 — My Ticket
- **Goal:** Make ticket and event details easy to find at check-in.
- **Layout:** Back + “My Ticket”; event title and venue/date/time; registrant identity (`Alex Morgan`, `STU-849201`); pass type (`General Admission`) and ticket number (`CMN-2026-0849`); simulated QR code area with explicit demo label.
- **Actions:** Back returns to the prior ticket context (S05 or S06).
- **States:** Valid/confirmed.
- **Constraints:** Keep important information readable outdoors; identify the QR code as a UI demonstration (`Demonstration pass`); do not style non-interactive pass type text as a blue link.
- **Reference:** `assets/stitch/s07_digital_ticket.png`.

### S08 — Saved Events
- **Goal:** Revisit bookmarked events.
- **Layout:** Nested title with Back and saved count (`3 saved`); saved event list using the same horizontal row component as S02; each row retains title/date/time/venue and active bookmark control; secondary `Explore More Events` action.
- **Actions:** Event row → S03; bookmark removes the event from Saved; removing the last item transitions to T04; Explore More Events → S02.
- **States:** Populated; T04 empty.
- **Constraints:** Saved Events is not a fifth bottom tab; preserve a clear route back to the source screen.
- **Reference:** `assets/stitch/s08_saved_events.png`, `assets/stitch/t04_saved_events_empty_state.png`.

### S09 — Notifications
- **Goal:** Review event updates and registration-related messages.
- **Layout:** Nested title with Back and `Mark all read` action; chronological notification rows grouped under `Today` (`2 new`) and `This Week`; unread indicator with explicit `NEW` text label plus blue dot; concise title/body/time.
- **Actions:** Opening a notification marks it read and navigates to the related destination; `Mark all read` clears unread badges; Back returns to prior screen; T05 offers a route to Explore.
- **States:** Read/unread; T05 empty.
- **Constraints:** “2 new” must equal the number of rows actually marked unread with `NEW` labels; never rely on a dot/color alone.
- **Reference:** `assets/stitch/s09_notifications.png`, `assets/stitch/t05_notifications_empty_state.png`.

### S10 — Student Profile
- **Goal:** Show student identity and provide account-related destinations.
- **Layout:** Top-level Profile header; avatar; student name (`Alex Morgan`), student ID (`STU-849201`) and email (`alex.m@university.edu`); `Edit Profile` button; grouped destinations under `Your Activity` (My Events, Saved Events, Notifications) and `Settings & Support` (App Settings, Help & Support); Profile active in bottom navigation.
- **Actions:** My Events → S06; Saved Events → S08; Notifications → S09; profile/support rows open their respective prototype targets.
- **States:** Complete profile.
- **Constraints:** Do not repeat a full profile header on every nested screen; maintain readable labels and ≥48 dp touch targets.
- **Reference:** `assets/stitch/s10_student_profile.png`.

## 4. State specifications

### T01 — Cancel Registration Dialog
- **Presentation:** Modal overlay over S06 with dimmed backdrop covering the entire viewport including bottom navigation; title explicitly names cancellation (`Cancel Registration?`); event context (`Campus Music Night`) is clear.
- **Actions:** “Keep Registration” closes the dialog without changing data; “Cancel Registration” commits cancellation and transitions to T07.
- **Safety:** Dismiss/backdrop/back leaves data unchanged.
- **Reference:** `assets/stitch/t01_cancel_registration_dialog.png`.

### T02 — Registration Validation Error
- **Presentation:** S04 remains visible; invalid fields have red error border (`#B42336`), warning icon and explanatory inline text below each field.
- **Behavior:** Keep user-entered values (such as `alex@gmail.com`); focus or scroll to first invalid field; clear the error when the field becomes valid.
- **Recovery:** Correct input → Confirm Registration → T03.
- **Reference:** `assets/stitch/t02_registration_form_validation_error.png`.

### T03 — Registration Loading
- **Presentation:** S04 remains contextual under a dimmed overlay with a centered loading dialog (`Confirming your registration... Please wait a moment.`); Confirm Registration button becomes disabled (`Confirming...`).
- **Behavior:** Prevent duplicate submission; preserve input; transition to S05 on success, or display a slow-network retry/exit option on timeout.
- **Reference:** `assets/stitch/t03_registration_loading_state.png`.

### T04 — Saved Events Empty
- **Presentation:** Quiet bookmark icon, heading “No Saved Events Yet”, one short explanation and one primary action “Explore Events”.
- **Action:** Explore Events → S02.
- **Reference:** `assets/stitch/t04_saved_events_empty_state.png`.

### T05 — Notifications Empty
- **Presentation:** Quiet bell icon; heading “You're All Caught Up!”; short message “No notifications yet. Updates about your campus events will appear here.”; primary action “Explore Events”.
- **Action:** Back or Explore Events → S02.
- **Reference:** `assets/stitch/t05_notifications_empty_state.png`.

### T06 — Explore No Results
- **Presentation:** Keep query (`Robotics Hackathon`) and selected category filter (`Workshop`) visible; clear message “No Events Found”; primary action “Clear Filters” and secondary action “Try Another Search”.
- **Behavior:** Clear Filters resets the query/filter state and returns to S02 results.
- **Reference:** `assets/stitch/t06_explore_no_results.png`.

### T07 — Cancellation Confirmed (no Undo)
- **Presentation:** After the user confirms cancellation in T01, S06 updates the registration list/status and displays a brief “Registration cancelled.” confirmation snackbar above the bottom navigation. **Do not show an Undo button** or imply that the committed cancellation can be reversed from the snackbar.
- **Next step:** If other upcoming events remain (e.g., *AI & Future Careers Workshop*), show the updated list (`Upcoming 1`); if no upcoming events remain, show the empty state (`No Upcoming Events`) with an `Explore Events` button leading to S02. Offer “Register again” on the event detail screen only if the event is still open.
- **Rationale:** Cancellation is treated as committed after the user explicitly confirms in T01 (Decision D07), avoiding a rollback promise the system may not support.
- **Reference:** `assets/stitch/t07_my_events_cancellation_with_undo_snackbar.png` (legacy Stitch exploration; the final Figma screen removes the Undo action per Decision D07).

## 5. Interaction and navigation matrix

| From | Action | To / result |
|---|---|---|
| S01 | Featured event | S03 |
| S01 | Category / See all | S02, with category selected when supported |
| S01 | Notification icon | S09 |
| Bottom nav | Discover / Explore / My Events / Profile | S01 / S02 / S06 / S10 |
| S02 | Event row | S03 |
| S02 | Bookmark | Toggle saved state; stay on current screen |
| S03 | Register Now | S04 |
| S04 | Invalid Confirm | T02 |
| S04 | Valid Confirm | T03 → S05 on success |
| S04 | Submission failure / timeout | Recoverable error; retry without losing data |
| S05 | View My Digital Ticket | S07 |
| S05 | Back to Discover | S01 |
| S06 | View Ticket | S07 |
| S06 | Cancel | T01 |
| T01 | Keep Registration / dismiss | S06 unchanged |
| T01 | Confirm cancellation | S06 updated + T07 confirmation (no Undo) |
| T07 | Continue / dismiss confirmation | S06 remains updated; Explore Events → S02 |
| S08 | Event row | S03 |
| S08 | Remove bookmark | Remove row; show T04 if last item |
| S09 | Related notification | Valid related destination; mark read |
| S10 | My Events / Saved Events / Notifications | S06 / S08 / S09 |

## 6. Acceptance checklist

- [x] Ten distinct final screens S01–S10 are present in Figma page 03.
- [x] T01–T07 are positioned beside their parent screens and visually implemented.
- [x] Four bottom tabs and active icon treatment are consistent.
- [x] Event title/date/time/venue match across S01/S02/S03.
- [x] Every interactive control has a defined action and visible state.
- [x] Loading does not permit duplicate submission; errors preserve form data.
- [x] Cancellation is committed and no Undo is offered on T07 (Decision D07).
- [x] Text ≥14 sp, touch targets ≥48 dp, contrast checked with actual token values.
- [x] Layout checked at 360 dp and 412 dp; keyboard and safe areas do not obscure content.
- [x] Prototype flows have explicit start points and no dead ends.