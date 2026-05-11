# Problem Frame: CS team đốt 15h/tuần "đọc lại lịch sử khách" trước mỗi cuộc gọi gia hạn

> Framed: 2026-05-14 (ví dụ Tony chuẩn bị sẵn — Path B demo) · Owner: founder, công ty SaaS B2B 60 người, cuối Series A
>
> **Bài học của ví dụ này:** triệu chứng rõ ràng, đau, giá trị cao — và lần này nút thắt THẬT là đọc/tổng hợp (đúng việc của AI). Nhưng giải pháp KHÔNG phải "hỏi Claude từng lần" — là DỰNG MỘT MÔI TRƯỜNG: skill + MCP + ranh giới rõ. Đây là cái slide 7 (Path B, hướng ✅ + môi trường rõ) nên dùng — hoặc cặp với example-1.

## The 7-field canvas

### 1. Symptom — what you can see
Trước mỗi cuộc gọi gia hạn hợp đồng (renewal call), Customer Success Manager (CSM) phải **tự đọc lại toàn bộ lịch sử khách**: ticket support 12 tháng, email threads, ghi chú CRM, usage data, hóa đơn, các lần escalate. Trung bình **45–60 phút chuẩn bị/cuộc gọi**. ~20 renewal call/tuần across team = ~15–18h/tuần "đọc lại". CSM kêu "không có thời gian làm việc thật sự là nói chuyện với khách."

### 2. Who feels it + how often
4 CSM. ~20 renewal call/tuần = ~5/người/tuần × ~50 phút = ~4h/người/tuần chỉ để chuẩn bị. Ngoài renewal còn QBR (quarterly business review) — thêm ~8 buổi/quý, mỗi buổi chuẩn bị ~2h.

### 3. Current workaround
CSM mở 5 tab: Zendesk (ticket), HubSpot (CRM notes + email), Stripe (billing), Mixpanel (usage), một Google Doc "account brief" tự gõ tay (thường lỗi thời). Đọc, scroll, copy vài thứ vào Doc, vào cuộc gọi. Sau cuộc gọi, hiếm khi update Doc → lần sau đọc lại từ đầu.

### 4. Root-cause hypothesis
Thông tin về khách **phân tán across 5 hệ thống**, không ai tổng hợp. Mỗi lần cần "bức tranh khách" thì phải dựng lại bằng tay. Đây không phải thiếu người, không phải incentive — là một việc đọc/tổng hợp lặp đi lặp lại mà chưa ai tự động hóa. (Lưu ý: data KHÔNG bẩn — nó nằm rải rác nhưng sạch và có API. Đây không phải data-cleanup project.)

### 5. Cost of doing nothing (next 12 months)
4 CSM × ~4h/tuần × 48 tuần = ~768h/năm = ~0.4 FTE đốt vào "đọc lại". Với CSM lương ~70.000$/năm → ~28.000$/năm chi phí trực tiếp. CỘNG: chất lượng renewal call thấp hơn (CSM mệt, chuẩn bị vội) → ảnh hưởng net revenue retention. NRR hiện 102%; mỗi 1 điểm NRR ≈ 60.000$ ARR. Nếu chuẩn bị tốt hơn đẩy NRR lên 105% → ~180.000$ ARR. **Tổng giá trị tiềm năng: 200.000$+/năm.** Rất đáng làm.

### 6. What "solved" looks like in 30 days
CSM mở MỘT chỗ, gõ tên khách, nhận **một bản brief 1 trang trong 60 giây**: tình trạng hợp đồng, usage trend (tăng/giảm + sản phẩm nào), 3 ticket gần nhất + cái nào còn mở, các lần escalate, hóa đơn quá hạn, "điểm rủi ro" + lý do, 3 điểm nên hỏi trong cuộc gọi. Thời gian chuẩn bị: 45 phút → dưới 10 phút.

### 7. Company context
- **Size:** 60 người · **Stage:** cuối Series A · **Industry:** SaaS B2B (phần mềm vận hành nhà hàng)
- **Tools we run:** Zendesk (support), HubSpot (CRM), Stripe (billing), Mixpanel (product analytics), Google Workspace, Slack, Linear. Có team dev 8 người. Tất cả các tool trên đều có API.

---

## Solution directions

### Direction A — Sửa quy trình: thuê 1 ops analyst gõ brief tay
Một người chuyên đọc 5 hệ thống và viết brief cho CSM trước mỗi call.
- **Real bottleneck:** đúng — đọc/tổng hợp. Nhưng người này sẽ làm chính xác việc máy làm tốt: đọc API output, tổng hợp theo template. 768h/năm = ~0.4 FTE → thuê 1 người part-time.
- **Verdict:** ⚠️ pursue with caveat — chạy được, nhưng tốn lương + người đó cũng chậm hơn máy + phụ thuộc một người. Đây là lựa chọn "nếu không muốn build gì". Founder không muốn hire (đang giữ headcount).

### Direction B — Build một AI ENVIRONMENT: skill `/account-brief` + MCP nối 4 hệ thống *(chosen)*
Dev build một MCP server (hoặc dùng connector sẵn có) cho Zendesk + HubSpot + Stripe + Mixpanel. Build một skill `/account-brief {tên khách}` → skill gọi 4 nguồn, tổng hợp theo template cố định, ra brief 1 trang. CSM chạy trong Cowork hoặc Claude chat. Sau này: thêm trigger tự động sinh brief đêm trước mỗi renewal call đã lên lịch (Routine).
- **Real bottleneck:** đọc + tổng hợp across nguồn — *đúng việc Claude giỏi.*
- **Repetition:** ~20/tuần + QBR — thừa đủ để build (gate Q2: pass mạnh).
- **Input availability:** 4 hệ thống đều có API, data sạch. KHÔNG phải data-cleanup project. (gate Q3: pass.)
- **Output owner + risk:** CSM dùng brief để chuẩn bị nói chuyện — không gửi khách, không pháp lý. Sai sót thấp rủi ro; CSM vẫn đọc qua. Nhưng: brief KHÔNG được tự động ra quyết định "khách này sắp churn, hạ giá đi" — đó là phán đoán của CSM. (gate Q4–5: brief = trợ lý đọc, không phải người quyết.)
- **What Claude would do here:** gọi 4 API, lọc 12 tháng dữ liệu xuống cái quan trọng, viết brief theo template, tính "điểm rủi ro" thô (usage giảm + ticket mở + hóa đơn trễ) — và *gắn cờ* để CSM xem, không kết luận.
- **What stays with a human:** quyết định chiến lược cho cuộc gọi (có upsell không, có nhượng bộ gì, có escalate lên founder không) — CSM, dựa trên brief + hiểu biết quan hệ. Không tự động hóa.
- **Verdict:** ✅ pursue — đây là hướng. Build chuẩn: MCP trước (dev, ~1 tuần cho 4 connector hoặc dùng connector có sẵn), skill sau (~2 ngày), test với 1 CSM 1 tuần, rollout.

### Direction C — Mua một "customer 360" SaaS (Catalyst, Vitally, Gainsight…)
Có sản phẩm sẵn làm việc này.
- **Verdict:** ⚠️ pursue with caveat — chạy được, nhưng: 20–60k$/năm license, setup 2–3 tháng, và bạn vẫn phải config nó đọc đúng những gì bạn cần. Cân nhắc nếu không có dev rảnh. Với team dev 8 người + chỉ cần 4 connector + 1 skill, build (Direction B) rẻ hơn và đúng nhu cầu hơn. Đánh giá lại nếu Direction B kéo dài quá 3 tuần.

## Environment design (Direction B)
- **Surface:** **skill + MCP** — `/account-brief` (skill, dùng được trong Cowork bởi CSM không kỹ thuật) + MCP server nối Zendesk/HubSpot/Stripe/Mixpanel (dev build, hoặc connector sẵn). Sau: bọc thành **Routine** chạy đêm trước mỗi renewal call.
- **Connections:** Zendesk (ticket) · HubSpot (CRM notes, email, contract status) · Stripe (billing/overdue) · Mixpanel (usage trend) · lịch renewal call (để Routine biết khi nào sinh brief).
- **Reusable skill:** `/account-brief {tên khách}` → brief 1 trang theo template cố định: hợp đồng · usage trend · 3 ticket gần nhất + open · escalations · billing flags · risk score + lý do · 3 câu nên hỏi.
- **Boundary:** Claude đọc + tổng hợp + gắn cờ rủi ro. Claude KHÔNG quyết: upsell/nhượng bộ/escalate — đó là CSM. Brief luôn được CSM đọc qua trước cuộc gọi (không "tự động hành động").
- **Still TBD:** dùng MCP tự build hay connector có sẵn cho từng tool (dev đánh giá tuần 1); risk-score formula cần CSM góp ý 2-3 vòng trước khi tin.

## Verdict
Đây là vấn đề AI thật — nút thắt là đọc/tổng hợp, lặp đủ nhiều, data có sẵn, giá trị 200k$+/năm. Và giải pháp đúng KHÔNG phải "CSM hỏi Claude từng lần" — là **dựng một môi trường một lần**: MCP nối 4 hệ thống + skill `/account-brief` + ranh giới rõ (Claude tổng hợp, CSM quyết). Bắt đầu từ Direction B: dev làm MCP trước, skill sau, test với 1 CSM 1 tuần. Đánh đổi bạn chấp nhận: ~1.5 tuần dev time bây giờ (đổi lấy 0.4 FTE/năm vĩnh viễn + NRR tốt hơn) — và kỷ luật giữ ranh giới: cái brief tốt đến mấy cũng không thay phán đoán của CSM về cuộc gọi.

---

> **Cách dùng file này trong demo (slide 7):** đọc qua 7 ô (nhanh) → chỉ vào gate verdict: ✅ vấn đề AI thật (khác example-1!) → rồi chỉ vào phần "Environment design": "thấy chưa — nó không nói 'dùng AI'. Nó nói: dựng skill `/account-brief` + MCP nối 4 hệ thống + ranh giới 'Claude tổng hợp, CSM quyết'. Cụ thể. Một lần. Cả team CS dùng mãi. Đó là khác biệt giữa 'use case' và 'môi trường'."
