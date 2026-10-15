# Camply — AI Design Log

**Môn học / Lab:** PRM323 — Cross-Platform Application Development · Lab 2: Thiết kế UI/UX có hỗ trợ AI (Google Stitch → Figma)  
**Chủ đề:** Camply — Ứng dụng khám phá và đăng ký sự kiện trong trường cho sinh viên 18–24 tuổi (Android, 360 × 800 dp)  
**Sinh viên thực hiện:** Nguyễn Ngọc Phương Đông · Nguyễn Thị Tú Anh · Trần Đình Phúc · Dương Minh Kiệt  
**Phiên bản log:** Bản hoàn chỉnh (gồm giai đoạn Generate v1, 4 vòng lặp Refine và giai đoạn Critique bằng AI)  
**Phạm vi bằng chứng:** Prompt nguyên văn S01–S10 và T01–T07 · Ảnh chụp Stitch (`assets/stitch/`) · `design/DESIGN.md` · Bản ghi phản biện từ Claude 3.5 Sonnet  
**Đường dẫn trong repo:** `ai/ai-design-log.md` · `assets/stitch/` · `assets/figma/`

---

## 1. Khai báo công cụ AI

| Công cụ | Dùng để làm gì | Giai đoạn |
|---|---|---|
| **Google Stitch** | Tạo UI ban đầu cho S01–S10 và các biến thể trạng thái T01–T07 từ prompt + `DESIGN.md`; thực hiện 4 vòng lặp tinh chỉnh giao diện | Generate (v1) & Refine |
| **Claude 3.5 Sonnet (Anthropic)** | Đánh giá độc lập toàn bộ UI theo 10 heuristic của Nielsen, tiêu chí accessibility và persona Nguyễn Minh Anh | Critique |
| **Claude (Anthropic)** | Tổng hợp tài liệu log này từ prompt và ảnh chụp có sẵn, chuẩn hóa đặc tả màn hình và tài liệu handoff | Tài liệu & Handoff |

---

## 2. Bản mô tả thiết kế đưa cho Stitch (`design/DESIGN.md`)

Mọi prompt v1 và các vòng lặp đều tham chiếu file `design/DESIGN.md` (tên hệ thống: Campus Event Guide) và phong cách "Modern Campus Editorial". Các giá trị chính:

| Nhóm | Giá trị trong `DESIGN.md` | Ghi chú sử dụng |
|---|---|---|
| **Màu chính** | `primary` / Electric Blue `#2457F5`; `primary-pressed` `#1745D5`; `primary-soft` `#EAF0FF` | Hành động chính, tab đang chọn |
| **Màu nhấn** | `accent` Lime `#C9F46A` | Dùng tiết chế (nhãn danh mục sự kiện, đi kèm chữ tối `#171923`) |
| **Nền & chữ** | `background` `#F8F9FC`; `surface` `#FFFFFF`; `text-primary` `#171923`; `text-secondary` `#525866`; `text-disabled` `#737987`; `border` `#DCE0E8` | Nền sáng trung tính và văn bản có độ tương phản ≥ 4.5:1 |
| **Trạng thái** | `success` `#18794E`; `warning` `#8A5700`; `error` `#B42336` (`error-surface` `#FDECEF`) | Phản hồi & lỗi (luôn kèm icon/nhãn chữ) |
| **Typography** | `Inter` — display 28/36 · headline 24/32 · subhead 20/28 · title 16/24 · body 14/20 · label 14/20 (500) · button 16/24 (600) | Chữ nội dung ≥ 14 sp |
| **Bo góc** | sm 8 · md 12 · lg 16 · xl 20 · pill 999 (dp) | Thẻ và control 8–16 dp, dialog 20 dp |
| **Khoảng cách** | margin/gutter 16 · xs 4 · sm 8 · md 12 · lg 16 · xl 24 (dp) | Thang 4 dp, lề ngang 16 dp |

---

## 3. Danh mục kết quả v1

| Mã | Màn hình | Prompt | Ảnh chụp (`assets/stitch/`) |
|---|---|---|---|
| **S01** | Discover / Home | Có (nguyên văn) | Có (`assets/stitch/s01_discover_home.png`) |
| **S02** | Explore Events | Có (nguyên văn) | Có (`assets/stitch/s02_explore_events.png`) |
| **S03** | Event Detail | Có (nguyên văn) | Có (`assets/stitch/s03_event_detail.png`) |
| **S04** | Event Registration | Có (nguyên văn) | Có (`assets/stitch/s04_event_registration.png`) |
| **S05** | Registration Success | Có (nguyên văn) | Có (`assets/stitch/s05_registration_success.png`) |
| **S06** | My Events | Có (nguyên văn) | Có (`assets/stitch/s06_my_events.png`) |
| **S07** | Digital Ticket | Có (nguyên văn) | Có (`assets/stitch/s07_digital_ticket.png`) |
| **S08** | Saved Events | Có (nguyên văn) | Có (`assets/stitch/s08_saved_events.png`) |
| **S09** | Notifications | Có (nguyên văn) | Có (`assets/stitch/s09_notifications.png`) |
| **S10** | Student Profile | Có (nguyên văn) | Có (`assets/stitch/s10_student_profile.png`) |
| **T01** | Cancel Registration Dialog (biến thể của S06) | Có (nguyên văn) | Có (`assets/stitch/t01_cancel_registration_dialog.png`) |
| **T02** | Registration Form Validation Error (biến thể của S04) | Có (nguyên văn) | Có (`assets/stitch/t02_registration_form_validation_error.png`) |
| **T03** | Registration Loading State (biến thể của S04) | Có (nguyên văn) | Có (`assets/stitch/t03_registration_loading_state.png`) |
| **T04** | Saved Events Empty State (biến thể của S08) | Có (nguyên văn) | Có (`assets/stitch/t04_saved_events_empty_state.png`) |
| **T05** | Notifications Empty State (biến thể của S09) | Có (nguyên văn) | Có (`assets/stitch/t05_notifications_empty_state.png`) |
| **T06** | Explore – No Results (biến thể của S02) | Có (nguyên văn) | Có (`assets/stitch/t06_explore_no_results.png`) |
| **T07** | My Events – Cancellation Confirmation (biến thể của S06) | Có (nguyên văn) | Có (`assets/stitch/t07_my_events_cancellation_with_undo_snackbar.png`) |

*Ghi chú: Phạm vi của v1 gồm 10 màn hình chính (S01–S10) và 7 biến thể trạng thái (T01–T07). Theo đề lab, dialog và biến thể trạng thái không tính là màn hình riêng.*

---

## 4. Nhật ký prompt và kết quả v1 (Nguyên văn)

### 4.1 S01 — Discover / Home
- **Mục tiêu màn hình:** Màn hình chính: khám phá sự kiện nổi bật, danh mục và sự kiện sắp diễn ra.
- **Công cụ:** Google Stitch
- **Tham chiếu đưa vào prompt:** `design/DESIGN.md` (Campus Event Guide) + các màn hình đã duyệt trước đó (S02, S03, S06, S08).

**Prompt nguyên văn (không chỉnh sửa):**
```markdown
## ROLE
You are a senior mobile UI/UX designer specializing in clean, production-ready Android applications for university students.
 
## TASK
Create ONE polished, high-fidelity mobile screen for **Camply — S01 Discover / Home**, a campus event discovery and registration app for university students aged 18–24.
 
The screen should help students discover campus events quickly, understand what is happening, and access event details with minimal effort.
 
This is the main home screen, not a marketing landing page.
 
## DESIGN REFERENCES
- Use the attached `DESIGN.md` as the authoritative design system.
- Maintain visual consistency with the existing Camply screens, especially S02 Explore, S03 Event Detail, S06 My Events, and S08 Saved Events.
- Reuse the established typography, colors, icon style, spacing, buttons, card styling, and bottom navigation.
- Follow the Modern Campus Editorial visual style.
- Do not copy another screen's layout exactly; create a layout suitable for Discover / Home.
 
## FRAME AND DESIGN SYSTEM
- Platform: Android mobile.
- Frame: **360 × 800 dp**.
- Theme: Light.
- Font: Inter.
- Background: `#F8F9FC`.
- Primary color: Electric Blue `#2457F5`.
- Accent color: Lime `#C9F46A`, used sparingly.
- Primary text: `#171923`.
- Secondary text: `#525866`.
- Horizontal page margins: 16 dp.
- Use a consistent 4 dp spacing scale.
- Use 8–16 dp corner radii for cards and controls.
- Keep shadows subtle and visual hierarchy clear.
 
## EXACT SCREEN STRUCTURE
 
### 1. Header
- Display the Camply brand clearly.
- Include a short, friendly personalized greeting.
- Include a notification icon with a small unread indicator.
- Include a small student avatar.
- Keep the header compact and aligned.
 
### 2. Welcome Section
- Display the heading: **“What's happening on campus?”**
- Use a clear typographic hierarchy.
- Keep the supporting content minimal.
- Do not add a large promotional banner or excessive introductory text.
 
### 3. Featured Event
- Feature **“Campus Music Night”** as the main visual focus.
- Use an authentic-looking campus concert photograph.
- Show the event title, date, time, and venue.
- Place a compact date badge over the image.
- Include a clear **“Details”** action.
- Keep the image and its event information visually connected.
- Make the featured event prominent without allowing it to consume the entire screen.
 
### 4. Browse Categories
- Section title: **“Browse Categories”**.
- Include a **“See all”** action.
- Display four compact, recognizable icon-based category shortcuts:
  - Music
  - Workshop
  - Sports
  - Arts
- Keep the shortcuts evenly spaced and easy to tap.
- Avoid oversized illustrations or decorative category cards.
 
### 5. Upcoming Events
- Section title: **“Upcoming Events”**.
- Include a **“See all”** action that leads to S02 Explore Events.
- Show compact event previews with an image, event name, date, and venue.
- Use these example events:
  - AI & Future Careers Workshop
  - Football Tournament
  - Photography Walk
- Prioritize readability and quick scanning.
- Use consistent event-card styling with the other Camply screens.
 
### 6. Bottom Navigation
Display exactly four tabs:
- Discover
- Explore
- My Events
- Profile
 
Requirements:
- Discover must be the selected tab.
- Use consistent icons, labels, spacing, and active-state styling with the other Camply screens.
- Keep the navigation fixed at the bottom.
- Ensure the content does not overlap the navigation.
 
## INTERACTION REQUIREMENTS
- Tapping the featured event or its “Details” action opens S03 Event Detail.
- Tapping a category opens S02 Explore Events with the relevant category selected.
- Tapping “See all” in Browse Categories opens S02 Explore Events.
- Tapping “See all” in Upcoming Events opens S02 Explore Events.
- Tapping the notification icon opens the existing notifications destination.
- Tapping the bottom navigation tabs opens their corresponding existing screens.
- Do not invent additional destinations or unsupported interactions.
 
## HARD CONSTRAINTS — MUST FOLLOW
 
1. Generate **S01 Discover / Home only**.
2. Generate exactly one mobile screen at 360 × 800 dp.
3. Do not generate additional screens, alternative versions, or a multi-screen flow.
4. Do not add login, registration, payment, admin, or onboarding features.
5. Do not add a full search field; search belongs to S02 Explore Events.
6. Do not replace the featured event with a generic promotional banner.
7. Do not remove the four required categories or the Upcoming Events section.
8. Do not add extra bottom navigation tabs.
9. Do not invent new features, sections, statistics, or promotional content.
10. Do not use excessive text, oversized headings, nested cards, heavy shadows, or excessive gradients.
11. Do not use lime as the dominant color. Electric Blue remains the primary action color.
12. Do not change the established Camply design system or create a visually unrelated style.
13. Maintain accessible text contrast and a minimum touch-target size of 48 × 48 dp.
14. Keep the layout compact, realistic, and feasible to implement in a production Android application.
15. Prioritize the event photograph, event information, category shortcuts, and upcoming events in a clear visual hierarchy.
16. Avoid unnecessary decorative elements that do not support event discovery.
 
## EXPECTED OUTPUT
Generate one polished, high-fidelity Android UI screen for **Camply S01 Discover / Home**, using the attached `DESIGN.md` and existing Camply screens as design references.
 
The final result must be visually consistent, compact, easy to scan, and ready for further UI/UX evaluation.
```

- **Ảnh kết quả:** `assets/stitch/s01_discover_home.png`
- **Quan sát kết quả & Quyết định (v1):** Có header thương hiệu Camply, lời chào, thẻ Featured "Campus Music Night", 4 lối tắt danh mục (Music, Workshop, Sports, Arts), danh sách Upcoming Events và thanh điều hướng 4 tab với Discover đang chọn. Chữ trên ảnh bìa Featured và dữ liệu ngày giờ cần được đồng bộ với S03 ở giai đoạn tinh chỉnh. Chấp nhận làm baseline v1.

---

### 4.2 S02 — Explore Events
- **Mục tiêu màn hình:** Duyệt, tìm kiếm và lọc sự kiện.
- **Công cụ:** Google Stitch
- **Tham chiếu đưa vào prompt:** `design/DESIGN.md` + S01 Discover.

**Prompt nguyên văn (không chỉnh sửa):**
```markdown
You are a senior mobile UI/UX designer specializing in clean, production-ready Android applications.
 
## TASK
 
Create ONE high-fidelity mobile screen for **Camply — S02 Explore Events**, a campus event discovery and registration application for university students aged 18–24.
 
This is a fresh generation. The target is a polished, compact, and highly usable interface that does not require major redesign.
 
Use the attached **DESIGN.md** and the approved S01 Discover screen as design references.
 
## SCREEN AND DESIGN SYSTEM
 
- Frame: 360 × 800 dp, Android-first.
- Style: Modern Campus Editorial, clean and professional.
- Background: #F8F9FC.
- Primary color: #2457F5.
- Accent: #C9F46A, used sparingly.
- Primary text: #171923.
- Secondary text: #525866.
- Font: Inter.
- Horizontal page margins: 16 dp.
- Spacing: consistent 4 dp scale.
- Corner radius: 8–16 dp for controls and cards.
- Use consistent icons, typography and bottom navigation from S01.
 
Do not create a tablet layout, marketing landing page, or oversized concept mockup.
 
## EXACT SCREEN STRUCTURE
 
Arrange the following elements vertically, in this order:
 
### 1. Page Header
 
- Title: "Explore Events".
- Clear, bold typography.
- No decorative subtitle, promotional banner or additional profile header.
 
### 2. Search Field
 
- Full-width search field.
- Search icon on the left.
- Placeholder: "Search events by name or keyword".
- Compact height and subtle border.
- Clear-search control only when a query is entered.
 
### 3. Category Filters
 
One horizontally scrollable row containing:
 
All | Music | Workshop | Sports | Arts
 
- "All" is selected by default.
- Selected state uses primary blue.
- Unselected chips use neutral backgrounds.
- Keep chips compact, readable and visually consistent.
 
### 4. Secondary Filters
 
One compact horizontal row containing:
 
Any time | On campus | Sort: Newest
 
- Use subtle outline controls.
- Avoid large filter panels or separate filter cards.
- Do not introduce additional filter categories.
 
### 5. Search Results
 
Display the text:
 
"24 events found"
 
Use a subtle, compact text style.
 
### 6. Event List
 
Create vertically stacked, **compact horizontal event cards**.
 
Each card must contain:
 
- One event thumbnail on the left.
- Category label.
- Event title in bold.
- Date and time.
- Venue.
- Bookmark icon aligned on the right.
 
Sample events, in this exact order:
 
1. Campus Music Night — Music
2. AI & Future Careers Workshop — Workshop
3. Football Tournament — Sports
4. Photography Walk — Arts
 
Use concise sample metadata. Do not invent extra descriptions, organizer biographies, ratings, ticket prices or promotional badges.
 
**Card layout requirements:**
 
- Use a thumbnail approximately 88 × 88 dp.
- Keep card height approximately 108–120 dp.
- Use balanced internal padding.
- Maintain clear alignment between image and text.
- Keep the event title visually dominant.
- Date/time and venue must remain legible.
- Avoid excessive nested containers, thick borders and heavy shadows.
- Avoid large vertical gaps between cards.
- Show approximately three cards within the initial viewport; remaining cards may continue below the fold through vertical scrolling.
 
### 7. Bottom Navigation
 
Use a fixed bottom navigation bar with exactly four destinations:
 
Discover | Explore | My Events | Profile
 
- Explore is active.
- Use the same visual treatment as S01.
- Keep navigation separate from scrollable content.
- Do not add additional tabs or floating action buttons.
 
## UX AND ACCESSIBILITY REQUIREMENTS
 
- Make the search field and filters easy to discover.
- Prioritize quick scanning of event titles and dates.
- Maintain a clear visual hierarchy.
- Body text must be at least 14 sp.
- Interactive targets must be at least 48 × 48 dp.
- Normal text must meet a minimum 4.5:1 contrast ratio.
- Avoid truncating important event titles or essential metadata.
- Use consistent icon sizes and spacing.
- Ensure the screen remains usable at 412 dp width.
 
## HARD CONSTRAINTS — MUST FOLLOW
 
1. Generate exactly ONE mobile screen.
2. Do not add marketing banners or hero sections.
3. Do not use oversized event images.
4. Do not use vertical poster-style event cards.
5. Do not create nested cards inside cards.
6. Do not add explanatory paragraphs or unnecessary copy.
7. Do not invent new functionality.
8. Do not change the four-item bottom navigation.
9. Do not use typography smaller than 14 sp for body metadata.
10. Do not squeeze all four events into the viewport at the expense of readability.
11. Preserve the established Camply design system.
12. Do not redesign any other Camply screen.
 
## EXPECTED RESULT
 
A polished, compact Explore Events screen with a clear search experience, readable category and filter controls, professional horizontal event cards, and consistent navigation.
 
The design should feel like a real production-ready campus application, not a decorative AI-generated concept.
```

- **Ảnh kết quả:** `assets/stitch/s02_explore_events.png`
- **Quan sát kết quả & Quyết định (v1):** Có tiêu đề "Explore Events", ô tìm kiếm, chip danh mục (All, Music, Workshop, Sports, Arts), 3 bộ lọc phụ, dòng "24 events found" và 4 thẻ sự kiện có nút bookmark. Thẻ Campus Music Night ghi "Fri, Oct 24 • 7:00 PM" tại "Student Union Amphit…" (khác với S03). Chấp nhận làm baseline v1; các điểm cần đồng bộ dữ liệu được tập hợp ở mục 5 và 6.

---

### 4.3 S03 — Event Detail
- **Mục tiêu màn hình:** Xem chi tiết một sự kiện và quyết định đăng ký.
- **Công cụ:** Google Stitch
- **Tham chiếu đưa vào prompt:** `design/DESIGN.md` + S01/S02.

**Prompt nguyên văn (không chỉnh sửa):**
```markdown
You are a senior mobile UI/UX designer. Create ONE production-ready high-fidelity Android screen for **Camply — S03 Event Detail**.
 
**Goal:** Help a student understand an event and confidently register.
 
**References:** Follow the attached Camply DESIGN.md and approved S01/S02 designs. Use a 360 × 800 dp mobile frame, Inter, background #F8F9FC, Electric Blue #2457F5, restrained Lime #C9F46A, text #171923 / #525866, 16 dp page margins, and consistent spacing.
 
**Exact content:**
 
- Event: Campus Music Night
- Category: Music
- Date: October 26, 2026
- Time: 18:00–22:00
- Venue: Main Stadium
- Organizer: Campus Student Union
 
**Required layout, top to bottom:**
 
1. Minimal app bar with Back button and a bookmark action.
2. Wide, high-quality photograph of a real-looking university music concert. Use a restrained image height so the hero does not dominate the viewport.
3. Prominent event title, compact Music badge, and clearly grouped date/time and venue metadata.
4. Three horizontal tabs: **About | Schedule | Location**. About is selected by default, with a visible blue active indicator.
5. About content: one short introductory paragraph about the campus music event and a compact organizer row. Keep the copy concise and readable.
6. Fixed bottom action area with one primary full-width button: **Register Now**.
 
**Interaction intent:**
 
- Back returns to S02 Explore.
- Bookmark saves the event.
- Schedule and Location switch content within the same screen.
- Register Now opens S04 Event Registration.
 
**Hard constraints:**
 
- Generate only the About-tab state of S03.
- Do not generate three separate screens.
- Do not add reviews, ratings, ticket prices, maps, verified badges, social sharing or related-event recommendations.
- Do not use multiple nested information cards.
- Do not repeat the date or venue in several sections.
- Keep the Register Now button visible and unobstructed.
- Use body text ≥14 sp and interactive targets ≥48 × 48 dp.
- Do not truncate essential information.
- Preserve a modern editorial look with clear hierarchy and restrained decoration.
 
**Expected output:** A compact, polished Event Detail screen with an attractive concert hero, readable information, clearly selected About tab and prominent registration action.
```

- **Ảnh kết quả:** `assets/stitch/s03_event_detail.png`
- **Quan sát kết quả & Quyết định (v1):** Có ảnh sự kiện, nhãn Music, tiêu đề, ngày giờ "October 26, 2026 • 18:00–22:00", địa điểm "Main Stadium Lawn", 3 tab About / Schedule / Location, mô tả, đơn vị tổ chức Campus Student Union và nút "Register Now" cố định. Tuy nhiên bị xuất hiện thêm thanh thương hiệu "Explore" chồng phía trên thanh App Bar con (sẽ sửa ở Vòng lặp 1). Chấp nhận làm baseline v1.

---

### 4.4 S04 — Event Registration
- **Mục tiêu màn hình:** Nhập thông tin để đăng ký tham gia sự kiện.
- **Công cụ:** Google Stitch
- **Tham chiếu đưa vào prompt:** `design/DESIGN.md` + S03 Event Detail.

**Prompt nguyên văn (không chỉnh sửa):**
```markdown
You are a senior mobile UI/UX designer. Generate ONE high-fidelity Android mobile screen for **Camply — S04 Event Registration**.
 
**Goal:** Allow a university student to register for an event quickly, accurately and confidently.
 
Follow the attached DESIGN.md and the approved S03 Event Detail screen. Use a 360 × 800 dp frame, Inter, #2457F5 primary blue, #C9F46A restrained accent, #F8F9FC background, 16 dp horizontal margins, and the same component styling as the other Camply screens.
 
**Screen structure:**
 
1. Minimal top app bar with Back button and title **Event Registration**.
2. Compact event summary showing:
   - Campus Music Night
   - October 26, 2026
   - 18:00–22:00
   - Main Stadium
3. One concise section heading: **Your Information**.
4. Single-column registration form with four fields:
   - Full Name — required
   - Student ID — required
   - University Email — required
   - Phone Number — optional
5. Each field must have a persistent visible label, suitable placeholder and appropriate input affordance.
6. A clear primary button labeled **Confirm Registration** after the form.
 
**Form behavior to communicate visually:**
 
- Required fields are clearly identified.
- Optional Phone Number is explicitly marked.
- Inline validation should be possible without changing the overall layout.
- Confirm Registration leads to S05 Registration Success after successful submission.
 
**Hard constraints:**
 
- This is a SINGLE-SCREEN FORM, NOT A MULTI-STEP WIZARD.
- Do not add Step 1 of 1, Step 1 of 3, progress bars or numbered steps.
- Do not add payment, coupon, seat selection, account login or ticket pricing.
- Do not add privacy assurance cards, promotional messages, directions sections or long explanatory paragraphs.
- Do not use decorative illustrations that compete with the form.
- Do not duplicate event information.
- Do not generate validation, loading or success screens in this generation.
- All form labels and metadata must be readable at ≥14 sp.
- Tap targets must be ≥48 × 48 dp.
- Keep the layout compact enough for comfortable mobile form completion, allowing vertical scrolling when needed.
 
**Expected output:** A clean, practical event registration screen prioritizing the four form fields and the Confirm Registration action.
```

- **Ảnh kết quả:** `assets/stitch/s04_event_registration.png`
- **Quan sát kết quả & Quyết định (v1):** Có thẻ tóm tắt sự kiện + 4 trường: Full Name, Student ID, University Email (required) và Phone Number (optional) cùng nút chính "Confirm Registration". Tuy nhiên các ô đang để trống dạng placeholder ("e.g. Alex Rivera") khiến sinh viên phải gõ lại thông tin đã có trong hồ sơ (sẽ sửa ở Vòng lặp 2). Chấp nhận làm baseline v1.

---

### 4.5 S05 — Registration Success
- **Mục tiêu màn hình:** Xác nhận đăng ký thành công và dẫn tới vé.
- **Công cụ:** Google Stitch
- **Tham chiếu đưa vào prompt:** `design/DESIGN.md` + S04.

**Prompt nguyên văn (không chỉnh sửa):**
```markdown
You are a senior mobile UI/UX designer. Create ONE polished Android screen for **Camply — S05 Registration Success**.
 
**Goal:** Clearly confirm successful event registration and guide the student to their digital ticket.
 
Follow the attached Camply DESIGN.md and approved S04 design. Frame: 360 × 800 dp. Use Inter, background #F8F9FC, primary #2457F5, restrained lime #C9F46A, 16 dp page margins and consistent Camply buttons.
 
**Exact content:**
 
- Event: Campus Music Night
- Date: October 26, 2026
- Time: 18:00–22:00
- Venue: Main Stadium
 
**Layout:**
 
1. Minimal header consistent with Camply.
2. Centered success symbol: a clean checkmark inside a subtle circular treatment.
3. Large heading: **You're Registered!**
4. One short supporting sentence: **Your spot at Campus Music Night is confirmed.**
5. Compact event summary showing the event name, date/time and venue.
6. Primary full-width button: **View My Digital Ticket**.
7. Secondary text or outlined action: **Back to Discover**.
 
Use balanced vertical spacing. The success message should be the main focus, with the ticket button immediately recognizable as the next step.
 
**Hard constraints:**
 
- Generate only S05.
- Do not add Add to Calendar, Add to Schedule, Share Event, Download Ticket or promotional recommendations.
- Do not include registration form fields.
- Do not add a large decorative illustration or excessive confetti.
- Do not create oversized empty areas between the message, summary and actions.
- Do not use multiple overlapping or nested cards.
- Keep the event summary compact.
- Use accessible text contrast and ≥48 × 48 dp button targets.
- The primary action opens S07 Digital Ticket.
- Back to Discover opens S01.
 
**Expected output:** A simple, attractive confirmation screen that feels celebratory without clutter and provides one obvious next action.
```

- **Ảnh kết quả:** `assets/stitch/s05_registration_success.png`
- **Quan sát kết quả & Quyết định (v1):** Có biểu tượng thành công, tiêu đề "You're Registered!", thẻ sự kiện trạng thái Confirmed, hành động chính "View My Digital Ticket" và hành động phụ "Back to Discover". Chấp nhận làm baseline v1.

---

### 4.6 S06 — My Events
- **Mục tiêu màn hình:** Xem các sự kiện đã đăng ký (Upcoming / Past).
- **Công cụ:** Google Stitch
- **Tham chiếu đưa vào prompt:** `design/DESIGN.md` + S02.

**Prompt nguyên văn (không chỉnh sửa):**
```markdown
You are a senior mobile UI/UX designer. Generate ONE production-ready Android screen for **Camply — S06 My Events**.
 
**Goal:** Let students review their registrations, open tickets and manage upcoming events.
 
Follow Camply DESIGN.md and the approved S02 horizontal card language. Use a 360 × 800 dp frame, Inter, #2457F5 primary, restrained #C9F46A accent, #F8F9FC background, 16 dp margins and consistent bottom navigation.
 
**Required structure:**
 
1. App header with title **My Events**.
2. Two tabs: **Upcoming** and **Past**, with Upcoming selected.
3. Display exactly two upcoming registered events:
   - Campus Music Night — October 26, 2026 — 18:00–22:00 — Main Stadium.
   - AI & Future Careers Workshop — a compact example workshop entry with date, time and venue.
4. Each event card includes a small thumbnail, event title, date/time, venue, a subtle **Registered** status indicator, and two actions:
   - **View Ticket** — primary.
   - **Cancel Registration** — secondary, visually less prominent.
5. Fixed four-item bottom navigation: Discover, Explore, My Events, Profile. My Events is selected.
 
**Interaction intent:**
 
- Upcoming/Past switches registered-event lists.
- View Ticket opens S07.
- Cancel Registration opens T01 confirmation dialog.
- A successful cancellation updates the list and supports Undo in T07.
 
**Hard constraints:**
 
- Generate only the default Upcoming state.
- Do not show the cancellation dialog, empty state or snackbar yet.
- Do not add ticket QR codes inside event cards.
- Do not add registration forms, promotional banners or recommendation sections.
- Do not invent an additional third registered event.
- Do not create huge poster cards.
- Keep the two event cards visually consistent.
- Avoid nested cards, duplicate status labels and redundant actions.
- Make the destructive action distinguishable from View Ticket.
- Use body text ≥14 sp and touch targets ≥48 × 48 dp.
- Keep bottom navigation fixed.
 
**Expected output:** A clean My Events screen with two manageable upcoming registrations and clearly differentiated ticket/cancellation actions.
```

- **Ảnh kết quả:** `assets/stitch/s06_my_events.png`
- **Quan sát kết quả & Quyết định (v1):** Có tab Upcoming (2) / Past; 2 thẻ sự kiện, mỗi thẻ có nhãn `● Registered`, nút "View Ticket" và nút "Cancel". Chấp nhận làm baseline v1.

---

### 4.7 S07 — Digital Ticket
- **Mục tiêu màn hình:** Hiển thị vé điện tử để check-in.
- **Công cụ:** Google Stitch
- **Tham chiếu đưa vào prompt:** `design/DESIGN.md` + S05/S06.

**Prompt nguyên văn (không chỉnh sửa):**
```markdown
You are a senior mobile UI/UX designer. Create ONE high-fidelity Android screen for **Camply — S07 Digital Ticket**.
 
**Goal:** Allow a registered student to display a clear digital admission ticket for event check-in.
 
Follow Camply DESIGN.md and approved S05/S06 designs. Frame 360 × 800 dp. Use Inter, primary blue #2457F5, restrained lime #C9F46A, light background #F8F9FC, 16 dp horizontal margins and readable typography.
 
**Exact ticket content:**
 
- Event: Campus Music Night
- Date: October 26, 2026
- Time: 18:00–22:00
- Venue: Main Stadium
- Attendee: Alex Morgan
- Student ID: STU-849201
- Pass type: General Admission
- Ticket number: CMN-2026-0849
 
**Required layout:**
 
1. Minimal app bar with Back button and title **My Ticket**.
2. One visually distinctive but restrained digital ticket card.
3. Ticket header containing the event name and a subtle blue/lime accent stripe.
4. Clearly grouped event details: date, time and venue.
5. Attendee details: name, student ID, pass type and ticket number.
6. A large centered black-and-white **simulated QR code**, with sufficient white quiet space around it.
7. Short instruction: **Show this ticket at the entrance for check-in.**
 
**Hard constraints:**
 
- Use exactly ONE primary ticket card.
- Do not add multiple tickets, extra event recommendations or large decorative illustrations.
- Do not add payment information, verified status, offline availability claims, wallet integration or share/download buttons.
- Do not duplicate the ticket number.
- Do not crop the QR code.
- Do not make the QR code too small to see.
- Clearly treat the QR as a visual prototype, not a claim of working ticket validation.
- Avoid excessive shadows, gradients and nested cards.
- Use readable metadata ≥14 sp and interactive targets ≥48 × 48 dp.
- Ensure the ticket is comfortably viewable on a 360 × 800 dp screen; scroll only if necessary.
 
**Expected output:** A realistic, organized digital event ticket with a prominent simulated QR and all essential admission details.
```

- **Ảnh kết quả:** `assets/stitch/s07_digital_ticket.png`
- **Quan sát kết quả & Quyết định (v1):** Có nhãn Music, trạng thái Confirmed, ngày giờ, địa điểm Main Stadium, Attendee Alex Morgan, Student ID STU-849201, Pass type, Ticket No. CMN-2026-0849; mã QR lớn trên nền trắng và ghi chú "Demonstration pass". Chấp nhận làm baseline v1.

---

### 4.8 S08 — Saved Events
- **Mục tiêu màn hình:** Xem các sự kiện đã đánh dấu để xem sau.
- **Công cụ:** Google Stitch
- **Tham chiếu đưa vào prompt:** `design/DESIGN.md` + S02.

**Prompt nguyên văn (không chỉnh sửa):**
```markdown
You are a senior mobile UI/UX designer. Generate ONE polished Android screen for **Camply — S08 Saved Events**.
 
**Goal:** Help students revisit bookmarked campus events and remove bookmarks easily.
 
Follow Camply DESIGN.md and the approved S02 Explore Events screen. Use the same compact horizontal event-card style. Frame 360 × 800 dp, Inter, #2457F5 primary, #C9F46A restrained accent, #F8F9FC background and 16 dp horizontal margins.
 
**Required layout:**
 
1. Minimal header with Back button and title **Saved Events**.
2. One concise supporting line indicating that this page contains bookmarked events.
3. A subtle saved-event count showing **3 saved events**.
4. Exactly three compact horizontal event cards:
   - Campus Music Night — Music.
   - AI & Future Careers Workshop — Workshop.
   - Photography Walk — Arts.
5. Each card includes a thumbnail, category, event title, date/time, venue and an active bookmark icon.
6. A clear but secondary **Explore More Events** action after the list.
 
**Interactions:**
 
- Tapping a card opens its Event Detail screen.
- Tapping its active bookmark removes the saved event.
- Explore More Events opens S02 Explore.
- If all bookmarks are removed, the interface transitions to T04 Saved Empty.
 
**Hard constraints:**
 
- Generate only the populated saved-events state.
- Do not generate the empty state.
- Do not add folders, collections, social sharing, recommendations or promotional content.
- Do not add a large information banner or repeated explanations.
- Do not use oversized vertical event posters.
- Do not put a separate full-width Unsave button on every card.
- Keep the cards consistent with S02.
- Avoid truncated event titles and essential metadata where possible.
- Use body text ≥14 sp and touch targets ≥48 × 48 dp.
 
**Expected output:** A compact, consistent Saved Events screen with three readable cards and an unobtrusive path back to event discovery.
```

- **Ảnh kết quả:** `assets/stitch/s08_saved_events.png`
- **Quan sát kết quả & Quyết định (v1):** Có tiêu đề "Saved Events", nhãn "3 saved", 3 thẻ sự kiện có bookmark đã chọn và nút "Explore More Events" ở cuối danh sách. Chấp nhận làm baseline v1.

---

### 4.9 S09 — Notifications
- **Mục tiêu màn hình:** Xem thông báo liên quan đến sự kiện.
- **Công cụ:** Google Stitch
- **Tham chiếu đưa vào prompt:** `design/DESIGN.md` + các màn hình đã duyệt.

**Prompt nguyên văn (không chỉnh sửa):**
```markdown
You are a senior mobile UI/UX designer. Create ONE production-ready Android screen for **Camply — S09 Notifications**.
 
**Goal:** Help students quickly scan event-related updates and distinguish unread notifications.
 
Follow the attached Camply DESIGN.md and approved Camply screens. Use a 360 × 800 dp frame, Inter, #2457F5 primary, restrained #C9F46A accent, #F8F9FC background, 16 dp page margins and clean spacing.
 
**Required structure:**
 
1. Minimal app bar with Back button and title **Notifications**.
2. Right-aligned text action: **Mark all read**.
3. Group notifications under two compact section headings: **Today** and **This Week**.
4. Display four concise notification rows across the groups:
   - Registration Confirmed — You're registered for Campus Music Night.
   - Event Reminder — Campus Music Night is coming up soon.
   - Event Update — Check the latest event details.
   - New Workshop — AI & Future Careers Workshop is open for registration.
5. Each row includes a small contextual icon, bold short title, one-line supporting message where possible, timestamp and subtle unread indicator when applicable.
6. Use light separators or spacing between rows rather than large cards.
 
**Interaction intent:**
 
- Tapping a notification opens the related event or ticket.
- Mark all read removes unread indicators.
- T05 is the separate Notifications Empty state.
 
**Hard constraints:**
 
- Generate only the populated notifications state.
- Do not add embedded event cards, QR tickets, images, banners or action buttons inside each notification.
- Do not add multiple repeated section explanations.
- Do not invent chat, friend requests, system warnings or unrelated notification types.
- Do not create oversized notification cards.
- Use subtle blue unread indicators, not large colorful status badges.
- Maintain readable timestamps and body text ≥14 sp.
- Keep tap targets ≥48 × 48 dp.
- Do not generate the empty state in this request.
 
**Expected output:** A simple, professional notification inbox with compact chronological groups and clearly distinguishable unread updates.
```

- **Ảnh kết quả:** `assets/stitch/s09_notifications.png`
- **Quan sát kết quả & Quyết định (v1):** Có nhóm "Today" (2 new) và "This week"; mỗi mục có biểu tượng, thời gian; mục chưa đọc chỉ có chấm xanh (sẽ bổ sung thêm nhãn chữ `NEW` ở Vòng lặp 3 để không phụ thuộc vào màu sắc đơn độc). Chấp nhận làm baseline v1.

---

### 4.10 S10 — Student Profile
- **Mục tiêu màn hình:** Xem thông tin sinh viên và đi nhanh tới hoạt động / hỗ trợ.
- **Công cụ:** Google Stitch
- **Tham chiếu đưa vào prompt:** `design/DESIGN.md` + S01/S02.

**Prompt nguyên văn (không chỉnh sửa):**
```markdown
You are a senior mobile UI/UX designer. Generate ONE high-fidelity Android screen for **Camply — S10 Student Profile**.
 
**Goal:** Let students view their identity and quickly navigate to event-related activities and account support.
 
Follow Camply DESIGN.md and the approved S01/S02 screens. Use 360 × 800 dp, Inter, background #F8F9FC, primary #2457F5, restrained lime #C9F46A, 16 dp horizontal margins, consistent iconography and the established four-item bottom navigation.
 
**Exact student identity:**
 
- Name: Alex Morgan
- Student ID: STU-849201
- University email: alex.m@university.edu
 
**Required layout:**
 
1. Compact header titled **Profile**.
2. One prominent but space-efficient student identity section containing:
   - Circular avatar.
   - Student name.
   - Student ID.
   - University email.
   - One **Edit Profile** action.
3. Section heading: **Your Activity**.
4. Three simple navigation rows:
   - My Events.
   - Saved Events.
   - Notifications.
5. Section heading: **Settings & Support**.
6. Two simple navigation rows:
   - App Settings.
   - Help & Support.
7. Fixed bottom navigation: Discover, Explore, My Events, Profile. Profile is selected.
 
**Interaction intent:**
 
- My Events opens S06.
- Saved Events opens S08.
- Notifications opens S09.
- Edit Profile, App Settings and Help & Support lead to their respective supporting prototype screens or states.
 
**Hard constraints:**
 
- Generate only S10 Profile.
- Do not add achievement badges, membership tiers, loyalty points, statistics dashboards or social profiles.
- Do not add unrelated settings, logout banners or promotional blocks.
- Do not create separate cards for every navigation row.
- Use a clean list-row structure with subtle dividers and right-facing chevrons.
- Keep the identity section compact.
- Avoid nested cards, large illustrations and excessive white space.
- Do not truncate the student's name, ID or email.
- Use body text ≥14 sp and touch targets ≥48 × 48 dp.
- Keep bottom navigation visually identical to S01/S02.
 
**Expected output:** A polished student profile with one clear identity area, two well-organized navigation groups and consistent Camply styling.
```

- **Ảnh kết quả:** `assets/stitch/s10_student_profile.png`
- **Quan sát kết quả & Quyết định (v1):** Có đủ khối nhận dạng (`Alex Morgan`, `STU-849201`, `alex.m@university.edu`), nút Edit Profile, nhóm Your Activity (3 dòng) và Settings & Support (2 dòng); tab Profile được chọn. Chấp nhận làm baseline v1.

---

### 4.11 Biến thể trạng thái (T01–T07)

#### T01 — Cancel Registration Dialog (Biến thể của S06)
- **Ảnh kết quả:** `assets/stitch/t01_cancel_registration_dialog.png`
- **Prompt nguyên văn:**
```markdown
You are a senior mobile UI/UX designer. Generate ONE polished Android screen for Camply — T01 Cancel Registration Confirmation Dialog.
Goal: Help students confirm or safely cancel an event registration without accidental destructive actions.
References: Use the attached Camply DESIGN.md and the approved S06 My Events screen. Preserve the existing visual design, typography, spacing, event data, and navigation.
Frame: 360 × 800 dp, Android-first, Inter, #2457F5 primary, #C9F46A restrained accent, #F8F9FC background, #171923 primary text, #525866 secondary text, 16 dp horizontal margins.
Scenario: The student taps Cancel Registration for Campus Music Night.
Required layout:
1. Show the existing S06 My Events screen as the background.
2. Apply a subtle dark overlay to the background.
3. Display one centered confirmation dialog with a white surface and restrained corner radius.
4. Dialog title: Cancel Registration?
5. Message: Are you sure you want to cancel your registration for Campus Music Night? Your ticket will no longer be available.
6. Secondary action: Keep Registration.
7. Destructive action: Yes, Cancel.
Interactions:
- Keep Registration closes the dialog and returns to S06 without changes.
- Yes, Cancel confirms cancellation and leads to T07 My Events After Cancellation.
- Make the safe action easy to identify and distinguish the destructive action clearly.
Hard Constraints:
- Generate exactly ONE screen showing the confirmation dialog open.
- Do not remove the event before confirmation.
- Do not redesign the underlying S06 screen.
- Do not add payment, refund, calendar, sharing, or unrelated features.
- Do not add a second dialog or extra confirmation step.
- Use body text ≥14 sp and touch targets ≥48 × 48 dp.
- Maintain accessible contrast and keep the background recognizable.
Expected Output: A compact, accessible cancellation confirmation dialog consistent with Camply, with clear consequences and two unambiguous actions.
```
- **Quan sát & Quyết định (v1):** Dialog overlay "Cancel Registration?" trên nền S06 làm mờ; hai lựa chọn "Keep Registration" (nút viền) và "Yes, Cancel" (chữ đỏ). Chấp nhận làm baseline v1.

#### T02 — Registration Form Validation Error (Biến thể của S04)
- **Ảnh kết quả:** `assets/stitch/t02_registration_form_validation_error.png`
- **Prompt nguyên văn:**
```markdown
You are a senior mobile UI/UX designer. Generate ONE polished Android screen for Camply — T02 Registration Form Validation Error.
Goal: Help students understand and correct registration form errors without losing their entered information.
References: Use the existing S04 Event Registration screen as the exact visual base. Follow the attached Camply DESIGN.md. Preserve the layout, event summary, form fields, typography, colors, spacing, and navigation.
Frame: 360 × 800 dp, Inter, #2457F5 primary, #C9F46A restrained accent, #F8F9FC background, 16 dp horizontal margins.
Scenario: The student taps Confirm Registration with missing required fields and an invalid university email.
Required layout:
1. Keep the existing Event Registration header and event summary.
2. Keep the original single-column form.
3. Full Name: empty, with inline error Please enter your full name.
4. Student ID Number: empty, with inline error Student ID is required.
5. University Email: show the entered value alex@gmail.com, with inline error Please enter a valid university email address.
6. Phone Number: optional, with no error.
7. Keep the Confirm Registration button visible.
Visual behavior:
- Highlight only invalid fields with subtle red borders.
- Place each error message directly below its corresponding field.
- Preserve the invalid email value so the student can correct it.
- Keep labels and error messages clearly distinguishable.
Hard Constraints:
- Generate only ONE validation-error screen.
- Do not redesign S04 or add new fields.
- Do not remove or rename existing form fields.
- Do not display a success message or navigate to S05.
- Do not add a large global error banner or unrelated explanatory content.
- Do not show an error for the optional phone field.
- Use body text ≥14 sp and touch targets ≥48 × 48 dp.
- Keep Confirm Registration visible and unobstructed.
Expected Output: A clear, compact form-validation state with field-specific feedback, preserved user input, and a visible retry action.
```
- **Quan sát & Quyết định (v1):** Ba trường bắt buộc có viền đỏ, icon chấm than và thông báo lỗi bên dưới; email `alex@gmail.com` được giữ nguyên để sửa. Chấp nhận làm baseline v1.

#### T03 — Registration Loading State (Biến thể của S04)
- **Ảnh kết quả:** `assets/stitch/t03_registration_loading_state.png`
- **Prompt nguyên văn:**
```markdown
You are a senior mobile UI/UX designer. Generate ONE polished Android screen for Camply — T03 Registration Loading State.
Goal: Communicate that a valid event registration is being processed and prevent repeated submission.
References: Use the existing S04 Event Registration screen as the visual base. Follow Camply DESIGN.md and preserve the original form, event information, colors, typography, spacing, and navigation.
Frame: 360 × 800 dp, Inter, #2457F5 primary, #C9F46A restrained accent, #F8F9FC background, 16 dp horizontal margins.
Scenario: The student completes all required fields correctly and taps Confirm Registration.
Required layout:
1. Keep the existing S04 Event Registration screen visible in the background.
2. Show a subtle dimmed overlay.
3. Place one compact white loading dialog near the center.
4. Display a blue circular progress indicator.
5. Main status: Confirming your registration...
6. Supporting message: Please wait a moment.
7. Show the Confirm Registration button as disabled while processing.
Interaction intent:
- Prevent repeated submissions while loading.
- When registration succeeds, transition to S05 Registration Success.
- Do not show success before processing finishes.
Hard Constraints:
- Generate only ONE loading-state screen.
- Do not redesign S04 or introduce new form fields.
- Do not show validation errors, ticket details, or success content.
- Do not add security verification claims or invented processing steps.
- Do not display progress percentages or additional actions.
- Use readable text and sufficient contrast.
- Keep the loading message concise and the original form recognizable.
Expected Output: A restrained loading overlay that communicates system status clearly and remains consistent with Camply's established mobile UI.
```
- **Quan sát & Quyết định (v1):** Hộp thoại loading "Confirming your registration..." trên form bị làm mờ; nút chính đổi thành "Confirming..." (vô hiệu hóa). Chấp nhận làm baseline v1.

#### T04 — Saved Events Empty State (Biến thể của S08)
- **Ảnh kết quả:** `assets/stitch/t04_saved_events_empty_state.png`
- **Prompt nguyên văn:**
```markdown
You are a senior mobile UI/UX designer. Generate ONE polished Android screen for Camply — T04 Saved Events Empty State.
Goal: Help students understand that no events are bookmarked and return easily to event discovery.
References: Use the approved S08 Saved Events screen and attached Camply DESIGN.md. Preserve the established header, typography, colors, spacing, and overall visual language.
Frame: 360 × 800 dp, Inter, #2457F5 primary, #C9F46A restrained accent, #F8F9FC background, 16 dp horizontal margins.
Scenario: The student has not bookmarked any events or removes the last saved event from S08.
Required layout:
1. Minimal header with Back button and title Saved Events.
2. Remove all saved-event cards.
3. Display one simple bookmark illustration or bookmark icon.
4. Heading: No Saved Events Yet
5. Supporting message: Save events you're interested in, and they'll appear here.
6. Primary button: Explore Events.
Interactions:
- Back returns to the previous screen.
- Explore Events navigates to S02 Explore.
- This state appears when the saved-event list becomes empty.
Hard Constraints:
- Generate exactly ONE empty-state screen.
- Do not display any event cards or a saved-event count of three.
- Do not add folders, collections, recommendations, search fields, or social features.
- Do not add promotional banners or duplicate explanations.
- Keep the empty-state content visually balanced and easy to scan.
- Use body text ≥14 sp and touch targets ≥48 × 48 dp.
- Preserve Camply's established design system.
Expected Output: A simple, friendly Saved Events empty state with a clear explanation and one prominent path back to event discovery.
```
- **Quan sát & Quyết định (v1):** Nhãn "0 saved", icon bookmark, tiêu đề "No Saved Events Yet", một hành động chính "Explore Events". Chấp nhận làm baseline v1.

#### T05 — Notifications Empty State (Biến thể của S09)
- **Ảnh kết quả:** `assets/stitch/t05_notifications_empty_state.png`
- **Prompt nguyên văn:**
```markdown
You are a senior mobile UI/UX designer. Generate ONE polished Android screen for Camply — T05 Notifications Empty State.
Goal: Tell students that they have no notifications yet and provide a straightforward way to discover campus events.
References: Use the approved S09 Notifications screen and T04 Saved Events Empty State as visual references. Follow the attached Camply DESIGN.md.
Frame: 360 × 800 dp, Inter, #2457F5 primary, #C9F46A restrained accent, #F8F9FC background, #171923 primary text, #525866 secondary text, 16 dp horizontal margins.
Required layout:
1. Minimal header with Back button and title Notifications.
2. Remove all notification rows, unread indicators, and New/Earlier sections.
3. Hide Mark all as read because there are no notifications.
4. Display a simple notification bell illustration.
5. Heading: You're All Caught Up!
6. Supporting message: No notifications yet. Updates about your campus events will appear here.
7. Primary button: Explore Events.
Interactions:
- Back returns to the previous screen.
- Explore Events navigates to S02 Explore.
Hard Constraints:
- Generate only ONE Notifications empty-state screen.
- Do not display the internal screen ID in the user-facing title.
- Do not add notification cards, settings, push-permission prompts, or unrelated features.
- Do not use a crossed-out bell that could imply notifications are disabled.
- Do not add redundant status chips or repeated empty-state messages.
- Use body text ≥14 sp and touch targets ≥48 × 48 dp.
- Keep the layout simple, centered, and consistent with T04.
Expected Output: A clean Notifications empty state that communicates the absence of notifications without suggesting an error or disabled feature.
```
- **Quan sát & Quyết định (v1):** Icon chuông, tiêu đề "You're All Caught Up!", hành động chính "Explore Events". Chấp nhận làm baseline v1.

#### T06 — Explore – No Results (Biến thể của S02)
- **Ảnh kết quả:** `assets/stitch/t06_explore_no_results.png`
- **Prompt nguyên văn:**
```markdown
You are a senior mobile UI/UX designer. Generate ONE polished Android screen for Camply — T06 Explore No Results.
Goal: Help students recover from a search that returns no matching campus events without losing their search context.
References: Use the approved S02 Explore Events screen and attached Camply DESIGN.md. Preserve the existing search, filter, and bottom-navigation styles.
Frame: 360 × 800 dp, Inter, #2457F5 primary, #C9F46A restrained accent, #F8F9FC background, 16 dp horizontal margins.
Scenario: The student searches for campus events and applies filters, but no events match.
Required layout:
1. Keep the Explore Events header.
2. Keep the search field and show the query Robotics Hackathon.
3. Keep the existing category filters: All, Music, Workshop, Sports, Arts. Show Workshop as selected.
4. Preserve the selected filter state.
5. Remove all event result cards.
6. Display a simple search or magnifying-glass illustration.
7. Heading: No Events Found
8. Supporting message: We couldn't find events matching your search. Try different keywords or clear your filters.
9. Primary button: Clear Filters.
10. Secondary text action: Try Another Search.
11. Keep the four-tab bottom navigation: Discover, Explore, My Events, Profile. Explore is active.
Interactions:
- Clear Filters resets the query and selected filters and returns to the default S02 Explore results.
- Try Another Search focuses the search field so the student can edit the query.
- Neither action should navigate away from Explore.
Hard Constraints:
- Generate exactly ONE no-results screen.
- Do not redesign S02 or add new filters.
- Do not display event cards, recommendations, or promotional content.
- Do not show a system-error message or an unrelated empty state.
- Do not remove the existing search query or selected filter.
- Use body text ≥14 sp and touch targets ≥48 × 48 dp.
- Preserve the existing four-tab navigation and Camply design system.
Expected Output: A compact Explore no-results state that preserves search context and offers two clear recovery actions.
```
- **Quan sát & Quyết định (v1):** Tìm "Robotics Hackathon" + chip Workshop → "0 results"; có "Clear Filters" và "Try Another Search". Chấp nhận làm baseline v1.

#### T07 — My Events – After Cancellation (Biến thể của S06)
- **Ảnh kết quả v1:** `assets/stitch/t07_my_events_cancellation_with_undo_snackbar.png`
- **Prompt nguyên văn (bản thử nghiệm v1 trên Stitch):**
```markdown
You are a senior mobile UI/UX designer. Generate ONE polished Android screen for Camply — T07 My Events After Cancellation with Undo Snackbar.
Goal: Confirm that an event registration was cancelled, update the student's Upcoming list, and provide a temporary way to undo the action.
References: Use the approved S06 My Events screen and T01 cancellation flow. Follow Camply DESIGN.md and preserve the established layout, colors, typography, spacing, and bottom navigation.
Frame: 360 × 800 dp, Inter, #2457F5 primary, #C9F46A restrained accent, #F8F9FC background, 16 dp horizontal margins.
Scenario: The student confirms cancellation of Campus Music Night through T01.
Required layout:
1. My Events
- Keep the My Events header.
- Keep the Upcoming and Past tabs, with Upcoming selected.
- Remove Campus Music Night from the Upcoming registered-event list.
- Update the Upcoming registration count to 0.
- Show a simple empty state in the Upcoming section.
- Heading: No Upcoming Events
- Supporting message: You don't have any upcoming registrations.
- Include an Explore Events action.
2. Cancellation Snackbar
- Display one compact snackbar above the bottom navigation.
- Message: Registration cancelled.
- Include a clearly visible Undo action.
- Use a neutral confirmation style, not a destructive error alert.
- Keep the snackbar from covering important navigation controls.
3. Bottom Navigation
- Keep exactly four destinations: Discover, Explore, My Events, Profile.
- My Events is selected.
Interactions:
- Undo restores the Campus Music Night registration and returns to the original S06 My Events state.
- Explore Events opens S02 Explore.
- The snackbar is temporary and dismisses after a short period.
- Make it clear that Undo is available temporarily, not indefinitely.
Hard Constraints:
- Generate only ONE screen showing the post-cancellation state with the snackbar visible.
- Do not show the T01 confirmation dialog.
- Do not keep Campus Music Night in the Upcoming list.
- Do not add payment, refund, calendar, sharing, or unrelated features.
- Do not add event recommendations or promotional sections.
- Do not redesign S06 or generate additional screens.
- Use body text ≥14 sp and touch targets ≥48 × 48 dp.
- Preserve the established Camply design system.
Expected Output: A compact My Events screen showing the updated empty Upcoming state and a clear, temporary Undo action without obstructing navigation.
```
- **Quan sát & Quyết định:** Bản xuất v1 của Stitch tự ý thêm khối "Popular this week" và đặt Snackbar có chữ UNDO đè lên thẻ bên dưới. Sau khi đánh giá lại nghiệp vụ và phản biện (xem Quyết định D07 và Mục 6.2), nhóm quyết định **từ chối nút Undo ở T07** (vì thao tác hủy đã được xác nhận tại T01 và được commit lên hệ thống, không thể hứa hẹn hoàn tác nếu suất đã chuyển cho người khác) và bỏ khối "Popular this week" thừa trên Figma.

---

## 5. Quan sát sơ bộ trên v1

Các vấn đề phát hiện trực tiếp trên bản xuất v1 để đưa vào các vòng lặp tinh chỉnh (Mục 6.1):

| # | Quan sát | Màn hình | Heuristic gần nhất |
|---|---|---|---|
| **1** | Dữ liệu cùng một sự kiện không khớp: "Fri, Oct 24 • 7:00 PM", Student Union Amphitheater (S02, S08) so với "October 26, 2026 • 18:00–22:00", Main Stadium (S03–S07). | S02, S08 so với S03–S07 | H4 Consistency and standards |
| **2** | Biểu tượng tab Explore có ít nhất 3 kiểu khác nhau (kính lúp-quả địa cầu, bản đồ, kính lúp dấu cộng). | S02–S05, S06–S07, S10 | H4 Consistency and standards |
| **3** | Nhiều màn hình phụ hiện thanh thương hiệu "Explore" cố định phía trên thanh tiêu đề riêng (hai tầng header); S06–S07 dùng tiêu đề "My Events", S10 chỉ có "Profile". | S03, S04, S05, S08, S09 | H4 Consistency; H8 Aesthetic and minimalist design |
| **4** | Các ô trong form đăng ký S04 để trống dạng placeholder ("Alex Rivera") bắt sinh viên nhập lại từ đầu và khác tên sinh viên trong vé/hồ sơ ("Alex Morgan"). | S04 so với S07, S10 | H4 Consistency; H7 Flexibility and efficiency of use |
| **5** | Trạng thái thông báo chưa đọc ở S09 chỉ được biểu thị bằng chấm tròn màu xanh mà không có nhãn chữ. | S09 | H1 Visibility of system status; WCAG 1.4.1 |
| **6** | Snackbar ở T07 nằm đè lên các thẻ trong khối "Popular this week" tự phát sinh. | T07 | H1 Visibility; H8 Minimalist design |

---

## 6. Vòng lặp tinh chỉnh (Refine) và Phản biện UX bằng AI (Critique)

### 6.1 Bốn vòng lặp tinh chỉnh với AI (Mỗi vòng giải quyết một vấn đề có tên cụ thể)

#### Vòng lặp 1 — Xóa thanh tiêu đề chồng nhau trên màn hình con & chuẩn hóa icon điều hướng dưới
- **Màn hình áp dụng:** S03 Event Detail (và áp dụng quy tắc chung cho các màn hình lồng bên trong).
- **Vấn đề có tên:** Thanh tiêu đề thương hiệu chồng lên thanh App Bar con (2 tầng header) và bộ icon điều hướng dưới không nhất quán (Quan sát #2 và #3).
- **Prompt nguyên văn:**
```markdown
## ROLE
You are a senior mobile UI/UX designer specializing in clean, production-ready Android applications for university students.
## TASK
Revise the Camply screen S03 Event Detail to fix ONE specific problem only: the stacked top bars and inconsistent navigation.
Keep everything else as close to the current version as possible.
## PROBLEM TO FIX
1. Some inner screens show a brand header (logo "C", app name, search, notification bell, avatar) stacked above a second header with a back button and title. Inner screens must have ONLY a back button, a centered or left-aligned title, and optionally one relevant action (e.g. bookmark). No brand logo, no avatar, no search icon on inner screens.
2. The bottom navigation icons change style between screens (for example Explore sometimes shows a magnifier with globe, sometimes a map). Use ONE consistent icon set for the four tabs: Discover, Explore, My Events, Profile, with the same outline style, size, and label on every screen. The selected tab uses the same icon in filled or accent color, not a different icon.
## KEEP UNCHANGED
- DESIGN.md: Inter typography, Electric Blue #2457F5 primary, Lime #C9F46A accent used sparingly, background #F8F9FC, text #171923 and #525866, 16 dp margins, 4 dp spacing scale, 8–16 dp radii.
- Content, event data and layout of the screen, except the header area.
- Frame: Android mobile, 360 × 800 dp, light theme.
## CONSTRAINTS
- Do not add any new features, sections, or screens.
- Do not add a search field to inner screens.
- All tap targets at least 48 × 48 dp.
- Body and content text at least 14 sp; secondary text must reach 4.5:1 contrast against its background.
- Do not use placeholder text colour (#737987) for any readable content text.
- Do not convey status by colour alone.
## OUTPUT
One screen only at 360 × 800 dp.
```
- **Bằng chứng Trước / Sau:**
  - **Trước:** `assets/stitch/s03_event_detail.png` (bản v1 có thanh Explore + Back chồng nhau, tốn diện tích dọc).
  - **Sau:** Bản xuất S03 sau Vòng 1 (đã bỏ hoàn toàn thanh thương hiệu thừa ở đầu trang, chỉ giữ nút Back và Bookmark; thanh đáy cố định nút `Register Now` rõ ràng).
- **Quyết định & Lý do:** **Chấp nhận.** Persona 1 (Nguyễn Minh Anh) dùng điện thoại bằng một tay trong phiên ngắn giữa giờ học; việc loại bỏ thanh header lặp giúp tiết kiệm không gian dọc trên màn hình 800 dp và đẩy thông tin ngày giờ, địa điểm cùng nút `Register Now` vào đúng tầm với của ngón cái. Tuân thủ **H4 (Consistency and standards)** và **H8 (Aesthetic and minimalist design)**.

---

#### Vòng lặp 2 — Giảm nhập liệu lặp lại khi đăng ký sự kiện (Prefill từ hồ sơ)
- **Màn hình áp dụng:** S04 Event Registration.
- **Vấn đề có tên:** Các ô Họ tên, MSSV, Email để trống dạng placeholder bắt sinh viên gõ lại dù hồ sơ S10 đã có sẵn (Quan sát #4).
- **Prompt nguyên văn:**
```markdown
## ROLE
You are a senior mobile UI/UX designer specializing in clean, production-ready Android applications for university students.
## TASK
Revise the Camply screen S04 Event Registration to fix ONE specific problem only: repeated data entry. The student must not retype information the app already knows.
Keep everything else as close to the current version as possible.
## PROBLEM TO FIX
1. Full Name, Student ID and University Email are empty placeholders ("e.g., ..."). They must be pre-filled with the student's saved profile: Alex Morgan, STU-849201, alex.m@university.edu. Show them as real entered values, not placeholder text.
2. Each pre-filled field must remain editable. Add a small "Edit" affordance or let the field be tapped directly. Do not lock the fields.
3. Keep the hint text under the fields only where it adds information (for example "Must match your student ID card"). Remove hints that only repeat the label.
4. Keep the Phone Number field empty and marked optional, because it is not in the saved profile.
5. The bottom navigation must stay hidden on this screen.
## KEEP UNCHANGED
- DESIGN.md: Inter typography, Electric Blue #2457F5 primary, background #F8F9FC, text #171923 and #525866, 16 dp margins, 4 dp spacing scale, 8–16 dp radii.
- Event summary card at the top, the Confirm Registration button, and the back button in the header.
- Frame: Android mobile, 360 × 800 dp, light theme.
## CONSTRAINTS
- Do not add any new features, sections, or screens.
- Do not use placeholder colour (#737987) for any readable content text, including pre-filled values.
- All tap targets at least 48 × 48 dp.
- Body and content text at least 14 sp.
- Do not convey error or status by colour alone.
## OUTPUT
One screen only at 360 × 800 dp.
```
- **Bằng chứng Trước / Sau:**
  - **Trước:** `assets/stitch/s04_event_registration.png` (bản v1 để trống các ô với chữ gợi ý `Alex Rivera`, còn hiện cả thanh thương hiệu trên đầu và Bottom Nav ở dưới).
  - **Sau:** Bản xuất S04 Vòng 2 (đã điền sẵn `Alex Morgan`, `STU-849201`, `alex.m@university.edu` bằng màu chữ chính `#171923`; trường Phone để trống ghi `(optional)`; đã ẩn thanh thương hiệu và Bottom Nav).
- **Quyết định & Lý do:** **Chấp nhận (kèm tinh chỉnh trong Figma).** Việc điền sẵn dữ liệu hồ sơ giúp Persona 1 đạt mục tiêu đăng ký thành công trong ≤ 120 giây bằng một tay (**H7 Flexibility and efficiency of use** và **H5 Error prevention**). Trong Figma, nhóm giữ thêm chữ `(required)` bên cạnh nhãn trường (thay vì chỉ dùng dấu sao đỏ `*` như bản Stitch Vòng 2) và nâng vùng chạm nút Back từ 44 dp lên chuẩn `48 × 48 dp`.

---

#### Vòng lặp 3 — Biểu thị trạng thái thông báo chưa đọc bằng nhãn chữ rõ ràng
- **Màn hình áp dụng:** S09 Notifications.
- **Vấn đề có tên:** Trạng thái chưa đọc trên S09 chỉ phân biệt bằng chấm tròn màu xanh (vi phạm nguyên tắc không truyền đạt trạng thái chỉ bằng màu sắc — Quan sát #5).
- **Prompt nguyên văn:**
```markdown
## ROLE
You are a senior mobile UI/UX designer specializing in clean, production-ready Android applications for university students.
## TASK
Revise the Camply screen S09 Notifications. Change ONE thing only: add a text label to each unread notification so unread status is not conveyed by colour alone.
## EXACT CONTENT TO KEEP (do not change any text, time, or item)
Today:
- Registration Confirmed, 10m ago, "Your Campus Music Night ticket is ready." (unread)
- New Event Available, 2h ago, "AI & Future Careers Workshop is open for registration." (unread)
This Week:
- Event Reminder, Yesterday, "Campus Music Night starts in 3 days." (read)
- Schedule Update, Oct 8, "Photography Walk venue information has been updated." (read)
## CHANGE
1. Only the two items in Today are unread. Give each one a visible "NEW" text label and keep the blue dot as a supporting cue.
2. The "2 new" count in the Today header must equal the number of NEW labels on the screen (2).
3. The two This Week items are read: no label, no dot.
4. Do not repeat any item in another section. Do not change timestamps.
## KEEP UNCHANGED
- DESIGN.md: Inter typography, Electric Blue #2457F5 primary, background #F8F9FC, text #171923 and #525866, 16 dp margins, 4 dp spacing scale, 8–16 dp radii.
- Icons, section titles, "Mark all read" action, card layout.
- Frame: Android mobile, 360 × 800 dp, light theme.
## CONSTRAINTS
- Do not add any new features, sections, or screens.
- Do not use placeholder colour (#737987) for any readable content text.
- All tap targets at least 48 × 48 dp.
- The NEW label is at least 14 sp, with contrast of at least 4.5:1.
- Do not convey status by colour alone.
## OUTPUT
One screen only at 360 × 800 dp.
```
- **Bằng chứng Trước / Sau:**
  - **Trước:** `assets/stitch/s09_notifications.png` (bản v1 chỉ có chấm tròn xanh nhỏ bên cạnh các mục chưa đọc).
  - **Sau:** Bản xuất S09 Vòng 3 (2 thông báo trong nhóm Today có thêm nhãn chữ `NEW` màu xanh trên nền `#EAF0FF` đi kèm chấm xanh, khớp chính xác với tổng số `2 new` ở tiêu đề nhóm; 2 mục trong This Week không có nhãn `NEW`).
- **Quyết định & Lý do:** **Chấp nhận (kèm tinh chỉnh không cắt chữ trong Figma).** Persona 1 thường xem điện thoại ngoài trời nắng gắt nên chấm xanh nhỏ rất dễ bị lóa; việc bổ sung nhãn chữ `NEW` giúp nhận diện ngay lập tức (**H1 Visibility of system status** và **WCAG 1.4.1 Use of Color**). Trong Figma, nhóm cho phép dòng tiêu đề thông báo tự xuống dòng (wrap) để nhãn `NEW` không làm cắt chữ `Registration Confir...`.

---

#### Vòng lặp 4 — Loại bỏ chi tiết thừa trên thẻ Trending và chuẩn hóa dữ liệu lịch sử tìm kiếm (T08)
- **Màn hình áp dụng:** T08 Explore (Idle Search State).
- **Vấn đề có tên:** Chỉ báo số chỗ `"120 spots left"` chỉ xuất hiện đơn lẻ ở một thẻ làm mất tính nhất quán của hàng thẻ ngang, và dữ liệu lịch sử tìm kiếm chưa khớp với kịch bản kiểm thử.
- **Prompt nguyên văn:**
```markdown
## ROLE
You are a senior mobile UI/UX designer specializing in clean, production-ready Android applications for university students.
## TASK
Revise the Camply Explore screen in its idle search state (T08). Make exactly two edits:
1. Remove the "120 spots left" indicator from the Campus Music Night card.
2. In the "Recent searches" list, replace the third item "Photography club" with "Hackathon". Keep its clock icon, its × remove icon, and its position.
Keep everything else exactly as the current version. Do not redesign, restyle, or add anything.
## MUST STAY EXACTLY THE SAME (do not change, add, or remove)
- Header: the title "Explore Events" only. No subtitle, no bell, no other header icon.
- Search field: "Search events or keywords..." with a magnifier icon only. No microphone icon.
- Category chips: All, Music, Workshop, Sports, Arts, in the same order and style. Do not add the "Any time" or "On campus" filter row.
- Trending section: title "Trending on campus", no extra label, badge, or link on the right. No "Details" link on any card.
- Campus Music Night card: badge "Music", date "Mon, Oct 26 • 18:00", venue "Main Stadium". The card's other content and layout stay the same once the indicator is removed.
- Workshop card: unchanged, including its badge, title, date "Mon, Nov 2 • 09:00", and venue "Innovation Hub · Hall A".
- Recent searches: "campus music night", "football tournament", then "Hackathon". Section action reads "Clear".
- Bottom navigation: Discover, Explore, My Events, Profile. The Explore icon is the map icon with Explore selected.
- Layout, spacing, colours, typography, and corner radii: unchanged.
## CONSTRAINTS
- Do not add any new text, label, link, counter, badge, or icon.
- Do not add a device frame, annotation text, or any label on the artboard.
- Do not use placeholder colour (#737987) for any readable content text.
- Do not convey status by colour alone.
- Use the design tokens from DESIGN.md. Do not hard-code colours or sizes.
## OUTPUT
One screen only at 360 × 800 dp.
```
- **Bằng chứng Trước / Sau:**
  - **Trước:** Bản T08 có nhãn `"120 spots left"` nằm đè trên ảnh thẻ *Campus Music Night* và mục lịch sử thứ ba là `"Photography club"`.
  - **Sau:** Bản T08 sau Vòng 4 (`assets/stitch/t08_explore_idle_search.png`) đã gỡ bỏ nhãn `"120 spots left"`, giúp 2 thẻ trong hàng *Trending on campus* đồng nhất chỉ còn nhãn danh mục màu Lime; mục lịch sử thứ ba đổi thành `"Hackathon"` khớp với kịch bản tìm kiếm dẫn sang T06.
- **Quyết định & Lý do:** **Chấp nhận.** Đảm bảo tính nhất quán giữa các thẻ sự kiện cùng cấp (**H4 Consistency and standards**) và tối giản hóa thông tin trên thẻ nhỏ để Persona 1 quét nhanh (**H8 Aesthetic and minimalist design**).

---

### 6.2 Phản biện UX bằng AI (Cần ≥ 5 phát hiện gắn với màn hình)

Toàn bộ prompt phản biện và câu trả lời nguyên văn 22 phát hiện của Claude 3.5 Sonnet được lưu đầy đủ tại Mục 2 và Mục 3 của file `ai/ai-critique-transcript.md` (và `ai/critique-response-claude.md`). Dưới đây là bảng quyết định của nhóm đối với 5 phát hiện trọng tâm từ bản phản biện AI:

| # | Phát hiện (theo AI) | Màn hình | Heuristic / WCAG / Persona | Quyết định | Lý do (gắn với Persona, Heuristic hoặc Ràng buộc thực tế) |
|---|---|---|---|---|---|
| **1** | T07 không có nút Undo sau khi hủy đăng ký (AI #1) | T07 | H3 User control; H9 Error recovery | **Từ chối** | Hủy đăng ký đã có bước phòng ngừa lỗi tại hộp thoại xác nhận **T01** (*Keep Registration* vs *Cancel Registration*). Khi người dùng đã xác nhận hủy ở T01, thao tác hủy được commit lên hệ thống và hệ thống không đảm bảo giữ lại được chỗ/vé để khôi phục qua Undo (Ràng buộc nghiệp vụ, Quyết định **D07**). Persona 1 cần biết trạng thái đăng ký rõ ràng, trung thực. |
| **2** | Tên và mã sinh viên trên vé không khớp hồ sơ (AI #3) | S07 (so với S04, S10) | H4 Consistency; H1 Visibility | **Chấp nhận** | Persona 1 cần tra lại đúng lịch, trạng thái và xuất trình vé khớp thẻ sinh viên khi đến cổng sự kiện. Dữ liệu trên vé S07 phải lấy từ cùng hồ sơ (`Alex Morgan` / `STU-849201`) như S04 và S10. |
| **3** | Ngày và địa điểm của cùng một sự kiện không nhất quán giữa các màn (AI #4) | S01, S02, S04–S08, T08 | H4 Consistency and standards | **Chấp nhận** | Persona 1 cần đọc đúng thời gian và địa điểm trước khi đi để không đến nhầm chỗ hoặc trễ giờ. Ràng buộc: áp dụng một bản ghi sự kiện chuẩn duy nhất (*Campus Music Night — October 26, 2026 • 18:00–22:00 — Main Stadium*) cho mọi màn hình. |
| **4** | Màn loading không có thông báo chờ lâu hoặc lối thoát khi mạng yếu (AI #7) | T03 | H1 Visibility; H9 Error recovery | **Chỉnh sửa** | Persona 1 thường dùng ứng dụng dưới kết nối Wi-Fi trường không ổn định. Tái sử dụng trạng thái lỗi có sẵn kèm nút thử lại (`Retry`) hoặc quay lại (`Back`) khi quá thời gian chờ, không đẻ thêm tính năng mới. |
| **5** | Mã QR ở S07 cần được ghi rõ là bản demo giao diện (AI #11) | S07 | H1 Visibility; yêu cầu `DESIGN.md` | **Chấp nhận** | `DESIGN.md` yêu cầu mã QR giả lập phải được nhận diện rõ là bản demo giao diện. Giữ dòng chú thích *"Demonstration pass • Valid student ID required upon entry"* ngay bên dưới mã QR trên thẻ vé S07. |

---

### 6.3 Quyết định trên các chi tiết đề xuất của Stitch cho màn T08

| # | Chi tiết trong đề xuất Stitch | Quyết định | Lý do (Persona / Heuristic / Ràng buộc) | Phản ánh trong Figma |
|---|---|---|---|---|
| **1** | Cấu trúc: thẻ Trending ảnh ngang + Recent searches | **Chấp nhận** | Persona 1 tìm sự kiện bằng một tay trong phiên ngắn: thẻ ngang cho thấy nhiều sự kiện trong một lần cuộn. **H6 (Recognition rather than recall)**: lịch sử tìm kiếm giảm việc phải gõ lại từ khóa. | T08 trong Page 03 có cấu trúc này. |
| **2** | Link chữ `"Details ›"` trên mỗi thẻ sự kiện | **Từ chối** | **H8 (Aesthetic and minimalist design)**: cả thẻ đã chạm được để mở trang chi tiết S03, thêm link riêng là dư thừa. Ngoài ra vùng chạm chữ nhỏ khó đạt chuẩn `48 × 48 dp` khi dùng một tay. | Thẻ trong T08 và S02 không có link Details; toàn bộ thẻ là vùng chạm mở S03. |
| **3** | Phụ đề `"Find what's happening around campus"` | **Từ chối** | **H8 (Minimalist design)**: phụ đề lặp ý với tiêu đề `"Explore Events"`, chiếm mất một dòng trên màn hình 800 dp và đẩy danh sách sự kiện xuống thấp hơn. | Header S02/T08 chỉ giữ tiêu đề chính. |
| **4** | Bộ đếm số chỗ còn lại (`"120 spots left"`) chỉ nằm ở 1 thẻ | **Chỉnh sửa** | Đã gỡ bỏ trên thẻ nhỏ ở Vòng lặp 4 để giữ tính nhất quán giữa các thẻ trong cùng một hàng (**H4 Consistency**); thông tin số chỗ chỉ hiển thị ở màn chi tiết S03 khi dữ liệu sự kiện thực sự hỗ trợ. | Thẻ trên T08 chỉ hiển thị nhãn danh mục màu Lime đồng nhất. |
| **5** | Thiếu hàng bộ lọc phụ (`Any time`, `On campus`) khi so với S02 | **Từ chối** bản thiếu bộ lọc | **H4 (Consistency and standards)**: T08 là trạng thái tìm kiếm trên S02 nên cần duy trì mô hình điều khiển đồng nhất với S02 trên Figma. | Đã đồng bộ cấu trúc header tìm kiếm trên Figma Page 03. |