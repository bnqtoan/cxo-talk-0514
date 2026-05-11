---
type: workshop-slide-outline
workshop: workshop-20260514-cxo-club
session: talk (20-min slot in a 2-hr club session)
status: draft-for-review
created: 2026-05-11
duration: 20 min on stage (pre-talk setup happens earlier in the 2-hr session)
target_count: 12 slides — cover · setup (pre-slot) · 1 hook · 2 hammer · 3 five-nail-shaped · 4 gate · 4b use-case menu · 5 use-case→environment · 6 five-surfaces+4-elements · 7 demo · 8 close · thank-you
build_status: >
  DONE. slides.html (12 slides, brand palette + dark gradient covers, Esc grid + S toggle). 7 Codex images generated (slides 1,2,3,5,8 wired; 4 & 6 kept as HTML for legibility — gate-card + five-surfaces PNGs sit in images/ as optional alternates). Examples: examples/example-1 (❌ sửa quy trình) + example-2 (✅ dựng môi trường), linked on slide 7. Prompt: no Gist — repo file via amy short link.
deployed: https://bnqtoan.github.io/cxo-talk-0514/slides/slides.html · repo github.com/bnqtoan/cxo-talk-0514 · prompt go.bnqtoan.workers.dev/dinh-vande · QR go.bnqtoan.workers.dev/qr/dinh-vande (embedded live in deck)
open_items: run the phone prompt once yourself (sanity check; examples are backup). That's it.
reference_deck: workshops/workshop-20260504-ai-orchestration-product-team/session-1/slides.html
brand: Anthropic / Claude brand guidelines (session-1 deck already encodes it)
design_principles:
  - one idea per slide (more than one → two slides)
  - speaker notes ≠ slide content (script in .stage-strip, hidden with S)
  - image > words where the image carries the idea
  - 22pt minimum body, breathing room, orange used sparingly (brand restraint)
  - presenter chrome kept: Esc grid · S stage-toggle · F fullscreen · @media print
  - images generated out-of-band via Codex (ChatGPT Plus), dropped into images/
---

# CXO Club — "Định nghĩa vấn đề trước khi với tay lấy AI" · Slide Outline

> Design intent: slides are **for the audience to look at and remember** — not for Tony to read off. Script lives in `.stage-strip` (toggle with `S`). Each slide = ONE idea + image. 20 min, peer-to-peer founders club, no pitch. VN Southern dialect. **Internal — no "pay-back / I owe the mentor" framing.**
>
> The named anti-pattern that threads the whole talk: **"đi tìm vấn đề cho giải pháp"** — bạn thấy AI làm được gì đó hay → đi tìm một vấn đề trong công ty để nhét nó vào. Solution in search of a problem. = cầm búa đi tìm đinh. The talk reverses it: start from the problem, gate it, then design the environment.
>
> Arc: **(1) the hook + the hammer → (2) is it a nail? — the 5-question gate → (3) don't hammer case-by-case: design an environment → (4) dissect a real problem / example + close.**
>
> Two photograph-it slides: **#4 (5-question gate)** and **#6 (5 surfaces + 4 environment elements)** — make these the most legible.

## Visual system

> Forked from `workshop-20260504/session-1/slides.html`, which already IS Anthropic-branded. Keep its `<style>` + `<script>` verbatim; only adjust deck title/meta and slide content. No recolour needed.

- **Palette (brand):** dark `#141413` · light/cream `#faf9f5` · mid `#b0aea5` · light-gray `#e8e6dc` · **orange `#d97757`** (the single accent — kickers, one underlined word per slide, card top-borders; used sparingly) · blue `#6a9bcc` + green `#788c5d` (rare secondary, e.g. ✅/❌ tinting). No red.
- **Fonts:** headings = Be Vietnam Pro (VN support) / Poppins fallback · body = Lora / Be Vietnam Pro fallback · mono = JetBrains Mono (kickers, slide numbers, code).
- **Accent treatment:** orange `.slide-kicker` (small uppercase mono) above each h1; ONE key word per h1 with an orange underline (`.orange-underline` — add if not in session-1, mirror session-2's `.teal-underline` recoloured). Big-quote slides: large display-weight, centered.
- **Layout blocks in use:** `.cmp2`/`.cmp3` (the 5-nail-shaped-things, the demo dissection), `.doors.n5` (the 5 surfaces), a small checklist block (4 environment elements; gate's 5 questions), `.bigquote` (the close takeaways), `.demo-frame` (slide 7 — Tony switches to screen), `.setup`/QR layout (slide 0), `.image-placeholder` everywhere.
- **Image style:** Anthropic-brand-consistent flat editorial illustration on cream `#faf9f5` ground — clean line work, restrained orange accent, no faces, dignified. (NOT the Moleskine hand-drawn look — this deck is brand-aligned. Every image prompt below names this.)
- **Interaction patterns:** distinction → `.cmp` compare · steps → checklist reveal · anchor → big quote · the "5 surfaces" → `.doors.n5` · hands-on/QR → setup slide · presenter: `Esc`/`G` grid · `S` stage cues · `F` fullscreen.

---

## Slide-by-slide map (20 min on stage; slide 0 used before the slot)

> The **Speaker note hook** column = the `.stage-strip` on that slide. Separate from the Slide column on purpose.

| #  | Slide                                        | Type        | Image / asset                                                                 | Speaker note hook (`.stage-strip`)                                                                 |
| -- | -------------------------------------------- | ----------- | ----------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| 0  | **Setup — quét QR, chạy thử**                | setup       | Large QR (Gist link) + short URL text below. Small icon: phone + sparkle.      | ▸ PRE-TALK (lúc mọi người đến / nghỉ). "Quét → mở app Claude (free OK) → dán prompt → 7 câu về MỘT vấn đề đau nhất → giơ tay khi xong." Đi quanh giúp ai kẹt. KHÔNG ép. |
| 1  | **Hook — bạn đang đi tìm vấn đề cho giải pháp** | hero     | Img #1 — a figure (no face, just posture) walking along a wall holding a hammer, peering at the blank wall, searching for something to hit. Caption-style subtext: "solution in search of a problem." | ▸ Beat 1 · ~4 min. Mở thẳng: "Bạn thấy AI làm được gì đó hay → rồi đi tìm một vấn đề trong công ty để nhét nó vào. Đó là cầm búa đi tìm đinh." Để câu đó đứng yên một nhịp. Cả buổi nay mình đảo chiều: bắt đầu từ vấn đề, không từ giải pháp. |
| 2  | **Cây búa — Claude làm được gì**             | visual-diagram | Img #2 — a hammer with a clean label band: "đọc · viết · phán đoán · tổng hợp". | ▸ Beat 1 cont. Trước khi đảo chiều — cây búa: Claude giỏi 4 thứ này. Mạnh, rẻ, ai cũng cầm. Chính vì rẻ nên ai cũng đang vung bừa. "Phần khó: (a) đập vào đâu, (b) đừng đập từng cái một." Không demo — chỉ nói. → pivot sang Beat 2. |
| 3  | **5 thứ trông giống đinh**                   | cmp / 5-up  | Img #3 — five small objects in a row, each labeled: con ốc (quyết định thiếu) · ghế trống (người thiếu) · lò xo (incentive sai) · đống giấy lộn xộn (data chưa có) · biển giá (giá sai). Hammer crossed-out over each. | ▸ Beat 2 · ~6 min. Búa KHÔNG đóng được 5 thứ này — đập vào là hỏng. 1 mini case 30s: "founder muốn build AI X" → hóa ra vấn đề [Y]. → dẫn sang slide gate. |
| 4  | **5 CÂU GATE** (photograph-it #1)            | checklist   | Img #4 — a clean numbered checklist card, 5 lines, orange numerals. Big, legible from the back. | ▸ Beat 2 cont. **Chiếu TO. Đọc cả 5 câu thành tiếng.** Chốt: "Rớt 1 trong 5 → đừng đập. Cái prompt anh/chị quét lúc nãy hỏi anh/chị đúng 5 câu này." Để slide đứng yên một nhịp. |
| 5  | **Use case → Môi trường**                    | side-by-side-compare | Img #5 — LEFT: a person hammering scattered single nails one by one (tired). RIGHT: a tidy set-up workbench, tools mounted, ready. Caption: "Đừng đập từng cái. Dựng chỗ làm việc một lần." | ▸ Beat 3 · ~7 min (ngang Beat 2). Cái bẫy thứ hai: qua gate rồi → hỏi Claude từng việc → tuần sau quay lại. Đảo: use case = "làm cái này cho tôi"; môi trường = dựng MỘT LẦN cho cả một LỚP. Việc của founder: hiểu PATTERN + CAPACITY. |
| 6  | **5 BỀ MẶT + 4 thứ môi trường** (photograph-it #2) | doors.n5 + checklist | Img #6 — five labeled "doors"/drawers: Chat · Cowork · Skill+MCP · Code · Routine, each with a one-line "khi nào". Below: a 4-item checklist: bề mặt · kết nối · skill · ranh giới. | ▸ Beat 3 cont. **Chiếu TO.** Đi nhanh 5 bề mặt — một dòng mỗi cái: Chat (một lần, không build) · **Cowork** (agentic, không code, cho người không kỹ thuật — mặc định cho phần lớn use case sếp) · **Skill+MCP** (build một lần, cả team bấm — đòn bẩy cao nhất) · Code (dính code/repo, nơi build skill/MCP) · Routine (chạy không cần ai có mặt — build thủ công trước). Rồi 4 thứ: chưa đủ 4 → vẫn case-by-case. → nối về demo. |
| 7  | **Mổ xẻ một vấn đề thật** (live / màn hình)  | demo        | Just a frame border + "● TRỰC TIẾP" tag. Tony switches to the screen (problem file from the room, OR his prepared example). | ▸ Beat 4 · ~3 min. **Quyết A/B trong 5 giây: ai giơ tay → A (đọc file của họ). Không ai → B (ví dụ Tony chuẩn bị sẵn).** Điểm nhanh: gate verdict (có ❌?) → môi trường đề xuất (bề mặt nào, đủ 4 thứ chưa). Khoảnh khắc vàng: "AI vừa bảo anh/chị đừng dùng AI cho phần này" HOẶC "không phải 'dùng AI' — mà là 'dựng Cowork với 3 kết nối + một skill'. Cụ thể. Một lần. Dùng mãi." |
| 8  | **Chốt + link**                              | big-quote   | Img #7 — a nail driven cleanly into wood; the screws/pebble/spring set aside in a small tray. Below: QR again + short URL. | ▸ Beat 4 cont. 3 câu: (1) Đừng đi tìm vấn đề cho giải pháp — đi từ vấn đề. Ai cũng có búa; lợi thế là biết đập vào đâu, và đừng đập từng cái một. (2) Vấn đề lớn nhất thường KHÔNG phải vấn đề AI — chạy gate trước. (3) Nếu đúng là vấn đề AI: **dựng môi trường** — bề mặt + kết nối + skill + ranh giới. Một lần. Hành động: "Bookmark Gist. Tối nay chạy cho vấn đề lớn nhất. Ai pitch AI trong công ty → dán vào gate trước khi duyệt tiền. Câu hỏi cụ thể: gặp mình lúc nghỉ, 60s." |

---

## Image-generation list (for Codex)

> Generate via Codex CLI (`codex exec -i ref.png -- "prompt"`, ChatGPT Plus — no API key). Output in `~/.codex/generated_images/`; rename → drop into `slides/images/` as `slide-NN-slug.png`. Placeholders auto-activate (`:has(img)`).
> **Style for EVERY prompt:** "Anthropic/Claude-brand flat editorial illustration, clean line work on warm cream `#faf9f5` background, restrained single orange `#d97757` accent, no faces, dignified and calm, generous whitespace." (NOT hand-drawn / Moleskine — this deck is brand-aligned.)

| Slide # | Image needed                              | Prompt seed                                                                                                                   |
| ------- | ----------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| 1       | Hero — searching for a problem to hit     | "{style} A figure shown only from behind / in posture (no face), walking slowly along a long blank wall while holding a claw hammer raised slightly, head tilted as if scanning the wall for something to hit. The wall is empty — there is no nail. Quiet, slightly absurd, not mocking. Subtext idea: 'solution in search of a problem.'" |
| 2       | The hammer — what Claude does             | "{style} A single claw hammer, with a clean horizontal label band beneath it reading 'đọc · viết · phán đoán · tổng hợp' in a tidy sans-serif. Minimal, almost diagram-like." |
| 3       | 5 things that look like nails             | "{style} Five small objects in a neat horizontal row, each with a tiny crossed-out hammer icon above it: (1) a wood screw, (2) an empty office chair, (3) a coiled spring, (4) a messy stack of loose papers, (5) a price-tag sign. Small handwritten-style labels under each in Vietnamese: 'quyết định thiếu', 'người thiếu', 'incentive sai', 'data chưa có', 'giá sai'. Calm, instructional." |
| 4       | The 5-question gate card                  | "{style} A single clean checklist card on cream, titled in Vietnamese 'AI có phải đúng công cụ?', with 5 numbered lines (numerals in orange), each line a short Vietnamese question. Designed to be readable from across a room — large type, lots of air. Almost a UI card, not decorative." |
| 5       | Use case vs environment                   | "{style} Split composition. LEFT half: a figure (no face, just posture) hammering scattered single nails into a wall one at a time, looking weary, nails everywhere. RIGHT half: a tidy workbench with tools mounted on a pegboard, well-organized, ready to use. A thin divider between. Caption beneath in Vietnamese handwriting-style: 'Đừng đập từng cái. Dựng chỗ làm việc một lần.'" |
| 6       | 5 surfaces + 4 environment elements       | "{style} A row of five labeled drawers or doors, each with a heading and a one-line caption: 'Chat — việc một lần', 'Cowork — agentic, không code', 'Skill + MCP — build một lần, cả team dùng', 'Code — dính code/repo', 'Routine — chạy không cần ai có mặt'. Below the row, a small 4-item checklist titled 'Một môi trường đã thiết kế:' with items 'bề mặt · kết nối · skill · ranh giới'. Clean, diagrammatic, readable from a distance." |
| 7       | (no image — demo frame, live screen)      | — |
| 8       | Closing — nail driven home                | "{style} A single nail driven cleanly and fully into a piece of wood, flush. Beside it, a small tray holding the screws/pebble/spring from slide 1 — set aside, not discarded. Resolved, calm. Below, leave clear space for a QR code overlay." |

7 images · ~3 min each via Codex · ~20 min total.

---

## Build checklist (phase 2 — after Tony approves this outline)

- [ ] Outline approved
- [ ] Fork `workshop-20260504/session-1/slides.html` → `slides/slides.html`: keep `<style>` + `<script>` verbatim, update `<title>`/`<meta>`/hero meta line, add `.orange-underline` class if absent (recolour of session-2's `.teal-underline`)
- [ ] 9 `<section class="slide">` (0–8), each with `<!-- type: ... -->` comment
- [ ] `.image-placeholder` on slides 1–6, 8 with `data-image-prompt` from the list above
- [ ] `.stage-strip` on EVERY slide — beat # + timing + the cue (copy the Speaker note hook column)
- [ ] Slide 0 (setup) and slide 8 both carry the QR + short URL — needs the Gist created first (see talk TODO)
- [ ] Slide 4 and slide 6 made maximally legible (these are the photograph-it slides)
- [ ] Presenter chrome intact: auto-numbering, `#slide-N` deep links, `Esc` grid, `S` toggle, `F` fullscreen, `@media print`
- [ ] No unverified facts — the 5-surface descriptions trace to `40-artifacts/skills/problem-frame/references/solution-map.md` (already vault-grounded via the 2026-05-09 + 2026-05-03 research)
- [ ] images/ list handed to Codex (phase 3, out-of-band) — don't block the deck on it; placeholders are fine for rehearsal
