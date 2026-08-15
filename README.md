# BilaScript

**BilaScript** là ngôn ngữ lập trình thử nghiệm được hiện thực như một **frontend/compiler AST-first hướng CVNSS4.0**. Mốc kiến trúc **v4.0.0** đọc mã `.bila`, phân tích lexer/parser/AST, semantic-evidence, chuẩn hóa strict và sinh **JavaScript + Source Map** để chạy trên Browser/Node.

> **Triết lý:** BilaScript làm chủ frontend; JavaScript đảm nhiệm backend/runtime.

## Kiến trúc

```text
*.bila
  ↓
Lexer / Semantic Token IDs
  ↓
Parser → Bila AST
  ↓
Symbol / Type Evidence
  ↓
Strict Normalizer
  ↓
JavaScript Code Generator + Source Map
  ↓
Browser / Node / JavaScript Engine
```

## Ưu điểm & công dụng

- **Structure-first:** AST giữ nesting và quan hệ cú pháp, an toàn hơn thay chuỗi/regex mù.
- **Evidence-driven:** strict mode chỉ hạ alias khi có bằng chứng symbol/type phù hợp.
- **Zero-cost backend:** mapping 1:1 sinh JavaScript trực tiếp, không cần runtime translator riêng.
- **Tận dụng JavaScript:** chạy trên Browser/Node và tiếp cận hệ sinh thái Web/npm.
- **Offline:** compiler core không phụ thuộc AI, API hay Internet.
- **Tooling-ready:** AST, diagnostics và Source Map tạo nền cho IDE/LSP, debug và kiểm thử.

**Công dụng:** học/nghiên cứu compiler, viết mã hướng CVNSS4.0, biên dịch sang JavaScript, xây playground và thử nghiệm tooling ngôn ngữ.

## Lộ trình sau v4.0.0

| Giai đoạn | Trọng tâm |
|---|---|
| **0–3 tháng** | Ổn định AST/semantic/tests; làm BilaScript → JavaScript đáng tin cậy hơn |
| **4–6 tháng** | Backend abstraction; thử nghiệm Python/C#/JSON-IR theo semantic subset |
| **7–9 tháng** | LSP + VS Code/editor tooling: diagnostics, completion, hover, symbols |
| **10–12 tháng** | AI adapter trên AST; AI là lớp hỗ trợ, không phải dependency của core |
| **Năm 2+** | Rust/WASM/native backend và tích hợp input method/OS khi semantics ổn định |

> **Roadmap không phải danh sách tính năng của v4.0.0.** Multi-target, LSP, AI và WASM chỉ được xem là đã có khi source tương ứng được hiện thực và kiểm thử.

## Lịch sử phiên bản

- **v1.x** — vocabulary CVNSS4.0 trên dòng Rhino/Babylscript; hình thành Bila mode.
- **v2.0** — grammar tương thích JavaScript, profiles và chuẩn hóa vocabulary.
- **v3.0** — tách frontend với lexer/parser/AST/semantic; JavaScript trở thành backend.
- **v3.5** — Semantic IDs, receiver-safe aliases, Source Map và zero-cost contract.
- **v4.0.0** — evidence-required strict lowering, diagnostics, AST-first hardening và kiến trúc modular.
- **5.0.0 DevKit Preview** — playground/compiler AST-first thử nghiệm; không đồng nghĩa toàn bộ roadmap sau v4 đã hoàn tất.

## Giới hạn hiện tại

BilaScript v4 không tuyên bố tương thích toàn bộ ECMAScript/Test262 và hệ type/evidence được thiết kế gọn hơn TypeScript. Python/C#/WASM và các backend khác là hướng mở rộng sau khi semantic model ổn định.

---

**BilaScript** · AST-first · CVNSS4.0-oriented frontend · JavaScript backend · MIT
