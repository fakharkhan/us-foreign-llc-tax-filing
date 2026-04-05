# 🇺🇸 U.S. Tax Filing Skill — Foreign-Owned Single-Member LLC

A Claude AI skill that guides foreign nationals through the complete U.S. annual tax filing
process for a foreign-owned single-member LLC (disregarded entity).

**Built from a real filing. Designed for the global entrepreneur.**

---

## Who Is This For?

You are a **non-U.S. resident** who:
- Owns a **U.S. single-member LLC** (100% foreign-owned)
- Operates **remotely** from outside the United States
- Has **no U.S. employees** and no U.S. payroll
- Needs to file annual U.S. taxes but finds the process confusing and expensive

This includes entrepreneurs from Pakistan, India, Nigeria, UAE, Egypt, Philippines, Bangladesh,
and anywhere else in the world who have formed a U.S. LLC to serve global clients.

---

## What Forms Does This Cover?

| Form | Purpose |
|------|---------|
| **Form 7004** | Extension of time to file (buys you 6 extra months) |
| **Form 1120** | Pro forma corporate return (required to attach Form 5472) |
| **Form 5472** | Foreign-owned LLC related-party transaction reporting |
| **Form 1040-NR** | Your personal U.S. nonresident alien income tax return |

---

## What Does This Skill Do?

✅ **Asks you the right questions** — walks through all data you need, one question at a time

✅ **Calculates your taxes** — applies correct MFS tax brackets, no standard deduction, no SE tax

✅ **Guides you field by field** — works with Claude in Chrome to open IRS PDFs and tell you
exactly what to type in each field

✅ **Verifies your entries** — takes screenshots after each field group to confirm accuracy

✅ **Explains complex fields** — Form 5472 related-party transactions, Schedule OI, and more
in plain English

✅ **Tells you where to file** — exact IRS mailing addresses for each form

✅ **Helps you find a CPA** — drafts outreach messages if you want a professional review

---

## ⚠️ Disclaimer

> This skill is for **informational and workflow guidance purposes only**.
> It does **not** constitute tax advice.
> Tax laws change annually — always verify figures and rules for the current year.
> **Consult a qualified CPA or tax professional before filing**, especially for Form 5472
> (where errors carry a **$25,000 minimum penalty**).

---

## How to Install

1. Download `us-foreign-llc-tax-filing.skill` from the [Releases](../../releases) page
2. Go to **Claude.ai → Settings → Skills**
3. Click **Upload Skill** and select the `.skill` file
4. Done! Claude will use this skill automatically when you mention tax filing

---

## How to Use

Once installed, simply start a conversation with Claude:

> *"I need to file my 2025 U.S. taxes for my foreign-owned LLC"*

Claude will automatically:
1. Ask you all the necessary questions one by one
2. Save your answers to memory
3. Calculate your tax figures
4. Open the IRS forms in your browser and guide you field by field
5. Verify each entry with a screenshot

---

## What You'll Need

Before starting, have these ready:
- Your LLC's **EIN** (Employer Identification Number)
- Your personal **ITIN** (Individual Taxpayer Identification Number)
- Your **annual Profit & Loss statement**
- Your **U.S. registered office address**
- Your **foreign address** (where you live/work)
- **Days spent in the U.S.** during the tax year
- **Year-end bank balance** in your LLC account

---

## Skill Contents

```
us-foreign-llc-tax-filing/
├── SKILL.md                        ← Main skill (7-step workflow)
├── README.md                       ← This file
├── DISCLAIMER.md                   ← Legal disclaimer
├── CONTRIBUTING.md                 ← How to contribute
├── CHANGELOG.md                    ← Version history
├── references/
│   ├── data-collection.md          ← 11 questions to gather each year
│   ├── form-field-guide.md         ← Every field for all 4 IRS forms
│   └── tax-calculations.md         ← Tax brackets + Python calculator
└── examples/
    └── sample-pl.html              ← P&L template you can customize
```

---

## Annual Updates

Tax brackets and form versions change every year. Contributions welcome to update:
- `references/tax-calculations.md` — new MFS brackets each October/November
- `references/form-field-guide.md` — new form layouts if IRS changes them
- `SKILL.md` — any new filing requirements or rule changes

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to help.

---

## Contributing

Pull requests are welcome! Especially helpful:
- 📊 **Tax bracket updates** for new years
- 🌍 **Country-specific notes** (e.g., U.S.-Pakistan treaty, U.S.-India treaty)
- 🐛 **Bug fixes** — if a field location has changed on an IRS form
- 📝 **Edge cases** — distributions, loans, multiple accounts, etc.

---

## License

MIT License — free to use, share, and modify.

---

## Story Behind This Skill

This skill was built during a real 2025 tax filing session by a Pakistani entrepreneur
who owns a U.S. LLC. The entire workflow — from data collection to form filling to CPA
outreach — was captured and turned into a reusable skill so others don't have to start
from scratch.

If it helped you, consider ⭐ **starring the repo** so others can find it!

---

## Acknowledgments

Built with [Claude AI](https://claude.ai) by Anthropic.
Inspired by the thousands of global entrepreneurs navigating U.S. tax compliance every year.
