# Form Field Guide — Field-by-Field Instructions

Complete reference for all 4 IRS forms. Use when guiding browser-based form filling.

---

## Form 7004 — Extension (1 page)

| Field | Value |
|-------|-------|
| Name | LLC legal name |
| Identifying number | EIN (XX-XXXXXXX) |
| Number and street | U.S. registered office street |
| City / State / ZIP | City, State abbreviation, ZIP |
| Line 1 — Form code | `12` (for Form 1120) |
| Line 5a — Calendar year | Last 2 digits of tax year (e.g. `25`) |
| Line 6 — Tentative total tax | `0` (disregarded entity) |
| Line 7 — Total payments | `0` |
| Line 8 — Balance due | `0` |

**No signature required.**

---

## Form 1120 — Corporate Return (6 pages)

### Page 1 — Header

| Field | Value |
|-------|-------|
| Name | LLC legal name |
| B — EIN | XX-XXXXXXX |
| Street address | U.S. registered office |
| City / State / Country / ZIP | Fill each box |
| C — Date incorporated | MM/DD/YYYY |
| D — Total assets | Year-end cash balance |

### Page 1 — Income & Deductions

| Line | Description | Value |
|------|-------------|-------|
| 1a | Gross receipts | Total revenue |
| 1c | Balance | Same as 1a (no returns) |
| 3 | Gross profit | Same as 1c (no COGS) |
| 11 | Total income | Same as line 3 |
| 16 | Rents | Rent expense amount |
| 26 | Other deductions | All other expenses combined |
| 27 | Total deductions | Line 16 + Line 26 |
| 28 | Taxable income before NOL | Line 11 - Line 27 |
| 30 | Taxable income | Same as Line 28 |
| 31 | Total tax | `0` (disregarded entity) |
| 35 | Amount owed | `0` |

### Page 3 — Schedule J (all zeros)
Lines 1a, 2, 12, 19, 21, 23 → all `0`

### Page 4 — Schedule K

| Field | Value |
|-------|-------|
| Line 1 | Accounting method: Cash |
| Line 2a | Business activity code (e.g. `541511`) |
| Line 2b | Business activity description |
| Line 2c | Product or service |
| Line 3 | Subsidiary? → No |
| Line 6 | Dividends paid? → No |
| Line 7 | Foreign person owns 25%+? → Yes |
| Line 7(a) | Percentage owned: `100` |
| Line 7(b) | Owner's country |
| Line 7(c) | Number of Forms 5472: `1` |
| Line 10 | Number of shareholders: `1` |

### Sign Here (Page 1, bottom)
Signature + Date + Title (`Sole Member`) + May IRS discuss: No
Note: Form 1120 has **no phone number field**

---

## Form 5472 — Foreign-Owned LLC (3 pages)

### Page 1 — Part I (Reporting Corporation)

| Field | Value |
|-------|-------|
| Tax year | Beginning 01/01/YYYY — Ending 12/31/YYYY |
| 1a Name | LLC legal name |
| 1b EIN | XX-XXXXXXX |
| Address | U.S. registered office |
| 1c Total assets | Year-end cash balance |
| 1d Activity | Business description |
| 1e Code | NAICS code |
| 1f Gross payments (this form) | Sum of all related-party transactions |
| 1g Number of Forms 5472 | `1` |
| 1h Gross payments (all forms) | Same as 1f |
| 1j Initial year | Check if first year filing |
| 1l Country of incorporation | `US` |
| 1m Date of incorporation | MM/DD/YYYY |
| 1o Principal country | `US, [owner country]` |
| Line 2 | Foreign person owns 50%+: Check ✓ |
| Line 3 | Foreign-owned U.S. DE: Check ✓ |

### Page 1 — Part II (25% Foreign Shareholder)

| Field | Value |
|-------|-------|
| 4a Name and address | Owner full name + foreign address |
| 4b(1) U.S. identifying number | ITIN (XXX-XX-XXXX) |
| 4c Principal country | Owner's country |
| 4d Country of citizenship | Owner's country |
| 4e Country files as resident | Owner's country |

### Page 2 — Part III (Related Party)

| Field | Value |
|-------|-------|
| Foreign person checkbox | Check ✓ |
| 8a Name and address | Same as 4a |
| 8b(1) ITIN | XXX-XX-XXXX |
| 8c Business activity | `Individual Owner / Sole Member` |
| 8e Relationship | Check `25% foreign shareholder` |
| 8f Principal country | Owner's country |

### Page 2 — Part IV (Monetary Transactions)

| Line | Description | Value |
|------|-------------|-------|
| 22 | Total received | `0` (usually) |
| 27a | Rents paid | Rent paid for owner's benefit |
| 35 | Other amounts paid | Travel/other for owner |
| 36 | Total amounts paid | Sum of lines 23-35 |

### Page 3 — Part VII (all No for typical remote LLC)
Lines 37, 39, 40a, 41a, 42a, 43a → all **No**

**No signature required.**

---

## Form 1040-NR — Nonresident Alien Return (2 pages)

### Page 1 — Header & Personal Info

| Field | Value |
|-------|-------|
| First name | Owner's first name(s) |
| Last name | Owner's last name |
| Identifying number | ITIN (XXX-XX-XXXX) |
| Home address | Foreign street address |
| City | Foreign city |
| Foreign country | Country name |
| Foreign province | Province/state |
| Foreign postal code | Postal code |
| Filing Status | Married Filing Separately (MFS) |
| Digital Assets | No |

### Page 1 — Income

| Line | Value |
|------|-------|
| 1h type | `LLC distributive share income` |
| 1h amount | Net LLC income |
| 1z | Same as 1h |
| 9 | Same (total ECI) |
| 11a | Same (AGI) |

### Page 2 — Tax

| Line | Value |
|------|-------|
| 11b | AGI |
| 12 | `0` (no standard deduction for NRAs) |
| 15 | Taxable income (same as AGI) |
| 16 | Tax per MFS brackets |
| 18 | Same as line 16 |
| 22 | Same as line 16 |
| 24 | Total tax |
| 33 | `0` (if no estimated payments) |
| 37 | Amount owed |

### Sign Here (Page 2)
Signature + Date + Occupation + Phone + Email
