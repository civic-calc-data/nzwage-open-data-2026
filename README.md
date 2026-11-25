# NZWage Open Data (2026/27)

Open CSV datasets modelling finalised 2026/27 New Zealand PAYE income tax brackets, the rise in default KiwiSaver contributions (3.0% to 3.5%) and ACC Earner's Levy (1.75%, cap $156,641), employer ESCT tax rate cliffs, and exact year-end refunds across 10 secondary-tax scenarios.

All figures are computed from Inland Revenue (IRD) and ACC statutory tables effective 1 April 2026. Interactive calculators and full methodology live at [nzwage.nz](https://nzwage.nz/).

## Datasets in this repository

| File | Coverage | Live report & calculator |
|---|---|---|
| [`data/nz-effective-tax-burden-2026-2027.csv`](data/nz-effective-tax-burden-2026-2027.csv) | 18 salary levels ($35,000 to $250,000): PAYE, IETC, ACC 1.75%, KiwiSaver 3.5%, Student Loan 12%, marginal rates, and net change vs. 2025/26 | [NZ Effective Tax Burden Report](https://nzwage.nz/reports/nz-effective-tax-burden-2026-2027/) / [PAYE Calculator](https://nzwage.nz/) |
| [`data/kiwisaver-esct-impact.csv`](data/kiwisaver-esct-impact.csv) | 14 salary tiers ($17,500 to $250,000): employer 3.5% gross, ESCT rate (10.5% to 39%), ESCT tax deducted, and net employer contribution vs. 2025/26 (3%) | [KiwiSaver ESCT Impact Report](https://nzwage.nz/reports/kiwisaver-esct-impact/) / [KiwiSaver Calculator](https://nzwage.nz/kiwisaver-calculator/) |
| [`data/nz-secondary-tax-myth.csv`](data/nz-secondary-tax-myth.csv) | 10 two-job scenarios ($40k to $195k combined): IRD secondary code (S/SH/ST/SA), PAYE + ACC withheld vs. single-job equivalent, and exact post-31 March refund | [NZ Secondary Tax Myth Report](https://nzwage.nz/reports/nz-secondary-tax-myth/) / [Secondary Tax Calculator](https://nzwage.nz/secondary-tax-calculator/) |

---

## 1. 2026/27 Effective Tax Burden & Take-Home Change ($35k to $250k)

Key findings from [`data/nz-effective-tax-burden-2026-2027.csv`](data/nz-effective-tax-burden-2026-2027.csv):
- Raising default KiwiSaver from 3.0% to **3.5%** plus ACC Earner's Levy to **1.75%** (cap $156,641, max $2,741.22) lowers annual take-home pay by **$290** at $50,000, **$580** at $100,000, **$870** at $150,000, and **$1,189.63** at $200,000 compared with 2025/26.
- Between **$66,000 and $70,000**, the Independent Earner Tax Credit (IETC, $520/yr) abates at 13c per dollar, pushing the marginal PAYE + ACC + IETC rate to **44.75%**. With a 12% Student Loan and 3.5% KiwiSaver, the combined marginal deduction hits **60.25%**.

| Gross annual | PAYE tax | ACC (1.75%) | KiwiSaver (3.5%) | Net (no loan) | Net (with loan) | Marginal (PAYE+ACC+IETC) | Marginal (incl. loan & KS) | Change vs. 2025/26 |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| $50,000 | $7,138.00 | $875.00 | $1,750.00 | $40,237.00 | $37,132.36 | 19.25% | 34.75% | -$290.00 |
| $66,000 | $11,500.50 | $1,155.00 | $2,310.00 | $51,034.50 | $46,009.86 | **44.75%** | **60.25%** | -$382.80 |
| $70,000 | $13,220.50 | $1,225.00 | $2,450.00 | $53,104.50 | $47,599.86 | 31.75% | 47.25% | -$406.00 |
| $100,000 | $22,877.50 | $1,750.00 | $3,500.00 | $71,872.50 | $62,767.86 | 34.75% | 50.25% | -$580.00 |
| $150,000 | $39,377.50 | $2,625.00 | $5,250.00 | $102,747.50 | $87,642.86 | 34.75% | 50.25% | -$870.00 |
| $200,000 | $57,077.50 | $2,741.22 | $7,000.00 | $133,181.28 | $112,076.64 | 39.00% | 54.50% | -$1,189.63 |

---

## 2. KiwiSaver Employer ESCT Rate Cliffs (2026/27)

Unlike progressive PAYE, Employer Superannuation Contribution Tax (ESCT) applies a **single flat rate** to the entire employer contribution based on ESCT threshold income:
- Moving from **$62,000** (ESCT 17.5%) to **$65,000** (ESCT 30.0%) drops the net employer contribution from **$1,790.25** (2.89% of salary) to **$1,592.50** (2.45% of salary) — **$197.75 less** going into the employee's KiwiSaver account despite earning $3,000 more.
- At **$210,000+**, ESCT hits **39.0%**, reducing the 3.5% employer contribution to **2.14% net**.

Full 14-tier dataset is in [`data/kiwisaver-esct-impact.csv`](data/kiwisaver-esct-impact.csv).

---

## 3. Secondary Tax Myth: Exact Year-End Refund Math

Secondary tax codes (`S`, `SH`, `ST`, `SA`) do not impose an extra permanent tax. They withhold PAYE at the flat marginal bracket of combined income, and IRD automatically reconciles any overpayment after 31 March:
- **$45,000 + $15,000 (`SH` 30%):** $1,062.50 PAYE over-withheld during the year, refunded in full after 31 March.
- **$120,000 + $50,000 (`ST` 33%):** $0 PAYE overpayment, **$233.78** excess ACC refunded above the $156,641 levy cap.
- **$150,000 + $45,000 (`SA` 39%):** **$2,471.28** total refund ($1,800.00 PAYE + $671.28 excess ACC).

---

## Primary Official Sources

- Inland Revenue (IRD): [Individual tax rates](https://www.ird.govt.nz/income-tax/income-tax-for-individuals/tax-codes-and-tax-rates-for-individuals/tax-rates-for-individuals), [Tax codes](https://www.ird.govt.nz/income-tax/income-tax-for-individuals/tax-codes-and-tax-rates-for-individuals/tax-codes-for-individuals), [IETC](https://www.ird.govt.nz/income-tax/income-tax-for-individuals/individual-tax-credits/independent-earner-tax-credit-ietc)
- Inland Revenue (IRD): [KiwiSaver contributions & ESCT](https://www.ird.govt.nz/kiwisaver/kiwisaver-employers/contributions-and-deductions) and [Student loan repayments](https://www.ird.govt.nz/student-loans/living-in-new-zealand-with-a-student-loan/repaying-my-student-loan-when-i-earn-salary-or-wages)
- ACC: [Earner's Levy rates 2026/27](https://www.acc.co.nz/about-us/how-levies-work/levy-rates)

## Interactive Calculators and Embeds

- NZ PAYE calculator (2026/27): https://nzwage.nz/
- KiwiSaver & ESCT calculator: https://nzwage.nz/kiwisaver-calculator/
- Secondary tax calculator: https://nzwage.nz/secondary-tax-calculator/
- GST 15% calculator: https://nzwage.nz/gst-calculator/
- Lightweight iframe embeds (no sign-up): `https://nzwage.nz/embed/paye/`, `https://nzwage.nz/embed/kiwisaver/`, `https://nzwage.nz/embed/gst/`

## License and Citation

Licensed under [CC-BY-4.0](LICENSE). Citation metadata is in [`CITATION.cff`](CITATION.cff).

```text
NZWage (2026). NZWage Open Data 2026/27: New Zealand Effective PAYE Tax Burden, KiwiSaver ESCT Impact, and Secondary Tax Refunds [Dataset]. https://nzwage.nz/reports/ (CC-BY-4.0).
```
