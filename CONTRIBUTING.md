# Contributing to ToolTrust 🛠️

Thanks for helping protect repair technicians from counterfeit tools. This project started at **WarriorHacks 2.0** and is built for the Computer Village community — contributions that come from (or are tested with) real technicians are the most valuable.

## Ways to contribute

- 🐛 **Report bugs** — open an Issue with steps to reproduce (phone model + browser matters!)
- 🌍 **Add SKUs & suppliers** — contribute real catalog data from verified Ikeja suppliers
- 🗣️ **Translations** — Pidgin, Yorùbá, Hausa, Igbo UI strings
- 🔐 **Verification scheme** — review or extend the batch-code checksum (`checksum()` in `index.html`)
- 💳 **Payments** — help design the Paystack escrow flow (see Roadmap in README)
- 📱 **UX testing** — test on low-end Android phones and spotty 2G/3G connections

## Getting started

```bash
git clone https://github.com/<you>/tooltrust.git
cd tooltrust
# No build step. Open index.html in a browser, or:
python -m http.server 8000   # then visit http://localhost:8000
```

## Ground rules

1. **Empathy first.** Every PR should trace back to a real technician pain point from README §1–3. No feature without a problem statement.
2. **Mobile-first, low-bandwidth.** The target user has a ₦10k Android and unreliable data. Keep the single-file architecture and zero-dependency constraint unless a PR explicitly argues otherwise.
3. **Honest verification only.** Never mark an unknown code as genuine. The checker must fail closed.
4. **Local-first.** No user accounts or tracking. Keep data in `localStorage` until the escrow milestone.
5. Test your changes on a 360px-wide viewport before submitting.

## Pull request process

1. Fork the repo and create a branch: `git checkout -b feat/short-description`
2. Make your change, test on mobile viewport (Chrome DevTools)
3. Update README if behavior or demo codes change
4. Open a PR describing: the problem statement it addresses → the change → how to test it

## Code of conduct

Be kind, be honest, credit the community. We follow the standard [Contributor Covenant](https://www.contributor-covenant.org/version/2/1/code_of_conduct/).
