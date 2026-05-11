# Problem Frame: Sales đang "mất deal vì chậm" — báo giá tay, mỗi cái 2 ngày

> Framed: 2026-05-14 (ví dụ Tony chuẩn bị sẵn — Path B demo) · Owner: founder, công ty SaaS B2B 35 người, Series A
>
> **Bài học của ví dụ này:** triệu chứng nghe phức tạp ("mất deal, sales chậm, quy trình rối") → nhưng sau khi framing, nút thắt thật ĐƠN GIẢN và KHÔNG phải vấn đề AI. Đây là cái slide 7 (Path B, hướng ❌) nên dùng — hoặc một trong hai.

## The 7-field canvas

### 1. Symptom — what you can see
Sales reps mất trung bình **2 ngày** để gửi một báo giá cho khách. Mỗi tháng ~40 báo giá. Pipeline có ~12 deal đang "chờ báo giá" tại bất kỳ thời điểm nào. Sales kêu: "quy trình rối, em phải hỏi nhiều người, em không có thời gian." Founder nghe thành: "chúng ta cần một AI quoting tool."

### 2. Who feels it + how often
3 sales reps. ~40 báo giá/tháng = ~13 cái/người/tháng = ~3 cái/người/tuần. Mỗi cái "chiếm" 2 ngày calendar (không phải 2 ngày work — đa số là chờ).

### 3. Current workaround
Rep mở file Excel template báo giá cũ → copy → sửa số → **gửi cho Sales Manager duyệt giá** → Manager bận, 1-2 ngày sau mới reply → rep gửi khách. Đôi khi Manager hỏi "sao giá này?" → rep phải đi hỏi Product về cấu hình → thêm 1 ngày.

### 4. Root-cause hypothesis
Founder đoán: "thiếu công cụ — báo giá thủ công quá." Nhưng khi đào: thời gian SOẠN báo giá thật sự là ~30 phút. **2 ngày là thời gian CHỜ DUYỆT.** Bottleneck là một bước approval không có SLA, dồn vào một người (Sales Manager) đang quá tải, cộng với việc rep không có sẵn pricing rule nên cái gì cũng phải hỏi.

### 5. Cost of doing nothing (next 12 months)
~12 deal kẹt × tỷ lệ rớt do chậm ~25% × deal size trung bình 8.000$ = **~24.000$/quý "rò rỉ"**, ~96.000$/năm. Cộng tinh thần sales (3 người, thường xuyên xin lỗi khách). Đủ lớn để đáng sửa.

### 6. What "solved" looks like in 30 days
Báo giá ra tay khách **trong 4 tiếng** thay vì 2 ngày. Pipeline "chờ báo giá" ≤ 3 deal bất kỳ lúc nào.

### 7. Company context
- **Size:** 35 người · **Stage:** Series A · **Industry:** SaaS B2B (phần mềm quản lý kho)
- **Tools we run:** HubSpot (CRM), Google Workspace, Slack, Notion. Pricing: 3 tier + chiết khấu theo volume — quy tắc nằm trong đầu Sales Manager, chưa viết ra.

---

## Solution directions

### Direction A — Sửa QUY TRÌNH: viết pricing rule ra + bỏ bước duyệt cho 90% trường hợp *(chosen)*
Sales Manager dành 1 buổi viết pricing rule thành 1 trang: 3 tier, ngưỡng chiết khấu, khi nào cần duyệt (chỉ deal >20.000$ hoặc chiết khấu >15%). Rep tự ra báo giá trong khung đó, không cần duyệt. Manager chỉ duyệt ~10% deal lớn.
- **Real bottleneck:** một quyết định chưa ai chốt (pricing rule sống trong đầu một người) + một bước approval không cần thiết. KHÔNG phải đọc/viết/tổng hợp.
- **Repetition:** ~40/tháng — đủ để sửa quy trình, nhưng việc "soạn" chỉ 30 phút, không phải chỗ đau.
- **Input availability:** pricing rule chưa viết ra — nhưng đó là 1 buổi, không phải data project.
- **Output owner + risk:** khách hàng đọc báo giá — sai thì mất uy tín. Nhưng rule rõ ràng + Manager spot-check là đủ.
- **What Claude would do here:** *gần như không gì.* Có thể giúp Manager soạn cái 1-trang pricing rule (30 phút, một lần). Hết.
- **What stays with a human:** chốt pricing rule, duyệt 10% deal lớn — đó là việc của Manager, không tự động hóa.
- **Verdict:** ✅ pursue — đây là đòn bẩy lớn nhất. 1 buổi work, giải quyết ~90% độ chậm. Chi phí gần 0.

### Direction B — Mua/cấu hình một CPQ tool (config-price-quote) trong HubSpot
HubSpot có module quote sẵn. Bật lên, nhập template, rep ra báo giá từ trong CRM.
- **Real bottleneck:** vẫn là bước duyệt — CPQ tool không sửa cái đó. Nó chỉ làm bước "soạn 30 phút" thành "soạn 10 phút". Tiết kiệm 20 phút trên một quy trình 2 ngày.
- **Verdict:** ⚠️ pursue with caveat — đáng làm SAU Direction A, không phải thay. Nếu làm B mà bỏ A: tốn tiền + setup, độ chậm gần như không đổi.

### Direction C — Build "AI quoting environment" (cái founder muốn ban đầu)
Một skill đọc yêu cầu khách + cấu hình → tự sinh báo giá theo template → ghi vào HubSpot. Có thể thêm MCP nối HubSpot.
- **Real bottleneck:** AI sinh báo giá nhanh hơn — nhưng bottleneck là DUYỆT, không phải SINH. AI không bỏ được bước duyệt; chỉ founder + Manager bỏ được (bằng Direction A).
- **Repetition:** đủ (40/tháng).
- **Input availability:** cần pricing rule viết ra trước — y như Direction A. Tức là *Direction A là điều kiện của Direction C*, không phải thay thế nó.
- **Verdict:** 🅿️ park — sau khi Direction A chạy, NẾU phần "soạn 30 phút" vẫn còn đau (chắc không), lúc đó mới build. Build C trước A = giải sai vấn đề bằng công cụ đắt tiền.

## Environment design (cho Direction nào "build với AI")
Không có direction nào cần một môi trường AI ngay bây giờ. Direction A không cần phần mềm. Nếu sau này build C: surface = skill (+ MCP HubSpot nếu cần ghi ngược), connections = HubSpot + pricing-rule doc + quote template, reusable skill = `/build-quote`, boundary = AI sinh nháp, Manager duyệt deal lớn. **Nhưng đó là chuyện của quý sau, không phải tuần này.**

## Verdict
Đòn bẩy lớn nhất của bạn ở đây **không phải AI — là viết pricing rule ra và bỏ bước duyệt cho 90% deal**. Đó là 1 buổi work, gần như không tốn gì, giải quyết phần lớn độ chậm. AI (hay CPQ tool) chỉ nhặt được phần "soạn 30 phút" — và chỉ nên đụng tới *sau khi* bạn đã sửa bước duyệt. Đánh đổi bạn chấp nhận: Sales Manager phải buông bớt quyền duyệt và tin pricing rule — đó là điều khó nhất, và là điều thật sự cần xảy ra.

---

> **Cách dùng file này trong demo (slide 7):** đọc qua 7 ô (nhanh, ~1 phút) → chỉ vào Direction C: "đây là cái founder MUỐN ngay từ đầu — một AI quoting tool." → rồi chỉ vào verdict C: **🅿️ park** và verdict A: ✅. "Thấy chưa — công cụ vừa bảo: đừng build AI cho việc này. Sửa quy trình trước. Đó là cầm búa đúng — nó nói cho bạn biết khi nào KHÔNG nên đập."
