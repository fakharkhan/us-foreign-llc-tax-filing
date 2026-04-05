---
name: us-tax-filing-foreign-llc
description: >
  Complete annual U.S. tax filing workflow for a foreign-owned single-member LLC (disregarded entity).
  Use this skill whenever the user mentions: annual tax filing, IRS forms, Form 1120, Form 5472,
  Form 1040-NR, Form 7004, foreign-owned LLC taxes, nonresident alien tax return, U.S. tax
  preparation, P&L to tax forms, or any combination of U.S. tax compliance for a foreign resident
  owning a U.S. LLC. Also triggers for: "prepare my taxes", "fill IRS forms", "tax season",
  "file my returns", "extension filing", "foreign LLC compliance". Always use this skill for
  tax-related workflows — do not attempt to guide through IRS forms without it.
---

# U.S. Tax Filing — Foreign-Owned Single-Member LLC

This skill guides Claude through the complete annual U.S. tax filing process for a **foreign-owned
U.S. single-member LLC** (treated as a disregarded entity). It covers all four required IRS forms
and is designed for foreign nationals who own a U.S. LLC and operate remotely from outside the U.S.

> ⚠️ **DISCLAIMER**: This skill is for informational and workflow guidance purposes only.
> It does not constitute tax advice. Always consult a qualified CPA or tax professional
> before filing. Tax laws change annually — verify all figures and rules for the current year.

---

## Who This Skill Is For

- Foreign national (non-U.S. resident) who owns a U.S. single-member LLC 100%
- LLC is a **disregarded entity** for U.S. tax purposes
- Owner files as a **nonresident alien** (Form 1040-NR)
- No U.S. employees, no payroll, fully remote operations from outside the U.S.
- Business activity: professional services, software, consulting, or similar

---

## Forms Required Each Year

| Form | Purpose | Due Date | Extension |
|------|---------|----------|-----------|
| **Form 7004** | Extension of time to file Form 1120 | April 15 | N/A — files itself |
| **Form 1120** | Pro forma corporate return (shell for 5472) | April 15 (or extended) | 6 months via 7004 |
| **Form 5472** | Foreign-owned LLC related-party transactions | Attached to 1120 | Same as 1120 |
| **Form 1040-NR** | Nonresident alien income tax return | April 15 | 6 months (Form 4868) |

> ⚠️ Form 5472 penalties start at **$25,000** for failure to file or errors. Always verify carefully.

---

## Step 1 — Collect Information Before Filing

Run through these questions with the user **one at a time** and save answers to memory.
Read `references/data-collection.md` for the full question list and memory-saving instructions.

Key categories:
1. LLC EIN and owner's ITIN/SSN
2. Annual P&L (revenue, all expense categories, total assets)
3. Information returns received/issued (1099s, W-2s, 1042-S)
4. Payroll confirmation
5. Form 5472 related-party transactions
6. Addresses (U.S. registered office vs. foreign personal/office address)
7. Form 1040-NR facts (filing status, days in U.S., treaty position)
8. Schedule OI facts (citizenship, visa type, prior year filing)
9. Prior filing status (any previously filed/abandoned returns)
10. State returns (usually N/A for remote foreign-owned LLCs)
11. Payment method

---

## Step 2 — Tax Calculations

Once P&L data is collected, calculate:

### Form 1120 (Pro Forma — $0 Tax)
- The LLC is disregarded; 1120 is filed only as a vehicle to attach Form 5472
- Income flows to owner's 1040-NR
- Line 1a = Gross receipts
- Line 1c = Gross receipts (no returns for service businesses)
- Line 3 = Gross profit (no COGS for service businesses)
- Line 11 = Total income
- Line 16 = Rent expense (if any)
- Line 26 = All other deductions combined
- Line 27 = Total deductions
- Line 28 = Taxable income (Line 11 - Line 27)
- Line 30 = Same as Line 28
- Line 31 = **$0** (tax is on 1040-NR, not here)
- Line 35 = **$0**

### Form 5472 Related-Party Transactions
Report ALL flows between LLC and foreign owner:
- Expenses paid by LLC for owner's personal benefit (travel, rent/office)
- Capital contributions or loans (in either direction)
- Distributions/withdrawals taken by owner
- Note retained earnings (not a transaction but document)

### Form 1040-NR Tax Calculation
```
Taxable Income = Net LLC Income (no standard deduction for NRAs)

See references/tax-calculations.md for current year MFS tax brackets
and the Python calculation function.

Important:
- No self-employment tax for NRA on B1/B2 visitor visa
- No standard deduction for nonresident aliens
- Use Married Filing Separately (MFS) brackets for married NRAs
```

---

## Step 3 — Fill the Forms

### Method A: Browser-Guided (with Claude in Chrome)
Use the Claude in Chrome extension to open each official IRS PDF and guide the user field by field.
Read `references/form-field-guide.md` for field-by-field instructions for all 4 forms.

**Order to fill:**
1. Form 7004 (simplest — 1 page)
2. Form 1120 (6 pages — focus on Pages 1, 3, 4)
3. Form 5472 (3 pages)
4. Form 1040-NR (2 pages)

**Official IRS PDF URLs (always use current year):**
- Form 7004: `https://www.irs.gov/pub/irs-pdf/f7004.pdf`
- Form 1120: `https://www.irs.gov/pub/irs-pdf/f1120.pdf`
- Form 5472: `https://www.irs.gov/pub/irs-pdf/f5472.pdf`
- Form 1040-NR: `https://www.irs.gov/pub/irs-pdf/f1040nr.pdf`

**Browser-guided tips:**
- Give user up to 3 fields at a time
- Always take a zoomed screenshot to verify after user says "next" or "done"
- If a field is unclear, explain it before asking user to fill
- Verify each batch before moving on

### Method B: P&L to PDF (automated)
Convert P&L HTML to PDF using weasyprint:
```python
from weasyprint import HTML
HTML('profit-and-loss.html').write_pdf('profit-and-loss.pdf')
```

---

## Step 4 — Review & Sign

**Form 1120 — Sign Here section (Page 1, bottom):**
- Signature of officer: owner's signature
- Date: filing date
- Title: `Sole Member`
- May IRS discuss with preparer: `No` (unless CPA is engaged)
- Note: Form 1120 does NOT have a phone number field

**Form 1040-NR — Sign Here section (Page 2, bottom):**
- Your signature + Date + Occupation + Phone + Email

**Form 7004 & 5472:** No signature required.

---

## Step 5 — Filing Instructions

**Form 1120 + 5472 (file together):**
```
Dept of the Treasury, IRS Center, Ogden, UT 84201-0012
```

**Form 1040-NR:**
```
Dept of the Treasury, IRS, Austin, TX 73301-0215
```

**Form 7004:**
```
Dept of the Treasury, IRS, Ogden, UT 84201-0045
```

> ⚠️ Always verify mailing addresses at irs.gov before filing — they change periodically.

**Payment:** Pay 1040-NR tax via IRS online account at `irs.gov/account`. No payment for Form 1120.

---

## Step 6 — CPA Review (Strongly Recommended)

Before filing, recommend CPA review especially for:
- Form 5472 (high penalty risk — $25,000 minimum for errors)
- Large/unusual deductions, treaty questions, first-time filers

**CPA outreach tips:**
- 2-step approach: WhatsApp intro first → email with attachments
- Emphasize forms are already prepared (lower fee)
- Ask for minimum fee for small companies with partial prep done
- Reference mutual introduction by name

---

## Step 7 — Document Archive Checklist

- [ ] `profit-and-loss-YYYY.pdf`
- [ ] `f7004-YYYY.pdf` (signed)
- [ ] `f1120-YYYY.pdf` (signed, 5472 attached)
- [ ] `f5472-YYYY.pdf`
- [ ] `f1040nr-YYYY.pdf` (signed)
- [ ] IRS payment confirmation
- [ ] Mailing receipts/tracking numbers
- [ ] CPA sign-off email (if applicable)

---

## Important Notes & Gotchas

1. Use registered U.S. office on 1120/5472; personal foreign address on 1040-NR
2. No standard deduction for NRAs on 1040-NR
3. No SE tax for NRA on B1/B2 visa
4. Form 5472 must be attached to Form 1120 — never file alone
5. Total assets = year-end cash balance if no other fixed assets
6. Round all amounts to nearest dollar
7. ITIN format: 9XX-XX-XXXX — confirm it has not expired
8. State returns generally not required for fully remote foreign-owned LLCs
9. Verify tax brackets, form versions, and addresses every year
10. If owner spent 183+ days in the U.S., residency rules change significantly

---

## Reference Files

- `references/data-collection.md` — Full question list + memory templates
- `references/form-field-guide.md` — Field-by-field instructions for all 4 forms
- `references/tax-calculations.md` — Tax brackets, Python calculator, deduction mapping
- `examples/sample-pl.html` — Anonymized P&L template
