# BÁO CÁO AUDIT WEBSITE BEDDING SOURCING
**Loại website:** Dịch vụ B2B (sourcing, tư vấn, kết nối sản xuất ngành bedding/mattress/home textile)
**Phạm vi audit:** Toàn bộ source `index.html` (3.771 dòng, SPA 8 trang con) + assets (~15MB)
**Ngày audit:** 12/07/2026

---

## TÓM TẮT ĐIỀU HÀNH

Website có nền tảng tốt hơn mặt bằng chung: thiết kế sạch kiểu Apple, nội dung kỹ thuật ngành sâu bất ngờ (chi số sợi, AQL, MIL-STD-105E, C/O forms), có song ngữ VI/EN, FAQ, quy trình 5 bước, responsive đã được xử lý khá kỹ. **Nhưng website hiện tại KHÔNG THỂ tạo ra lead** vì 3 lỗi chí mạng:

1. **Form liên hệ là form giả** — submit chỉ `console.log` rồi hiện toast "gửi thành công". Không có backend, không email, không webhook. Mọi lead đều mất 100%.
2. **Regex điện thoại chặn toàn bộ khách quốc tế** — form bắt buộc SĐT định dạng Việt Nam, trong khi mục tiêu là buyer/importer nước ngoài. Khách Mỹ/EU nhập +1, +49… sẽ bị `alert()` từ chối.
3. **Không có analytics** — không GA4, không pixel. Dù có sửa 2 lỗi trên cũng không đo được chuyển đổi.

Ngoài ra: 8.1MB ảnh chưa tối ưu (1 ảnh 5MB), 3 cặp ảnh trùng lặp/sai nội dung, SEO gần như bằng 0 với khách quốc tế (SPA hash → chỉ 1 URL, không schema, không OG, không hreflang, meta chỉ tiếng Việt), và **định vị bị pha loãng** giữa 2 tệp khách hoàn toàn khác nhau (buyer mua sản phẩm bedding vs. nhà máy mua máy móc sản xuất nệm).

**Trả lời câu hỏi cốt lõi:** Website hiện truyền tải thương hiệu ở mức TRUNG BÌNH KHÁ về hình thức, YẾU về khả năng tạo lead và YẾU về tiếp cận khách quốc tế.

---

## PHẦN 1: PHÂN TÍCH TỔNG QUAN

| Tiêu chí | Đánh giá | Ghi chú |
|---|---|---|
| Hiểu ngay Bedding Sourcing là ai? | ✅ Đạt | H1 "Giải pháp Sourcing Bedding cho thương hiệu quốc tế" + badge "B2B Supply Chain Partner" rõ trong 3 giây |
| Rõ đây là dịch vụ sourcing ngành bedding? | ✅ Đạt | Nhất quán xuyên suốt |
| Rõ khách hàng mục tiêu? | ⚠️ Nửa vời | Nêu "nhãn hàng, khách sạn, đơn vị nhập khẩu" nhưng hero nói "thương hiệu quốc tế" trong khi toàn site mặc định tiếng Việt, SĐT nội địa, Zalo — mâu thuẫn |
| Chuyên nghiệp, quốc tế, đáng tin? | ⚠️ Trung bình | Giao diện chuyên nghiệp; nhưng thiếu favicon, email placeholder `@gmail.com`, domain `.online` vs email `.vn` không khớp, ảnh trùng lặp làm giảm độ tin |
| Thể hiện năng lực sourcing/supply chain/PD/manufacturing? | ✅ Khá tốt | Nội dung kỹ thuật sâu (AQL, techpack, C/O, LCL/FCL) — điểm mạnh nhất của site |
| Thông điệp khác biệt? | ⚠️ Yếu | "Đồng hành kỹ thuật, không phải môi giới" là ý khác biệt tốt nhưng bị chôn ở trang Giới thiệu, không xuất hiện ở hero |
| Quá chung chung / thiếu lý do liên hệ? | ⚠️ | Nội dung không chung chung, nhưng thiếu PROOF (case study, logo khách, con số thật) nên lý do liên hệ chưa đủ mạnh |
| Đủ yếu tố tạo niềm tin B2B? | ❌ Chưa | Số liệu "02/03", "100%", "B2B" trong section "Năng lực số liệu" là số liệu rỗng; không case study; không đội ngũ; công ty mới 2023 lại đem ngày thành lập ra làm "thành tích" |
| Dẫn dắt đến hành động liên hệ? | ⚠️ Nửa vời | Trang chủ dẫn tốt; 4 trang con (Dịch vụ, Quy trình, Sản phẩm, Lợi thế) kết thúc CỤT — không có CTA cuối trang |

**Vấn đề chiến lược lớn nhất — định vị kép:** Site đang phục vụ đồng thời (a) buyer quốc tế mua sản phẩm bedding và (b) chủ nhà máy Việt Nam mua máy móc thiết bị nệm. Hai persona này khác ngôn ngữ, khác hành trình, khác CTA. Trộn chung ở hero (dashboard card 04 là "Thiết bị ngành nệm") làm loãng thông điệp với cả hai. **Đề xuất:** giữ bedding sourcing làm định vị chính của trang chủ; tách "Machinery Sourcing" thành trang riêng có landing/CTA riêng, chỉ để 1 link ở menu và footer.

---

## PHẦN 2: ĐỊNH VỊ THƯƠNG HIỆU

**Hiện trạng:** Định vị "đồng hành kỹ thuật dệt may, không phải trung gian môi giới" là góc định vị TỐT và có thật (nội dung kỹ thuật chứng minh được). Nhưng nó không được đưa lên tuyến đầu. Brand story hiện tại là… thông tin đăng ký kinh doanh (tên pháp lý, MST, người đại diện, 11 mã ngành) — đây là ngôn ngữ của tra cứu doanh nghiệp, không phải của thương hiệu.

**Cần làm rõ lợi thế:** CÓ — chính kiến thức BOM/vật liệu/nhà máy/QC/logistics đã có trong site cần được đóng gói thành thông điệp, không để dàn trải trong đoạn văn.

### Đề xuất định vị
- **Định vị:** *Văn phòng sourcing kỹ thuật (technical sourcing office) ngành bedding tại Việt Nam — đứng về phía buyer, làm việc bằng thông số, không phải bằng lời hứa.*
- **Tagline chính (EN):** **"Your technical sourcing partner for bedding — from spec sheet to shipment."**
- **Tagline (VI):** **"Đối tác sourcing kỹ thuật ngành bedding — từ thông số đến container."**
- **Thông điệp cốt lõi:** Chúng tôi không môi giới. Chúng tôi đọc BOM, hiểu vải, sống ở nhà máy, và chịu trách nhiệm chất lượng đến khi hàng lên tàu.

### Lý do chọn Bedding Sourcing (đóng gói lại từ nội dung có sẵn)
1. Engineering-first: đội ngũ am hiểu chi số sợi, mật độ dệt, nhuộm hoạt tính — thẩm định nhà máy bằng kỹ thuật, không bằng catalogue.
2. Minh bạch nhà máy: buyer biết rõ mình đang sản xuất ở đâu (danh sách nhà máy ISO/BSCI/OEKO-TEX được chia sẻ).
3. QC độc lập AQL 1.5/2.5 với báo cáo ảnh chi tiết trước khi đóng container.
4. Một đầu mối từ techpack → sample → sản xuất → C/O → logistics (LCL gom FCL, tiết kiệm ~30% cước).
5. Am hiểu cả máy móc sản xuất nệm — hiểu nhà máy từ bên trong dây chuyền.

### Làm thương hiệu dễ nhớ hơn
- Thêm favicon + og:image (hiện KHÔNG có — share link lên LinkedIn/WhatsApp sẽ trắng trơn, rất mất điểm B2B).
- Dùng nhất quán 1 con số mạng lưới: hero nói "50+ xưởng", trang Lợi thế nói "hàng chục nhà máy" → chọn một con số thật và dùng mọi nơi.
- Chuẩn hóa email: site là `beddingsourcing.online`, email là `info@beddingsourcing.vn` → phải cùng một domain (khuyến nghị dùng domain .vn hoặc mua .com và dùng email theo domain chính).
- Với khách quốc tế: mặc định EN khi trình duyệt không phải tiếng Việt (hiện mặc định VI).

---

## PHẦN 3: NỘI DUNG

**Điểm mạnh:** Nội dung kỹ thuật chân thật, sâu, đúng ngôn ngữ ngành (hiếm có ở website VN cùng loại). FAQ trả lời số liệu cụ thể (MOQ 500m/màu, sample 7–10 ngày).

**Điểm yếu và đề xuất viết lại:**

1. **Section "Năng lực số liệu" (trang chủ) — RỖNG NHẤT SITE.** Ba "stat" hiện tại: `02/03` (ngày thành lập!), `100%` (cam kết AQL), `B2B` (mô hình). Đây không phải số liệu năng lực.
   **Viết lại (chỉ dùng số có thật, xác nhận với chủ site):**
   - `50+` Nhà máy đối tác đạt OEKO-TEX / BSCI
   - `500m` MOQ thấp nhất mỗi màu vải
   - `7–10 ngày` Ra mẫu Gold Sample
   - `AQL 1.5/2.5` Chuẩn kiểm hàng độc lập
2. **Trang Giới thiệu — quá nặng pháp lý, thiếu brand story.** Đoạn "Được thành lập ngày 02/03/2023 dưới tên pháp lý… Người đại diện pháp luật là ông…" nên chuyển xuống trang Liên hệ/footer. Thay bằng brand story dạng vấn đề→giải pháp:
   > *"Bedding Sourcing ra đời từ một thực tế: buyer quốc tế mất tiền không phải vì nhà máy Việt Nam kém, mà vì lớp trung gian không đọc nổi một bản techpack. Chúng tôi là đội ngũ kỹ thuật dệt may đứng giữa — dịch yêu cầu của bạn thành thông số nhà máy hiểu được, và dịch năng lực nhà máy thành rủi ro bạn kiểm soát được."*
3. **Câu "trở thành văn phòng sourcing được tin cậy bởi các thương hiệu lớn trong nước và quốc tế"** — công ty thành lập 2023, không có logo/tên khách chứng minh → câu này phản tác dụng với buyer B2B (họ kiểm tra được). Đổi thành cam kết kiểm chứng được: *"Mỗi đơn hàng đều có báo cáo QC độc lập và danh sách nhà máy minh bạch — bạn kiểm chứng được mọi thứ chúng tôi nói."*
4. **Trang Sản phẩm viết giọng bán lẻ** ("êm ái tiêu chuẩn khách sạn 5 sao", "mát lạnh tự nhiên cho da nhạy cảm") — đây là ngôn ngữ bán cho người tiêu dùng, không phải cho buyer. Buyer cần: chất liệu, chi số, TC, MOQ, chứng chỉ, thị trường đã xuất. Viết lại mỗi card theo mẫu:
   > **Bed sheets** — Cotton Sateen 40s–80s (300–600TC), Tencel, Bamboo, Linen. MOQ từ 500m/màu. OEKO-TEX 100. Đã xuất EU/US. → CTA: "Request fabric specs & pricing"
5. **Khách nhận được gì sau khi liên hệ?** — chưa nói ở đâu. Thêm ngay dưới form: *"Trong 24h: chúng tôi phản hồi xác nhận. Trong 3–5 ngày làm việc: bạn nhận đề xuất nhà máy phù hợp + khung giá sơ bộ + MOQ. Miễn phí, không ràng buộc."*
6. **Tiếng Anh thương mại:** bản dịch EN hiện khá tốt nhưng vài chỗ dịch word-by-word ("Business service model", "Official launch date (2023)"). Khi sửa section stats thì các chuỗi này biến mất theo.

---

## PHẦN 4: DỊCH VỤ

Hiện có 7 service card + 1 section máy móc. Đối chiếu với 12 dịch vụ chuẩn:

| Dịch vụ | Trạng thái trên site | Đánh giá |
|---|---|---|
| Product sourcing | ✅ Card 1 | Rõ, có lợi ích (giá xưởng, điều khoản thanh toán) |
| Supplier sourcing / Factory matching | ✅ Card 4 | Rõ, có chứng chỉ cụ thể |
| Product development | ✅ Card 2 | Rõ (Gold Sample, thread count) |
| Material sourcing | ⚠️ Gộp trong card 1 | Nên nêu rõ nhóm vật liệu: foam, lò xo, vải, bông, lông vũ, phụ liệu |
| OEM/ODM support | ⚠️ Ẩn dưới "Private Label" | Buyer quốc tế tìm từ khóa "OEM/ODM" — cần xuất hiện chữ này |
| QC support | ✅ Card 5 + section riêng | Tốt nhất site |
| Cost optimization | ⚠️ Rải rác | Có ý (loại trung gian, LCL→FCL −30%) nhưng không có card riêng |
| Supply chain coordination | ✅ Card 7 + kho bãi | Ổn |
| Export support | ✅ Card 6 | Rõ (C/O forms cụ thể) |
| Sample development | ✅ Trong card 2 + FAQ | Ổn |
| Packaging & private label | ⚠️ Chỉ 1 dòng trong mã ngành | Nên có mô tả riêng |
| Machinery sourcing | ✅ Card 3 + section lớn | Rất chi tiết — nhưng nên tách trang riêng (xem Phần 1) |

**Vấn đề trình bày:** 7 card ngang hàng, không phân nhóm, không có CTA trên từng card, không nói "bạn nhận được gì".

**Đề xuất cấu trúc lại thành 3 nhóm:**
- **SOURCE** (Tìm nguồn): Product sourcing, Factory matching, Material sourcing
- **BUILD** (Phát triển): Product development OEM/ODM, Sample, Packaging & Private Label
- **PROTECT** (Bảo vệ đơn hàng): QC độc lập, Export & customs, Logistics & warehousing
- *(Trang riêng)* **EQUIP**: Machinery & equipment sourcing

**Template mỗi dịch vụ (áp dụng cho trang chi tiết):**
1. *Vấn đề:* "Bạn nhận 20 báo giá từ Alibaba nhưng không biết nhà máy nào thật sự dệt được 600TC."
2. *Cách giải quyết:* "Chúng tôi audit nhà máy tại chỗ, kiểm tra máy dệt và mẫu lưu, chỉ đưa vào shortlist 2–3 nhà máy đạt kỹ thuật."
3. *Kết quả nhận được:* "Shortlist nhà máy + khung giá + MOQ trong 5 ngày làm việc."
4. *Quy trình:* 3–5 bước ngắn.
5. *CTA:* "Request supplier matching" / "Gửi yêu cầu tìm nhà máy".

---

## PHẦN 5: HỆ THỐNG CTA

**Hiện trạng đã kiểm kê toàn site:**
- Header: "Nhận tư vấn" ✅ | Hero: "Nhận tư vấn sourcing" + "Khám phá dịch vụ" ✅ đúng chuẩn CTA chính/phụ
- CTA section trang chủ: "Nhận báo giá sourcing" ✅
- Mobile menu: "Nhận tư vấn sourcing" + Gọi ngay + Zalo ✅
- Form: "Gửi yêu cầu tư vấn" ✅
- **Trang Dịch vụ: KHÔNG có CTA nào** ❌ (kết thúc bằng list máy móc)
- **Trang Quy trình: KHÔNG có CTA** ❌
- **Trang Sản phẩm: KHÔNG có CTA** ❌ (6 product card không card nào có CTA)
- **Trang Lợi thế: KHÔNG có CTA** ❌
- Floating buttons: chỉ Zalo + Gọi — **thiếu WhatsApp và Email cho khách quốc tế** ❌ (Zalo vô nghĩa với buyer Mỹ/EU)

CTA wording hiện tại đúng hướng dịch vụ B2B (không có lỗi kiểu "Mua ngay"). Vấn đề là **độ phủ**, không phải câu chữ.

### Đề xuất CTA từng khu vực

| Khu vực | CTA chính | CTA phụ |
|---|---|---|
| Hero | Nhận tư vấn sourcing / *Talk to a sourcing expert* | Xem quy trình làm việc / *See how we work* (dẫn Quy trình thay vì Dịch vụ — tạo niềm tin trước) |
| Cuối trang Dịch vụ | Gửi yêu cầu sourcing của bạn / *Send your sourcing requirement* | Xem quy trình 5 bước |
| Cuối trang Quy trình | Bắt đầu bước 1 — gửi nhu cầu của bạn / *Start step 1 — tell us what you need* | Đặt lịch tư vấn 30 phút |
| Mỗi product card | Yêu cầu báo giá danh mục này / *Request pricing for this category* (link tới form kèm ?category=) | — |
| Cuối trang Sản phẩm | Nhận bảng thông số & báo giá vải / *Get fabric specs & pricing* | — |
| Cuối trang Lợi thế | Kiểm chứng năng lực của chúng tôi — đặt lịch trao đổi / *Put us to the test — book a call* | — |
| Section máy móc | Yêu cầu báo giá thiết bị / *Request machinery quotation* (CTA riêng cho persona nhà máy) | — |
| Footer | Thêm khối mini: "Có dự án sourcing? Gửi yêu cầu — phản hồi trong 24h" + nút | Email + WhatsApp |
| Mobile sticky | Thanh sticky đáy màn hình 2 nút: **"Gửi yêu cầu"** (accent) + **WhatsApp/Zalo** (tự chọn theo ngôn ngữ đang bật: EN→WhatsApp, VI→Zalo) | — |

---

## PHẦN 6: HÀNH TRÌNH KHÁCH HÀNG B2B

Chuỗi 8 bước — điểm gãy nằm ở bước 5 và 8:

1. Vào website ✅ (hero đẹp, rõ)
2. Hiểu là ai ✅
3. Hiểu giải quyết vấn đề gì ⚠️ — chưa có section "nỗi đau khi sourcing" (rủi ro chất lượng, trung gian, trễ hàng chỉ được nhắc 1 câu ở CTA section)
4. Thấy dịch vụ phù hợp ✅
5. **Tin vào năng lực ❌ — GÃY.** Không case study, không logo khách, không ảnh đội ngũ/nhà máy thật (ảnh stock + ảnh trùng lặp), stat rỗng. Buyer B2B dừng ở đây.
6. Hiểu quy trình ✅ (5 bước tốt)
7. Thấy rủi ro được giảm thiểu ⚠️ — QC/AQL tốt nhưng thiếu cam kết dạng "không đạt QC thì sao?", thiếu NDA/bảo mật thiết kế
8. **Được dẫn đến hành động ❌ — GÃY.** 4/7 trang là ngõ cụt; form thì không hoạt động thật.

**Bổ sung cần thiết:** section Problem trên trang chủ; 2–3 project example (kể cả ẩn danh: "Nhà nhập khẩu Đức — 3 container ga khách sạn 300TC — từ RFQ đến giao hàng 62 ngày, 0 lỗi AQL"); form "Send us your sourcing requirement" nhúng ngay trang chủ (không chỉ ở trang Liên hệ); FAQ mở rộng lên 8–10 câu (thêm: phí dịch vụ tính thế nào? có ký NDA không? thanh toán ra sao? có làm việc với startup/đơn nhỏ không?).

---

## PHẦN 7: UI/UX TỪNG PHẦN

| Phần | Điểm mạnh | Điểm yếu / Việc cần làm |
|---|---|---|
| Header | Gọn (60px), blur đẹp, CTA riêng | Logo chữ "B[E]DDING" với E bằng SVG dễ vỡ căn chỉnh; thiếu favicon; nav 7 mục hơi nhiều — gộp "Sản phẩm" vào "Dịch vụ" hoặc đổi "Sản phẩm"→"Ngành hàng" (đúng bản chất sourcing hơn) |
| Menu desktop | Uppercase 0.75rem rõ | "Sản phẩm" gây hiểu nhầm bán hàng |
| Menu mobile | Có label, CTA, Gọi/Zalo trong menu — tốt | Thiếu WhatsApp; đóng menu khi bấm link đã xử lý đúng |
| Hero | Video + poster + fallback ảnh, chữ rõ, overlay chuẩn | Video 768×432 kéo full màn 4K sẽ vỡ; hero image 2000×2000 vuông cho khung ngang — crop lãng phí; badge "B2B Supply Chain Partner" tiếng Anh trong bản VI hơi lệch tông |
| About (trang chủ) | Copy khá | Ảnh PNG 627KB nên đổi JPG/WebP |
| Stats | — | Số liệu rỗng (xem Phần 3) — đây là section yếu nhất trang chủ |
| Services | Card sạch, icon nhất quán | Không CTA trên card; không phân nhóm |
| Product categories | Grid đẹp | Ảnh sai nội dung (xem Phần 12), copy giọng bán lẻ, không CTA |
| Process | 5 bước rõ, số to | Nên thêm timeline tổng ("RFQ → giao hàng: 45–75 ngày") và CTA cuối |
| Why choose us | Nội dung khác biệt thật | Nên thêm proof đi kèm mỗi claim |
| Trust section | ❌ Chưa tồn tại | Cần: logo chứng chỉ (OEKO-TEX, BSCI…) dạng badge, project examples, ảnh thật hoạt động QC |
| Case study | ❌ Chưa có | Thêm 2–3 project example ẩn danh |
| FAQ | Dùng `<details>` native — nhẹ, không bug | Chỉ 4 câu, nằm ở trang Liên hệ — nên nhân đôi và đưa 1 bản rút gọn lên trang chủ |
| Contact | Form + thông tin cty 2 cột hợp lý | Cột trái toàn thông tin đăng ký KD — buyer không cần "mã số thuế" to hơn "email"; ưu tiên: email, WhatsApp, giờ làm việc theo timezone, bản đồ khu vực hoạt động |
| Footer | 4 cột đủ | Thiếu WhatsApp/email dạng link bấm được (hiện là text thường); link "Điều khoản & Cookie" trỏ cùng trang với "Chính sách bảo mật" |
| Thứ tự section trang chủ | — | Hiện: Hero→About→Stats→Services→CTA. Đề xuất ở Phần 13 |

---

## PHẦN 8: MOBILE

**Đánh giá chung: đây là phần được làm TỐT nhất của website.** Kiểm tra source cho thấy các nguyên nhân tràn ngang kinh điển đều đã xử lý tận gốc:
- Grid 2 cột → `minmax(0, 1fr)` + `min-width: 0` cho con (fix đúng gốc, không che) ✅
- Bảng spec → bọc trong `.spec-table-container { overflow-x: auto }` (cuộn nội bộ, không đẩy trang) ✅
- Toast → `max-width: min(90vw, 440px)` ✅
- `.cta-section::after` 200% → cha có `overflow: hidden` ✅
- Không có `100vw`, không negative margin, không fixed width lớn ✅
- Hero mobile rút còn 62vh, ẩn dashboard — hợp lý ✅
- Font mobile: h1 1.95rem, body 1rem — dễ đọc ✅
- Nút bấm: `.btn` padding 14×28 — đạt chuẩn ≥44px ✅

**Còn tồn tại:**
1. `overflow-x: hidden` khai báo 3 lần ở cấp trang (`html` dòng 56, `body` dòng 66, `html` lặp lại dòng 2141) như "safety net". Vì các nguyên nhân gốc đã fix, khuyến nghị **giữ 1 khai báo là đủ và thêm comment**; không được coi đây là giải pháp chính (hiện tại nó đang che khuất việc test — nên tắt tạm khi QA để chắc chắn không còn phần tử tràn).
2. **Cookie banner + floating buttons + back-to-top chồng nhau ở đáy màn hình mobile** — cookie banner (z-index 3000) che nút Zalo/Gọi cho tới khi user bấm chấp nhận. Đề xuất: thu cookie banner thành 1 dòng compact ở mobile, hoặc dời floating buttons lên trên banner khi banner hiển thị.
3. **Chưa có mobile sticky CTA "Gửi yêu cầu"** — hiện chỉ có Zalo/Gọi nổi. Buyer quốc tế trên mobile không có đường tắt tới form.
4. Ảnh 5MB/3MB trên 4G sẽ làm section trắng vài giây (lazy loading có nhưng file quá nặng) — xem Phần 12.
5. `<img>` không có thuộc tính `width`/`height` → nguy cơ CLS khi ảnh load (một phần được cứu bởi `aspect-ratio` trong CSS ở about/product, nhưng nên thêm thuộc tính cho tất cả).

---

## PHẦN 9: FORM & LEAD GENERATION

**Lỗi nghiêm trọng nhất toàn website (đã xác minh trong source, dòng 3658–3686):**

```js
sourcingForm.addEventListener('submit', (e) => {
    e.preventDefault();
    ...
    console.log('Sourcing Request Submitted:', {...});  // ← chỉ log ra console
    sourcingForm.reset();
    showToast(`Cảm ơn ${fullname}! ... đã được gửi thành công...`); // ← toast GIẢ
});
```
→ **Không một lead nào được gửi đi.** Khách tưởng đã gửi thành công → không liên hệ lại bằng kênh khác → mất lead vĩnh viễn + mất uy tín.

**Lỗi nghiêm trọng thứ 2 (dòng 3668):**
```js
const phoneRegex = /(84|0[3|5|7|8|9])+([0-9]{8})\b/g;
```
→ Chặn mọi SĐT không phải Việt Nam bằng `alert()`. Buyer quốc tế — đối tượng mục tiêu số 1 — **không thể gửi form**.

**Các lỗi khác của form:**
- Input không có thuộc tính `name` → không submit được qua backend chuẩn, autofill trình duyệt kém.
- Bắt buộc SĐT nhưng không bắt buộc Company — ngược nhu cầu B2B (buyer ngại cho SĐT, sẵn sàng cho company/email).
- Placeholder email `doi-tac@gmail.com` — gợi ý gmail thiếu chuyên nghiệp, đổi thành `name@company.com`.
- Không checkbox đồng ý chính sách bảo mật (chính sách của site tự yêu cầu "sự đồng ý").
- Không chống spam (honeypot/turnstile), không file upload cho techpack/BOM.

### Form đề xuất (2 tầng)

**Form ngắn (nhúng trang chủ + cuối các trang):** Name* · Work email* · Company · Bạn cần gì? (dropdown) · Nút "Send sourcing request"

**Form chi tiết (trang Liên hệ):**
| Trường | Bắt buộc | Ghi chú |
|---|---|---|
| Full name | ✅ | |
| Company | ✅ | B2B phải có |
| Work email | ✅ | validate email, gợi ý email công ty |
| Country/Region | ✅ | dropdown — giúp phân loại lead + timezone |
| Phone/WhatsApp | ❌ | tự do định dạng, KHÔNG regex VN; thêm ô "Preferred contact: Email/WhatsApp/Zalo/Call" |
| Product category | ✅ | Sheets/Duvet/Inserts/Mattress&Topper/Hotel linen/Curtains&Rugs/Machinery/Other |
| Estimated quantity / MOQ | ❌ | text tự do |
| Target price | ❌ | optional, ghi rõ "if available" |
| Requirement details | ✅ | textarea |
| File upload | ❌ | techpack/BOM/ảnh mẫu (pdf, xlsx, ảnh ≤10MB) |
| Consent checkbox | ✅ | link chính sách bảo mật |

**Tiêu đề form:** VI: "Gửi yêu cầu sourcing của bạn" / EN: **"Send Your Sourcing Requirement"**. Dưới nút submit ghi rõ: *"Phản hồi trong 24h — đề xuất nhà máy & khung giá trong 3–5 ngày làm việc."*

**Backend tối thiểu (chọn 1, làm được ngay không cần server):** Formspree / Getform / Web3Forms / Google Apps Script → gửi về email + Google Sheet. Đây là việc PHẢI làm trước mọi việc khác.

---

## PHẦN 10: SEO

**Hiện trạng (xác minh trên source): gần như chưa làm SEO.**

| Hạng mục | Trạng thái |
|---|---|
| Meta title/description | Có, chỉ tiếng Việt, chỉ 1 bộ cho toàn site |
| Kiến trúc URL | ❌ SPA hash routing (`#dich-vu`) → Google chỉ index 1 URL duy nhất; 7 "trang" không tồn tại với công cụ tìm kiếm |
| H1 | ❌ 8 thẻ H1 cùng lúc trong DOM (mỗi spa-page 1 cái, đều render trong 1 document) |
| Schema | ❌ Không có JSON-LD nào (Organization, Service, FAQPage đều thiếu — FAQ có sẵn nội dung, chỉ việc gắn schema) |
| OG/Twitter card | ❌ Không có → share link trắng trơn |
| Canonical, robots, sitemap | ❌ Không có |
| Favicon | ❌ Không có |
| hreflang / EN cho crawler | ❌ Bản EN là JS text-swap client-side — Google index bản VI; buyer tìm "bedding sourcing Vietnam" bằng tiếng Anh sẽ không bao giờ thấy site |
| Alt text | ✅ Có đủ, nhưng vài alt sai ngôn ngữ/generic ("Yarn spools spinning", "Clean modern warehouse storage") và alt không khớp ảnh do ảnh bị trùng |
| Internal link | ⚠️ Nav + footer có; thiếu link chéo trong nội dung |
| Blog/Insight | ❌ Chưa có |

**Khuyến nghị cấu trúc (quan trọng nhất):** chuyển hash-SPA thành đa trang tĩnh thật (`/en/services/`, `/vi/dich-vu/`…) hoặc tối thiểu dùng History API + prerender. Với mục tiêu SEO quốc tế, **bản EN phải là HTML thật có URL riêng + hreflang**, không phải JS swap.

**Meta đề xuất (EN homepage):**
- Title: `Bedding Sourcing Vietnam | B2B Sourcing Agent for Bedding & Home Textiles`
- Description: `Technical sourcing partner in Vietnam for bed linen, duvets, mattresses & hotel textiles. Factory matching, OEM/ODM development, independent AQL inspection, export support. Get a quote in 3–5 days.`

**Bộ từ khóa ưu tiên:** bedding sourcing agent Vietnam · Vietnam bedding manufacturer sourcing · mattress sourcing Vietnam · OEM bedding supplier Vietnam · hotel linen supplier Vietnam · bed sheet manufacturer Vietnam · home textile sourcing agent · private label bedding manufacturer · bedding quality inspection Vietnam · mattress machinery supplier. (Nhóm VI cho thị trường nội địa: tìm nguồn hàng chăn ga gối đệm xuất khẩu, máy sản xuất nệm lò xo túi, máy chần gòn đa kim…)

**Nội dung nên viết (landing/blog):**
1. "How to source bedding from Vietnam: a buyer's guide (2026)"
2. "Thread count explained: what 300TC vs 600TC really means for hotel sheets"
3. "Vietnam vs China for bedding manufacturing: costs, MOQs, lead times"
4. "AQL 1.5 vs 2.5: choosing the right inspection level for textiles"
5. "OEKO-TEX, BSCI, GOTS: which certificates your bedding supplier actually needs"
6. Landing riêng: "Hotel linen sourcing" (khách sạn/resort là ICP rõ nhất của site)
7. Landing riêng: "Mattress machinery sourcing" (tách persona máy móc)

---

## PHẦN 11: ĐỘ TIN CẬY B2B

| Yếu tố | Có? | Việc cần làm |
|---|---|---|
| Đội ngũ/chuyên môn | ❌ | Thêm section 2–4 người: ảnh thật, chức danh, số năm trong ngành dệt |
| Quy trình sourcing | ✅ | Tốt |
| Kinh nghiệm ngành | ⚠️ | Có kiến thức, thiếu bằng chứng con người/dự án |
| Case study | ❌ | 2–3 project example ẩn danh (thị trường, sản phẩm, số lượng, lead time, kết quả QC) |
| Danh mục ngành hàng | ✅ | Có, cần sửa ảnh + giọng văn |
| Cam kết QC | ✅ | Mạnh nhất site — nên thêm ảnh báo cáo QC mẫu (blur thông tin) |
| Supplier verification | ⚠️ | Có nhắc chứng chỉ; nên mô tả quy trình audit nhà máy 5 bước riêng |
| Sample process | ✅ | FAQ có; nên đưa lên trang Quy trình |
| Quy trình báo giá | ⚠️ | Thêm "nhận gì sau 24h/5 ngày" |
| OEM/ODM/Private label | ⚠️ | Có nhưng thiếu chữ OEM/ODM nổi bật |
| Thông tin liên hệ | ⚠️ | Có đủ nhưng: email khác domain website; SĐT chưa có +84; thiếu WhatsApp; thiếu giờ làm việc/timezone |
| Email doanh nghiệp | ⚠️ | `info@beddingsourcing.vn` trên site `.online` — phải đồng bộ |
| Địa chỉ/khu vực | ✅ | Có (TP.HCM + các vùng sản xuất) |
| FAQ quốc tế | ⚠️ | 4 câu — thêm: phí hoa hồng/phí dịch vụ, điều khoản thanh toán (T/T, LC), NDA, incoterms, đơn nhỏ có nhận không, làm việc múi giờ nào |

---

## PHẦN 12: HIỆU NĂNG & KỸ THUẬT

**Đã đo trực tiếp trên file:**

| Vấn đề | Số liệu thực | Mức độ | Cách sửa (không phá layout) |
|---|---|---|---|
| Ảnh quá khổ | `advantages/01`: 6000×4000px, **5.0MB**; `process/01`: 6000×4000px, **3.0MB**; `about/02`: 2584×4592px, 1.5MB; `specs/01` 797KB; `advantages/02` PNG 823KB; `about/01` PNG 627KB | 🔴 Cao | Resize về max 1600px cạnh dài, xuất WebP quality ~80 (dự kiến 15MB → ~1.5MB, giảm ~90%). Giữ nguyên tên file+markup, chỉ thay file (hoặc thêm `<picture>`) |
| Ảnh trùng lặp/sai nội dung | `products/02_vo_chan_vo_goi.jpg` **chính là ảnh hero container** (md5 trùng) — card "Vỏ chăn & Vỏ gối" đang hiển thị ảnh logistics; `products/06` trùng `products/01`; `about/03` trùng `services/01` | 🔴 Cao | Thay 3 ảnh đúng nội dung |
| Hero tải 3 tài nguyên | CSS background-image + poster (cùng file 780KB) + video 755KB | 🟡 TB | Bỏ `background-image` trong CSS `.hero` (poster đã làm việc đó); nén poster riêng ~150KB |
| Video 768×432 | Kéo giãn full màn desktop → mờ | 🟡 TB | Xuất bản 1280×720 ~1.2MB hoặc chấp nhận mờ nhẹ; thêm `media="(min-width:769px)"` source để mobile chỉ dùng poster |
| Font 6 weights | 300–800 Plus Jakarta Sans | 🟢 Thấp | Bỏ 300, 500 (ít dùng) còn 4 weights |
| CLS | `<img>` thiếu width/height | 🟡 TB | Thêm thuộc tính width/height cho mọi img |
| Animation | reveal dùng scroll listener thủ công (checkReveal chạy mỗi scroll event) | 🟢 Thấp | Chuyển sang IntersectionObserver; thêm `@media (prefers-reduced-motion)` |
| JS lỗi tiềm ẩn | `sourcingForm` được addEventListener không kiểm tra null — nếu sau này tách trang sẽ crash script | 🟢 Thấp | Bọc `if (sourcingForm)` |
| Form không hoạt động | Xem Phần 9 | 🔴 Cao | Nối backend |
| Link CTA | Đều dẫn đúng `#lien-he` ✅ | — | — |
| Analytics | Không có GA4/pixel nào (dù cookie policy nói có "cookie phân tích") | 🔴 Cao | Cài GA4 (gate sau cookie consent — consent đã có sẵn, chỉ việc nối) |
| overflow-x hidden | Khai báo 2 lần | 🟢 Thấp | Gộp còn 1 (root causes đã fix — xem Phần 8) |

---

## PHẦN 13: CẤU TRÚC TRANG CHỦ ĐỀ XUẤT

Hiện tại: Hero → About → Stats(rỗng) → Services(3) → CTA. Đề xuất 10 section:

| # | Section | Mục tiêu | Nội dung chính | CTA | Desktop / Mobile |
|---|---|---|---|---|---|
| 1 | Hero | Định vị 3 giây | H1 + sub (giữ hiện tại, thêm tagline kỹ thuật) | "Nhận tư vấn sourcing" + "Xem quy trình" | Video / ảnh tĩnh + 2 nút full-width |
| 2 | Trust bar | Neo niềm tin ngay | 1 hàng: 50+ nhà máy · MOQ 500m · Sample 7–10 ngày · AQL 1.5/2.5 · Xuất EU/US | — | 4 cột / 2×2 |
| 3 | Problem | Đồng cảm nỗi đau | 3 pain: trung gian không kỹ thuật · chất lượng xổ số · trễ container | "Chúng tôi giải quyết thế nào ↓" | 3 card / dọc |
| 4 | Services (3 nhóm) | Giải pháp | SOURCE / BUILD / PROTECT, mỗi nhóm 3 dòng | "Xem chi tiết dịch vụ" + CTA/card | 3 cột / dọc |
| 5 | Product categories | Đúng ngành hàng | 6 card viết giọng B2B (specs, MOQ, cert) | "Request pricing" mỗi card | Grid 3×2 / 1 cột |
| 6 | How it works | Giảm rủi ro | 5 bước + tổng lead time | "Bắt đầu bước 1" | Ngang / dọc số to |
| 7 | Why us + proof | Khác biệt | 4 lợi thế, mỗi cái kèm bằng chứng; badge chứng chỉ | — | 2 cột / dọc |
| 8 | Project examples | Chứng minh | 2–3 case ẩn danh dạng số liệu | "Trao đổi về dự án của bạn" | 3 card / carousel dọc |
| 9 | FAQ rút gọn | Gỡ rào cản | 5 câu hay gặp nhất | "Xem tất cả FAQ" | Accordion (giữ `<details>`) |
| 10 | Final CTA + form ngắn | Chốt lead | Form 4 trường nhúng thẳng + cam kết phản hồi 24h | "Send sourcing request" | 2 cột / form dọc |

*(Máy móc thiết bị: bỏ khỏi hero dashboard, thay bằng 1 banner nhỏ trước footer: "Bạn là nhà sản xuất nệm cần thiết bị? → Xem Machinery Sourcing")*

---

## PHẦN 14: BỘ THÔNG ĐIỆP THƯƠNG HIỆU

**Tagline:** "Your technical sourcing partner for bedding — from spec sheet to shipment." / VI: "Từ thông số kỹ thuật đến container hàng."

**Headline trang chủ:** EN: "Bedding sourcing in Vietnam, run by textile engineers." / VI: "Sourcing chăn ga gối đệm tại Việt Nam — vận hành bởi kỹ sư dệt may."

**Subheadline hero:** "We match global brands, hotels and importers with certified Vietnamese factories — and stay on the factory floor until your order ships right." / VI: "Kết nối thương hiệu, khách sạn và nhà nhập khẩu với nhà máy đạt chuẩn tại Việt Nam — và bám xưởng đến khi đơn hàng của bạn lên tàu đúng chuẩn."

**CTA chính:** "Send your sourcing requirement" / "Gửi yêu cầu sourcing" · **CTA phụ:** "See how we work" / "Xem quy trình làm việc"

**5 thông điệp năng lực:** (1) Chúng tôi đọc techpack của bạn như nhà máy đọc — và viết techpack như buyer cần. (2) Audit nhà máy bằng máy dệt và mẫu lưu, không bằng catalogue. (3) MOQ từ 500m/màu — cấu trúc được đơn hàng nhỏ cho thương hiệu mới. (4) Gold Sample trong 7–10 ngày làm việc. (5) LCL gom FCL đa nhà cung cấp — tiết kiệm đến 30% cước biển.

**5 thông điệp niềm tin:** (1) Báo cáo QC độc lập kèm ảnh trước khi đóng container — không đạt, không xuất. (2) Danh sách nhà máy minh bạch: bạn biết chính xác hàng của mình sản xuất ở đâu. (3) Chuẩn nghiệm thu AQL 1.5/2.5 ghi thẳng vào thỏa thuận. (4) Ký NDA bảo vệ thiết kế trước khi xem bất kỳ tài liệu nào. (5) Phản hồi trong 24 giờ, đề xuất nhà máy trong 5 ngày làm việc.

**5 thông điệp khác biệt:** (1) Không phải môi giới — là văn phòng kỹ thuật đứng về phía buyer. (2) Hiểu nhà máy từ bên trong: chúng tôi sourcing cả dây chuyền sản xuất nệm. (3) Chuyên sâu một ngành duy nhất: bedding & home textile. (4) Một đầu mối từ ý tưởng đến C/O và vận đơn. (5) Giá xưởng thật — vì chúng tôi ngồi đàm phán tại xưởng.

**5 CTA ngắn-mạnh:** Send your requirement · Get a sourcing quote · Book a factory-matching call · Request fabric specs · Start your project

**5 CTA mềm:** Talk to a sourcing expert · Ask us anything about Vietnam sourcing · Not sure where to start? Let's talk · Get a free feasibility check · Compare us with your current supplier

**5 mô tả dịch vụ 1 câu:** (1) Factory matching: shortlist 2–3 nhà máy đạt kỹ thuật trong 5 ngày. (2) Product development: từ moodboard đến Gold Sample sẵn sàng sản xuất hàng loạt. (3) QC độc lập: mắt của bạn tại xưởng, theo chuẩn AQL 1.5/2.5. (4) Export support: C/O, kiểm nghiệm, hải quan — trọn gói một chữ ký. (5) Machinery sourcing: dây chuyền nệm từ lò xo túi đến roll-pack, bảo hành 12 tháng.

---

## PHẦN 15: BẢNG ĐỀ XUẤT CẢI TIẾN (ưu tiên)

| Khu vực | Vấn đề | Ảnh hưởng | Nguyên nhân | Đề xuất | Thay thế cụ thể | Lợi ích | Ưu tiên |
|---|---|---|---|---|---|---|---|
| Form | Không gửi dữ liệu (console.log + toast giả) | 🔴 Cao | Chưa nối backend | Nối Formspree/Web3Forms/Apps Script; thêm `name` attributes | — | Bắt đầu có lead | **Làm ngay** |
| Form | Regex chặn SĐT quốc tế | 🔴 Cao | Regex VN hardcode | Bỏ regex; phone thành optional | Trường "Phone/WhatsApp (any format)" | Khách quốc tế gửi được | **Làm ngay** |
| Đo lường | Không có analytics | 🔴 Cao | Chưa cài | GA4 + sự kiện submit form, nối cookie consent sẵn có | — | Đo được chuyển đổi | **Làm ngay** |
| Ảnh | 8MB ảnh chưa nén; 3 cặp ảnh trùng/sai | 🔴 Cao | Ảnh gốc máy ảnh; đặt nhầm file | Nén WebP ≤1600px; thay 3 ảnh đúng nội dung | products/02, products/06, about/03 | Tốc độ + độ tin | **Làm ngay** |
| Liên hệ | Thiếu WhatsApp; email khác domain; SĐT không +84 | 🔴 Cao | Setup nội địa | Thêm WhatsApp float+footer; đồng bộ email theo domain chính; ghi +84 933 126 162 | — | Khách quốc tế liên hệ được | **Làm ngay** |
| Stats | Số liệu rỗng ("02/03", "B2B") | 🟡 TB | Thiếu số thật | Thay bằng 50+/500m/7–10 ngày/AQL | Xem Phần 3 | Niềm tin | Làm sau |
| CTA | 4 trang con không CTA cuối trang | 🟡 TB | Thiếu section | Thêm CTA block cuối mỗi trang | Xem Phần 5 | +Lead | Làm sau |
| Proof | Không case study/đội ngũ/badge chứng chỉ | 🟡 TB | Chưa xây | Thêm 3 section proof | Xem Phần 11 | Niềm tin B2B | Làm sau |
| SEO | 1 URL, không schema/OG/favicon/hreflang | 🟡 TB (cao nếu cần organic) | SPA hash | Đa trang hoá + schema Organization/Service/FAQ + OG + favicon | Xem Phần 10 | Organic quốc tế | Làm sau |
| Nội dung | Trang Sản phẩm giọng bán lẻ | 🟡 TB | Copy B2C | Viết lại theo spec/MOQ/cert | Xem Phần 3.4 | Đúng buyer | Làm sau |
| Định vị | Máy móc lẫn với bedding ở hero | 🟡 TB | 2 persona chung 1 trang | Tách landing Machinery | Xem Phần 1 | Thông điệp sắc | Làm sau |
| Mobile | Cookie banner che nút float; thiếu sticky CTA | 🟢 Thấp | Layout đáy màn | Compact banner; sticky "Gửi yêu cầu" | Xem Phần 8 | UX mobile | Cân nhắc |
| Hero | Video 432p; tải trùng poster/bg | 🟢 Thấp | Asset | Bỏ bg CSS; video 720p | Xem Phần 12 | Tốc độ | Cân nhắc |

---

## PHẦN 16: KẾ HOẠCH 3 GIAI ĐOẠN

**Giai đoạn 1 — Sửa lỗi nghiêm trọng (1–3 ngày):**
Nối backend form + name attributes + bỏ regex VN + consent checkbox → cài GA4 + event submit → nén/thay ảnh (8MB→~1.5MB) → thêm WhatsApp + đồng bộ email/+84 → favicon + OG tags cơ bản.

**Giai đoạn 2 — Nội dung, CTA, hành trình lead (1–2 tuần):**
Thay section Stats bằng 4 số thật → thêm CTA cuối 4 trang con + CTA trên product card → form ngắn nhúng trang chủ + đoạn "bạn nhận được gì sau 24h/5 ngày" → viết lại trang Sản phẩm giọng B2B → mở rộng FAQ lên 8–10 câu → thêm section Problem + Project examples → mobile sticky CTA.

**Giai đoạn 3 — Thương hiệu, SEO, độ tin (2–6 tuần):**
Chuyển đa trang thật + EN URLs + hreflang → JSON-LD Organization/Service/FAQPage → landing "Hotel linen" + "Machinery" → 3–5 bài blog EN đầu tiên → section đội ngũ + badge chứng chỉ + ảnh thật QC → chuẩn hóa domain/email thương hiệu.

---

## PHẦN 17: CHECKLIST NGHIỆM THU

**Lead & form:** ☐ Submit form → nhận được email thật ☐ Submit với SĐT +1/+49/không SĐT → thành công ☐ GA4 ghi nhận event ☐ Toast chỉ hiện khi gửi thành công thật ☐ Có consent checkbox
**Hiệu năng:** ☐ Tổng ảnh trang chủ <1.5MB ☐ Không ảnh nào >300KB ☐ LCP mobile <2.5s (PageSpeed) ☐ CLS <0.1 ☐ img có width/height
**Mobile:** ☐ Tắt tạm `overflow-x:hidden` → không tràn ngang ở 360/390/414px ☐ Cookie banner không che nút liên hệ ☐ Sticky CTA hoạt động ☐ Form nhập dễ trên bàn phím mobile
**Nội dung & CTA:** ☐ Không còn stat rỗng ☐ Mọi trang đều kết thúc bằng CTA ☐ Product card có CTA ☐ Không còn ảnh trùng md5 ☐ Ảnh khớp caption
**SEO & thương hiệu:** ☐ Favicon hiển thị ☐ Share link lên WhatsApp/LinkedIn có ảnh + title ☐ Schema pass Rich Results Test ☐ Bản EN crawl được (View Source thấy tiếng Anh) ☐ Email cùng domain website ☐ Một con số mạng lưới thống nhất toàn site
