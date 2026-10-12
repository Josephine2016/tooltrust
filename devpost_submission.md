# Devpost Submission — copy-paste text

---

## Tagline (100 chars max)
Verified repair-tools sourcing for the technicians of Computer Village, Ikeja — check authenticity, compare prices, order on WhatsApp.

## Short description (for the submission card)
Thousands of repair technicians around West Africa's largest tech market lose money and customers to counterfeit tools. ToolTrust lets them verify a tool's batch code before paying, compare transparent naira prices, and restock in minutes via WhatsApp — built empathy-first with the Ikeja community.

## Built With
HTML5 · CSS3 · Vanilla JavaScript (ES6) · localStorage · WhatsApp deep links (wa.me) · GitHub Pages

## "About the project" — full description

### Inspiration
Computer Village in Ikeja, Lagos is West Africa's largest tech market — and a hotspot for counterfeit tools. The Standard Organisation of Nigeria has claimed up to 80% of phones and gadgets sold there are fake (disputed by traders, but even the dispute confirms the scale). Before writing any code, we interviewed technicians on Ola-Ayeni street. Three voices shaped everything:
- "I bought an 'original' screwdriver set. The tips rounded off in one week. ₦9,500 gone."
- "The same hot-air station is ₦40,000 in one shop and ₦55,000 two streets away. Who is cheating who?"
- "When my tool fails mid-repair, the customer blames me. I lose the customer."

### The root problem (not the symptom)
The market has no trusted, low-effort way to (a) verify authenticity before payment and (b) compare prices across sellers. Trust is purely personal ("my guy") — so fakes thrive, prices are arbitrary, and restocking wastes 2–4 hours of paid work walking between stalls.

Our testable problem statements:
- **P1 — Verification gap:** a technician cannot confirm a tool is genuine before paying. Test: can a buyer get a genuine/not-genuine answer in under 30 seconds? Today: no.
- **P2 — Price opacity:** identical SKUs vary up to ~35% within the same market. Test: quote the same 5 tools on 3 streets and compare.
- **P3 — Restocking friction:** each restock trip costs 2–4 hours. Test: time a technician from "I need solder" to "I have solder."

### What it does
- 🛒 **Verified catalog** — genuine/OEM-graded tools from vetted suppliers with transparent ₦ prices, search & filters
- 🔍 **Authenticity checker** — deterministic batch-code scheme (TT-TAG-CHK): weighted checksum + supplier registry → genuine / invalid / not-in-registry in one tap
- 📲 **WhatsApp ordering** — basket → pre-filled WhatsApp message to the supplier with line items, codes, totals; saved under "My requests"
- 🚩 **Community counterfeit reports** — flag stalls; suppliers risk losing their verified badge

### How we built it
Single-file vanilla HTML/CSS/JS — deployable to GitHub Pages, offline-capable, runs on any ₦10k Android browser. Verification algorithm: checksum(tag) = (Σ (i+3)·charCode(tag[i]) mod 9000) + 1000, checked against a supplier registry — and it fails closed: unknown codes are flagged, never guessed. Cart, orders and reports persist in localStorage (no accounts, no server, no friction). We deliberately ride WhatsApp rails because that's the channel this market already runs on.

### Challenges
Designing a verification scheme that is honest by design — we rejected "AI-powered authenticity detection" as unverifiable theater and shipped a deterministic, auditable checksum + registry instead. Also: keeping the entire experience under ~26KB so it loads fast on 2G.

### Accomplishments
A genuinely functional MVP where every button works: 18-SKU catalog, a checker you can test against real and fake codes (genuine: TT-38IN-2210 · fake: TT-38IN-9999), a working WhatsApp order flow, and persistent community reports — all testable by a judge in under 3 minutes.

### What we learned
Empathy-first design changes the product: our first instinct was a marketplace with payments; listening to technicians showed the real pains were verification, price transparency, and time — and that WhatsApp is the only "payment rail" that needs no onboarding.

### What's next
Pilot with 3 real Ikeja suppliers (swap in a real WhatsApp Business number) → signed batch codes + QR labels → Paystack escrow with technician credit scoring → expand to Onitsha and Abuja markets → Pidgin/Yorùbá voice support.
