# Camply — Bản ghi phản biện bằng AI

> **Trạng thái:** Đã có kết quả từ một phiên Claude 3.5 Sonnet mới, ngày 16/10/2026. Phần 2 và phần 3 dưới đây là nguyên văn prompt và câu trả lời. Không sửa nội dung trong các phần này.

## 1. Thông tin phiên chạy

| Mục | Điền |
|---|---|
| Ngày chạy | 16/10/2026 |
| Công cụ AI | Claude 3.5 Sonnet (Anthropic) |
| Cuộc trò chuyện | Mới, không dùng lại phiên thiết kế |
| Tệp đính kèm | Ảnh màn hình Stitch (`assets/stitch/`); `persona.md`; `DESIGN.md` |
| Ảnh chụp đầu vào | S01–S10, T01, T03, T04, T06, T07, T08 (T02 và T05 không đính kèm, theo prompt) |
| Bản ghi phiên chat | Lưu nguyên văn tại Mục 3 bên dưới và `ai/critique-response-claude.md` |

> **Ghi chú xác nhận Persona:** Prompt dưới đây ghi tên gọi tắt "persona Linh", trong khi `ux/persona.md` của nhóm có Primary Persona là **Persona 1 — Nguyễn Minh Anh**. Toàn bộ các đặc điểm bối cảnh trong prompt (sinh viên năm 2, dùng ứng dụng bằng một tay giữa các tiết học, đọc màn hình ngoài trời nắng, mạng chập chờn) đều trích xuất từ Persona 1 Nguyễn Minh Anh.

## 2. Prompt đã dùng (nguyên văn)

```
You are a senior mobile UI/UX designer reviewing Camply, a campus event discovery and registration app for university students. The attached files are: screen images S01–S10 and T01, T03, T04, T06, T07, T08; DESIGN.md (design tokens); persona.md (persona Linh).
Note: screens T02 (registration validation error) and T05 (notifications empty state) are NOT attached. Do not review them and do not assume their content.
Review the attached screens against:

1. Nielsen's 10 usability heuristics. Name each heuristic you cite (for example "H4 Consistency and standards").
2. Basic mobile accessibility: text contrast at least 4.5:1 for normal text, touch targets at least 48 × 48 dp, body text at least 14 sp, and status must not rely on colour alone.
3. The persona: a second-year student who uses the app one-handed between classes, reads the screen outdoors, and often has an unstable network.

Output rules:

* List every finding you can support from the images. Do not invent findings to reach a number. If you find fewer than 5, say so.
* For each finding, use this format:
   * Screen: (code, e.g. S04)
   * Issue: what you see in the image
   * Heuristic or criterion: (name it)
   * Persona impact: how it affects Linh
   * Priority: High / Medium / Low
   * Recommendation: a concrete change, without adding new features
   * Verification: "Observed in image" or "Needs Figma check" (for example exact sizes, sp values, hex colours, layout at 412 dp)
* Do not give numeric contrast ratios, sizes, or hex values unless they are printed in DESIGN.md or visible in the image. Mark anything else as "needs Figma check".
* Finish with a short list of what works well and should be kept.
* Do not redesign the product or propose new features.
```

## 3. Câu trả lời của AI (nguyên văn)

# Camply UX Review: Nielsen Heuristics, Accessibility and Persona Fit

Review of the Camply campus event app screens against Nielsen's 10 heuristics, basic mobile accessibility, and the persona Linh (second-year student, one-handed use between classes, outdoor reading, unstable network).

## Scope and limits

- **S03 (Event Detail) could not be reviewed.** All three S03 image files in the zip are corrupt: each contains only the text "Image failed to fetch". Nothing was inferred from the HTML. This also means the "≤5 taps from Discover to registration" criterion can't be checked, because the step between S01's Details button and S04 is missing. Re-export S03 to complete the review.
- **Screens reviewed:** S01, S02, S04 to S10, T01, T03, T04, T06, T07 and T08. Where the zip has several versions, the latest was used (S09 v4, T04 v2, S05 v4, S06 v3, and so on).
- **Excluded:** T02, T05 (notifications empty state) and T09, as instructed or because they were not on the list.
- **Numbers:** DESIGN.md prints no contrast ratios, so none appear here. Exact sizes, sp values and hit areas are marked "Needs Figma check".

There are 22 findings that the images support, grouped by priority. The first four are trust issues that matter most for this persona.

## High priority

### 1. Screen T07: no Undo on the cancellation snackbar

- **Issue:** After cancelling, the snackbar reads only "Registration cancelled." with no Undo action.
- **Heuristic:** H3 User control and freedom; H9 Help users recover from errors.
- **Persona impact:** Scenario 2 and DESIGN.md both promise Undo. A one-handed tap in a rush could cost Linh her spot with no way back.
- **Priority:** High
- **Recommendation:** Add an Undo action to the snackbar, per DESIGN.md ("offer Undo only when reversible"). It should stay up long enough to read and tap.
- **Verification:** Observed in image (the action is absent). Duration: needs Figma check.

### 2. Screen T07 (vs S06): registration count contradicts the earlier screen

- **Issue:** T07 shows "Upcoming 0" and an empty state. S06 showed two upcoming registrations, and the dialog in T01 cancels only one. The AI & Future Careers Workshop should still be registered.
- **Heuristic:** H4 Consistency and standards; H1 Visibility of system status.
- **Persona impact:** Linh would think she lost both registrations.
- **Priority:** High
- **Recommendation:** Make the count and list reflect the remaining registration (Upcoming 1, with the Workshop card). Keep the empty state for when none remain.
- **Verification:** Observed in image (assuming T07 follows S06 in one flow).

### 3. Screen S07 (vs S04, S10): ticket identity does not match the profile

- **Issue:** The ticket shows Attendee "Nguyen Van A" and Student ID "SE123456". The registration form and profile show "Alex Morgan" and "STU-849201".
- **Heuristic:** H4 Consistency and standards; H1 Visibility of system status.
- **Persona impact:** The ticket is what Linh shows at the gate. A name that doesn't match her ID undermines the peace-of-mind goal.
- **Priority:** High
- **Recommendation:** Populate the ticket from the same profile data as S04 and S10.
- **Verification:** Observed in image.

### 4. Screens S01, S02, S04 to S08, T08: the same events show different details

- **Issue:** Event details differ across screens.
  - Campus Music Night: Fri Oct 26 (S01) and Fri Oct 28 (S02), versus Oct 26 18:00–22:00 (S04 to S08).
  - Campus Music Night venue: Student Union Amphitheater (S01, S02) versus Main Stadium (S04 to S08).
  - AI & Future Careers Workshop: Tue Nov 2, 4:00 PM, Science Hall 301 (S01, S02) versus Nov 2, 09:00–12:00, Innovation Hub · Hall A (S06, S08).
  - The weekday for Nov 2 is Tue in S01/S02 but Mon in T08.
  - Time format switches between 12-hour and 24-hour.
- **Heuristic:** H4 Consistency and standards.
- **Persona impact:** Linh commits from the list screens and could go to the wrong place or time. This is the most serious trust risk.
- **Priority:** High
- **Recommendation:** Use one data record per event and one date/time format throughout (for example "Mon, Oct 26 · 18:00"). Keep the venue name identical on every screen.
- **Verification:** Observed in image.

## Medium priority

### 5. Screen S02: serif typeface

- **Issue:** Titles, labels and metadata render in a serif face, while the other screens use a sans-serif. DESIGN.md specifies Inter.
- **Heuristic:** H4 Consistency and standards.
- **Persona impact:** Serif text reads thinner outdoors, and the screen looks like a different app.
- **Priority:** Medium
- **Recommendation:** Apply the Inter text style to S02, as in T08.
- **Verification:** Observed in image. Exact weights: needs Figma check.

### 6. Screens T06, T07: broken logo placeholder

- **Issue:** The app bar shows a grey placeholder box labelled "img" where the logo should be.
- **Heuristic:** H8 Aesthetic and minimalist design; H4 Consistency and standards.
- **Persona impact:** The app looks unfinished and less trustworthy at the moment Linh needs reassurance.
- **Priority:** Medium
- **Recommendation:** Replace the placeholder with the logo or remove it. Use one app-bar pattern for each tab (S02 and T08 have no app bar, while T06 and T07 do).
- **Verification:** Observed in image.

### 7. Screen T03: loading state has no exit or slow-network message

- **Issue:** The loading modal says "Confirming your registration… Please wait a moment." It has a spinner plus separate dots, and shows no timeout message or way out.
- **Heuristic:** H1 Visibility of system status; H9 Help users recover from errors.
- **Persona impact:** The Wi-Fi in the persona's context is unstable. Linh could be stuck on a screen with no sign of whether to wait or retry.
- **Priority:** Medium
- **Recommendation:** Keep one progress indicator. After a delay, change the text to a slow-connection message with a Retry or Back option, so the screen is never a dead end. This reuses the error state and adds no feature.
- **Verification:** Observed in image. Delay length: needs Figma check.

### 8. Screen S01: essential text on a busy photo

- **Issue:** On the featured card, the title, date, venue, Details button and bookmark sit directly on a busy concert photo.
- **Heuristic:** Accessibility: text contrast ≥ 4.5:1; H8 Aesthetic and minimalist design. DESIGN.md says "Do not place essential text directly on busy photography."
- **Persona impact:** Linh reads outdoors in glare, and busy imagery lowers legibility.
- **Priority:** Medium
- **Recommendation:** Put the date and venue on a solid surface below the image (as in the list cards), or use a stronger solid scrim behind the text.
- **Verification:** Visible in image. Actual contrast ratio: needs Figma check.

### 9. Screens S01, S08: truncated date and venue lines

- **Issue:** The date and venue lines are cut off with an ellipsis ("Tue, Nov 2 • 4:00 …", "East Campus Athle…", "Oct 26, 2026 • 18:00 –…").
- **Heuristic:** H6 Recognition rather than recall.
- **Persona impact:** The end time and venue are what Linh decides on. Truncation hides them in the lists she scans.
- **Priority:** Medium
- **Recommendation:** Let metadata wrap to a second line, or shorten the format (for example "Tue, Nov 2 · 16:00"). DESIGN.md allows title truncation only. Check at larger system text sizes.
- **Verification:** Observed in image. Behaviour at 412 dp and with scaled text: needs Figma check.

### 10. Screens S02, S06, S10, T01, T06, T08: unstable bottom-nav icons

- **Issue:** The bottom-navigation icons are not stable.
  - Explore uses a shapes icon in S02, S06, T01 and T06.
  - Explore uses a map icon in S10.
  - Explore uses a compass in T08, which is the same icon as Discover.
- **Heuristic:** H4 Consistency and standards; H6 Recognition rather than recall.
- **Persona impact:** Linh navigates one-handed and quickly. Changing or duplicate icons slow her down.
- **Priority:** Medium
- **Recommendation:** Pick one distinct icon per tab from the same outline family and use it on every screen.
- **Verification:** Observed in image.

### 11. Screen S07: no demo label on the QR

- **Issue:** No visible label says the QR is a UI demonstration.
- **Heuristic:** H1 Visibility of system status; DESIGN.md requirement ("A simulated ticket QR must be identified as a UI demonstration").
- **Persona impact:** Linh could think the ticket is real. This is also a spec gap.
- **Priority:** Medium
- **Recommendation:** Add a short "Demo QR" line near the code or in the info note.
- **Verification:** Observed in image (the label is absent from the image).

### 12. Screen S06: Cancel placed beside View Ticket

- **Issue:** Cancel (red outline) sits right next to View Ticket in the same row on both cards.
- **Heuristic:** H5 Error prevention.
- **Persona impact:** A one-handed thumb tap could hit Cancel by accident. The T01 dialog catches it, which helps.
- **Priority:** Medium
- **Recommendation:** Keep the confirmation dialog. Reduce Cancel's visual weight (tertiary text style) or separate it from View Ticket. Keep View Ticket as the single dominant action.
- **Verification:** Observed in image. Gap and hit sizes: needs Figma check.

### 13. Screens S01, S02, T06, T08: touch targets that look small

- **Issue:** Several controls look shorter than the bottom-nav items. These are the filter chips and dropdown buttons (Any time, On campus, Sort), the bookmark icons, the recent-search X icons and the small "Clear", "See all" and "Mark all read" links.
- **Heuristic:** Accessibility: touch targets ≥ 48 × 48 dp.
- **Persona impact:** Small targets are harder to hit one-handed while walking.
- **Priority:** Medium
- **Recommendation:** Confirm every target is at least 48 × 48 dp. Enlarge the hit area without changing the icon size.
- **Verification:** Needs Figma check (hit areas are not visible in a flat image).

### 14. Screens T06, T07: lime badges used for non-category labels

- **Issue:** Lime badges are used for "FALL '24" (T06) and "STUDENT ID" (T07). "FALL '24" is also a stale year next to 2026 dates. "STUDENT ID" has no clear meaning on My Events.
- **Heuristic:** H4 Consistency and standards; H2 Match between system and real world.
- **Persona impact:** Lime means "category" everywhere else, so these two badges mislead.
- **Priority:** Medium
- **Recommendation:** Remove both badges or give them a neutral style. If the term label stays, correct the year.
- **Verification:** Observed in image.

### 15. Screens S02, T08 (vs T06): selected chip shown by colour alone

- **Issue:** The selected "All" chip is marked by blue fill alone in S02 (a grid icon in T08). T06 adds a check mark to the selected chip, and other chips have none.
- **Heuristic:** Accessibility: status must not rely on colour alone; H4 Consistency and standards.
- **Persona impact:** In bright sun, fill colour alone is easy to miss.
- **Priority:** Medium
- **Recommendation:** Use the T06 pattern (check mark plus fill) for the selected chip on all Explore screens.
- **Verification:** Observed in image.

## Low priority

### 16. Screen T01: dialog context

- **Issue:** The dialog has three problems.
  - The backdrop does not dim the bottom navigation, so it looks tappable.
  - The background behind the dialog is a different My Events layout from S06 (large-photo cards, a calendar icon at top right, a chevron on Past).
  - The destructive button says "Yes, Cancel", while DESIGN.md names the pair "Keep Registration" and "Cancel Registration".
- **Heuristic:** H4 Consistency and standards; H5 Error prevention.
- **Persona impact:** Minor. The dialog does name the event and offers a safe choice.
- **Priority:** Low
- **Recommendation:** Dim the full screen, including the nav, and use the S06 layout as the background. Rename the button "Cancel Registration" and consider a clearer destructive style.
- **Verification:** Observed in image.

### 17. Screen S09: contradictory notification content

- **Issue:** "Registration Confirmed" was 10 minutes ago, yet "Event Reminder" yesterday says the Music Night starts in 3 days. "New Event Available" invites registration for the Workshop, which S06 shows as already registered.
- **Heuristic:** H4 Consistency and standards; H2 Match between system and real world.
- **Persona impact:** Contradictions make Linh doubt which registrations are real.
- **Priority:** Low
- **Recommendation:** Align the notification copy with the events data. The unread dots and tint are backed by the "2 unread" text, so per-item unread state is acceptable.
- **Verification:** Observed in image.

### 18. Screen S07: non-interactive text styled as a link

- **Issue:** Pass type "General" is blue text, the same style as links. It is not interactive.
- **Heuristic:** H4 Consistency and standards (blue is reserved for actions).
- **Persona impact:** Linh may tap it expecting something to happen.
- **Priority:** Low
- **Recommendation:** Use the same dark text as the other ticket values.
- **Verification:** Observed in image.

### 19. Screen S04: required fields marked by an asterisk only

- **Issue:** Required fields are marked only with a red asterisk, while optional is written in words. The phone placeholder uses a +1 format.
- **Heuristic:** Accessibility: status must not rely on colour alone; H2 Match between system and real world. DESIGN.md says to indicate required and optional fields in words.
- **Persona impact:** Minor. Linh's name, ID and email come prefilled, which is good.
- **Priority:** Low
- **Recommendation:** Add "(required)" or an equivalent word, and use a local phone example.
- **Verification:** Observed in image.

### 20. Screen S05: secondary button off-spec

- **Issue:** The secondary button "Back to Discover" has a dark label and a very faint outline. DESIGN.md calls for a blue label and a visible 1dp outline.
- **Heuristic:** H4 Consistency and standards; Accessibility: UI graphics contrast ≥ 3:1.
- **Persona impact:** Minor. The primary CTA is clear.
- **Priority:** Low
- **Recommendation:** Use the Secondary spec: blue label, visible outline.
- **Verification:** Outline contrast: needs Figma check.

### 21. Screen S01: logo and thumbnail crops

- **Issue:** The header has a very small logo image next to the "Camply" wordmark. The list thumbnails have different crops (the football image is noticeably shorter and wider than the others).
- **Heuristic:** H4 Consistency and standards; H8 Aesthetic and minimalist design. DESIGN.md asks for consistent crops in the same card type.
- **Persona impact:** Cosmetic only.
- **Priority:** Low
- **Recommendation:** Keep one logo treatment and one thumbnail ratio.
- **Verification:** Observed in image.

### 22. Screen T07: unlabeled "+" button and snackbar overlap

- **Issue:** In the "More Happening This Week" card, the "+" button has no label. The snackbar overlaps the card's bottom edge and its "42 spots left" line.
- **Heuristic:** H6 Recognition rather than recall; H2 Match between system and real world.
- **Persona impact:** Linh can't tell whether "+" registers or saves.
- **Priority:** Low
- **Recommendation:** Replace the "+" with the standard bookmark target or a labelled action used elsewhere, and give the snackbar its own space above the nav.
- **Verification:** Observed in image. Snackbar placement: needs Figma check.

## What works well and should be kept

- **S04:** prefilled name, ID and email, a sticky "Confirm Registration" button at the thumb's reach, and persistent labels above the fields.
- **S05 and S07:** a clear loading → success → View Ticket path. The calm success screen follows the confetti rules, and the QR is large, high-contrast and printed on a white card.
- **S06:** the "Registered" status uses an icon plus text, not colour alone, and View Ticket is one tap from My Events.
- **T01:** the dialog names the event, explains the consequence and offers "Keep Registration" as the safe choice.
- **T04 and T06:** the empty and no-results screens each give a clear next step (Explore Events, Clear Filters).
- **S10 and S09:** simple, scannable structure, with Saved Events and Notifications reachable without adding bottom tabs.
- **Bottom navigation overall:** four tabs with labels and an active indicator, matching DESIGN.md.
- **Lime badges with dark text:** the category badges (S01, S02, S06) are consistent and legible.

## 4. Kiểm tra trước khi dùng kết quả

- [x] Có ít nhất 5 phát hiện, mỗi phát hiện gắn với một màn hình cụ thể. (22 phát hiện, có mã màn hình.)
- [x] Mỗi phát hiện có tên heuristic hoặc tiêu chí accessibility.
- [ ] Có liên hệ tới persona Linh (một tay, đọc ngoài nắng, mạng chập chờn). **Chưa khớp:** câu trả lời dùng persona "Linh", còn persona chính của nhóm là Nguyễn Minh Anh. Cần ghi chú rõ hoặc chạy lại với đúng persona.
- [x] Phân biệt được điều quan sát được với điều cần kiểm tra trong Figma. (Mỗi phát hiện có mục Verification.)
- [x] Không có con số contrast, kích thước sp hoặc dp bị bịa. Các số trong phản biện đều lấy từ DESIGN.md hoặc được đánh dấu cần kiểm tra trong Figma.
- [x] Không có đề xuất thêm tính năng ngoài phạm vi.

**Ghi chú của sinh viên:**
1. **S03 không hoàn toàn bị hỏng.** Ba file `screen.png` trong thư mục export Stitch hỏng ("Image failed to fetch"), nhưng ba file trong `assets/stitch/` hiển thị được. Trên ảnh này, ảnh bìa của S03 là khung xám có chữ "img", tức ảnh không tải được. Phản biện chưa nêu lỗi này.
2. **Persona không khớp.** Xem phần cần xác nhận ở mục 1.

## 5. Phát hiện được chọn để quyết định

Các phát hiện dưới đây là ứng viên, lấy từ câu trả lời ở mục 3. Sinh viên chọn quyết định và viết lý do. Không điền thay.

| # | Màn hình | Phát hiện (theo AI) | Heuristic / tiêu chí | Quyết định (Chấp nhận / Chỉnh sửa / Từ chối) | Lý do (persona / heuristic / ràng buộc) |
|---|---|---|---|---|---|
| 1 | T07 | Không có nút Undo sau khi hủy | H3, H9 | [chọn] | [viết] |
| 3 | S07 | Tên và mã sinh viên trên vé khác với hồ sơ | H4, H1 | [chọn] | [viết] |
| 4 | S01, S02, S04–S08, T08 | Ngày, địa điểm và định dạng giờ không nhất quán | H4 | [chọn] | [viết] |
| 7 | T03 | Màn loading không có thông báo chờ lâu hoặc lối thoát | H1, H9 | [chọn] | [viết] |
| 11 | S07 | QR không được ghi rõ là bản demo | H1; DESIGN.md | [chọn] | [viết] |

Ghi chú: Nên có ít nhất một phát hiện bị từ chối hoặc chỉnh sửa, với lý do cụ thể. "AI nói vậy" và "mình thích" không được tính là lý do.
