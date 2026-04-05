# Tax Calculation Worksheets

> ⚠️ Update this file every October/November when IRS announces new year brackets.

---

## Form 1040-NR — MFS Tax Brackets

### 2025 Married Filing Separately (MFS) Brackets

| Income Range | Rate |
|-------------|------|
| $0 – $11,925 | 10% |
| $11,925 – $48,475 | 12% |
| $48,475 – $103,350 | 22% |
| $103,350 – $197,300 | 24% |
| $197,300 – $250,525 | 32% |
| $250,525 – $375,800 | 35% |
| Over $375,800 | 37% |

### Python Tax Calculator

```python
def calculate_tax_mfs(income, year=2025):
    """Calculate federal income tax for Married Filing Separately."""
    brackets_2025 = [
        (11925, 0.10),
        (48475, 0.12),
        (103350, 0.22),
        (197300, 0.24),
        (250525, 0.32),
        (375800, 0.35),
        (float('inf'), 0.37),
    ]
    tax = 0
    prev = 0
    for limit, rate in brackets_2025:
        if income <= limit:
            tax += (income - prev) * rate
            break
        else:
            tax += (limit - prev) * rate
            prev = limit
    return round(tax, 2)

# Example: net income $69,336
print(calculate_tax_mfs(69336))  # → 10167.92
```

---

## Form 1120 — Deduction Mapping (P&L → Form Lines)

| P&L Category | Form 1120 Line |
|-------------|----------------|
| Rent expense — office premises | Line 16 (Rents) |
| Foreign operations expense | Line 26 (Other deductions) |
| Bank service charges | Line 26 (Other deductions) |
| Sales commissions | Line 26 (Other deductions) |
| Software, subscriptions | Line 26 (Other deductions) |
| Contract labor | Line 26 (Other deductions) |
| Travel expense | Line 26 (Other deductions) |

### Line 26 Attachment Statement
When filing, attach a statement listing each Line 26 component:
```
Foreign operations expense:   $XXX,XXX.XX
Bank service charges:         $XXX.XX
Sales commissions:            $XX,XXX.XX
Software/subscriptions:       $XX,XXX.XX
Contract labor:               $XX,XXX.XX
Travel expense:               $X,XXX.XX
──────────────────────────────────────
Total other deductions:       $XXX,XXX.XX
```

---

## Form 5472 — Related-Party Transaction Total

Add all Part IV transactions for lines 1f and 1h:
- Line 27a (Rents paid): $X,XXX.XX
- Line 35 (Other amounts paid): $X,XXX.XX
- **Line 36 Total: $XX,XXX.XX**

---

## Key Rules for NRAs

| Rule | Detail |
|------|--------|
| Standard deduction | **$0** — NRAs do not get standard deduction |
| Self-employment tax | **$0** — NRA on B1/B2 visa, not subject to SE tax |
| Filing status | **MFS** — Married Filing Separately (most common for married NRAs) |
| ITIN | Format: 9XX-XX-XXXX. Check expiration every 3 years if unused |

---

## Annual Update Checklist

At the start of each new tax year, update:
1. ☐ MFS tax brackets (IRS announces in October/November)
2. ☐ Form PDF versions (check IRS.gov for updated forms)
3. ☐ Filing due dates (verify for weekends/holidays)
4. ☐ IRS mailing addresses (can change — verify at irs.gov)
5. ☐ NAICS codes (usually unchanged unless business changes)

---

## Notes on Special Situations

### Distributions Taken
Report in Form 5472 Part V — describe on separate attachment, check Part V box.

### Capital Contributions Made
Report in Form 5472 Part V — describe contribution, note USD amount and date.

### Loans Between LLC and Owner
- LLC borrowed from owner → Lines 17a/17b (Amounts borrowed)
- LLC lent to owner → Lines 31a/31b (Amounts loaned)

### Substantial Presence (183+ days in U.S.)
If owner was in U.S. for 183+ days, residency classification may change.
Consult a CPA immediately — this significantly changes filing requirements.
