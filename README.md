# Camply – Campus Event Discovery & Registration App

**Môn học:** PRM323 — Cross-Platform Application Development (Lab 2: Thiết kế UI/UX có hỗ trợ AI)

## 1. Thành viên nhóm (Team Members)
- Nguyễn Ngọc Phương Đông
- Nguyễn Thị Tú Anh
- Trần Đình Phúc
- Dương Minh Kiệt

## 2. Chủ đề & Persona
- **Chủ đề:** Ứng dụng di động khám phá và đăng ký sự kiện trong khuôn viên trường đại học dành cho sinh viên 18–24 tuổi (Android-first, 360 × 800 dp).
- **Persona một dòng:** **Nguyễn Minh Anh** — Sinh viên đại học năm 2 năng động, muốn nhanh chóng khám phá, đăng ký và tra cứu lại sự kiện trong trường bằng một tay vào giờ nghỉ giữa các tiết học dưới ánh nắng ngoài trời và mạng chập chờn.

## 3. Link Figma
- **Figma File (6 Pages & Interactive Prototype):** (https://www.figma.com/design/bXMjeQsAlst4tbouqjroGj/Campus-Event-App?node-id=189-503&t=RkNP0jgkxPcqX1SJ-0)

## 4. Công cụ AI đã sử dụng
| Công cụ AI | Mục đích sử dụng | Giai đoạn |
|---|---|---|
| **Google Stitch** | Tạo giao diện UI ban đầu (v1) cho 10 màn hình chính (S01–S10) và 7 biến thể trạng thái (T01–T07), thực hiện 4 vòng lặp tinh chỉnh (Refine) | Generate & Refine |
| **Claude 3.5 Sonnet (Anthropic)** | Đánh giá và phản biện UI theo 10 Usability Heuristics của Nielsen, tiêu chí Accessibility (WCAG) và mức độ phù hợp với Persona | Critique |
| **Claude (Anthropic)** | Hỗ trợ tổng hợp tài liệu log, chuẩn hóa bảng đặc tả màn hình và tài liệu Flutter Handoff | Documentation & Handoff |

## 5. Bản đồ sản phẩm trong Repository (Deliverables Map)
```text
prm323-lab2-camply/
├── README.md                       # Tổng quan dự án, link Figma, khai báo AI và bản đồ thư mục
├── ux/
│   ├── persona.md                  # Hồ sơ người dùng mục tiêu, bối cảnh, pain points & tiêu chí đo lường
│   └── user-flow.md                # Kiến trúc thông tin (IA), các sơ đồ User Flow (Mermaid) & bảng ánh xạ
├── design/
│   ├── DESIGN.md                   # Hệ thống Design Tokens (màu sắc, chữ, khoảng cách, quy tắc component)
│   ├── screen-spec.md              # Đặc tả chi tiết 10 màn hình chính (S01–S10) và các trạng thái (T01–T07)
│   └── design-decisions.md         # 8 quyết định thiết kế quan trọng kèm lý do & Checklist Accessibility
├── ai/
│   ├── ai-design-log.md            # Nhật ký toàn bộ Prompt nguyên văn, kết quả v1, 4 vòng lặp và phản biện AI
│   ├── ai-critique-transcript.md   # Bản ghi nguyên văn phiên chạy phản biện UX bằng AI
│   └── critique-response-claude.md # Chi tiết câu trả lời phản biện từ Claude Sonnet
├── assets/
│   ├── stitch/                     # Ảnh chụp màn hình mọi phiên bản do Google Stitch tạo (v1 & các vòng lặp)
│   └── figma/                      # Ảnh PNG xuất từ các màn hình hoàn thiện cuối cùng trên Figma
└── handoff/
    └── flutter-handoff.md          # Đặc tả kỹ thuật 6 mục/màn hình và bảng ánh xạ Token/Widget cho Flutter