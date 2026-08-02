# Supply Chain Audit — Loss & Late-Delivery Diagnosis

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge)
![EDA](https://img.shields.io/badge/EDA-1E3C73?style=for-the-badge)

> **The dataset reported a 54.8% late-delivery rate. Once cancelled orders were removed from the denominator, the real rate was 57.29% — worse, not better. And the 18.71% loss rate had no single cause anywhere in the catalog.**

---

## 📌 Project Overview

A data audit of **180,519 supply chain transactions**, investigating two separate, unrelated-looking problems that turned out to share the same shape: neither had a single fixable cause.

1. Why do **18.71% of orders lose money**?
2. Why does the reported **54.8% late-delivery rate** not hold up under scrutiny?

Both answers point toward the same conclusion — these are **structural, catalog-wide and schedule-wide issues**, not problems traceable to one product, region, or customer segment.

---

## 🎯 Business Problem

Two KPIs looked actionable on the surface — a loss rate and a late-delivery rate — but neither had an obvious lever attached to it. Before recommending any fix, the real questions were:

- **Is the loss concentrated** in a specific category, product, or discount tier — or is it spread everywhere?
- **Is the reported late-delivery rate even correct**, or is it distorted by how cancelled orders are counted?
- **Are all shipping modes "late" for the same reason**, or are there two different problems hiding under one number?
- **Does region, segment, or time period explain any of it?**

---

## 🔍 Key Findings

| Finding | Evidence |
|---|---|
| **The loss isn't concentrated anywhere** | 33,784 of 180,519 orders (18.71%) lose money. Tested individually across category, product, discount rate, order quantity, and delivery status — the loss rate holds at ~18–19% no matter how the data is sliced |
| **The real late-delivery rate is worse than reported** | Excluding cancelled orders from the denominator, the true late rate among orders that actually shipped is **57.29%** — not the reported 54.8% |
| **Late orders run ~1.62 days over** on average, once they are late | |
| **Two distinct delay problems exist under one metric** | First Class and Same Day appear "late" almost every time because their promised windows (1 day / 0 days) are unrealistically tight — a **promise problem**, not an execution problem |
| **Second Class is the real execution gap** | Scheduled for 2 days, but runs 2.5+ days over on **79.8%** of its orders — the one shipping mode that genuinely needs an operational review |
| **Region was ruled out** | Late rate stays within ~55–60% across all 21 regions |
| **Customer segment was ruled out** | Late rate varies by less than half a point across segments |
| **Time was ruled out** | Both the loss rate and late rate stayed flat across 33 months — no trend, no seasonality driving either problem |

---

## 💰 Business Impact

- Because the loss rate is **flat across every dimension tested** (product, category, discount, quantity), it rules out quick fixes like discontinuing a product or adjusting one discount tier — the real issue is a **margin structure problem across the catalog**
- Fishing, Cleats, and Camping & Hiking show the **largest losses in raw dollar terms** — but this is a volume effect: they are also the **most profitable categories overall**, meaning cutting them would remove more profit than loss
- Splitting the delivery problem into two separate fixes (promise vs. execution) prevents a wasted operational review of First Class/Same Day, where the fix is actually a **scheduling change, not a logistics fix**
- Second Class is now clearly isolated as the **single shipping mode carrying a real fulfillment problem**, focusing operational resources where they'll actually move the number

---

## ✅ Recommendations

1. **Treat the loss rate as a pricing/margin issue, not an operational one** — no single product, category, or discount level explains it; the right next step is a **category-level margin audit**, not a profit audit
2. **Split the delivery fix in two:**
   - Review **Second Class** operations specifically — it's the one mode with a genuine execution gap
   - Separately, **re-set the promised delivery windows** for First Class and Same Day — the problem is the promise, not the fulfillment
3. **Protect investment in Fishing, Cleats, and Camping & Hiking** — their dollar losses are a volume effect, not a sign of underperformance; they remain the most profitable categories overall

---

## 🛠 Technical Stack

| Tool | Usage |
|---|---|
| **Python (Pandas, NumPy)** | Data cleaning, aggregation, multi-dimensional slicing |
| **Matplotlib / Seaborn** | Distribution profiling, trend visualization |
| **EDA Methodology** | Group comparisons, distribution profiling, time-trend checks — used to systematically rule out causes rather than confirm assumptions |

---

## 🔬 Methodology

The investigation followed an **elimination approach** rather than a confirmation approach — testing each plausible cause individually and ruling it out if the metric didn't move:

```
Loss Rate (18.71%) tested against:
    ├── Category        → no concentration found
    ├── Product          → no concentration found
    ├── Discount Rate    → no concentration found
    ├── Order Quantity   → no concentration found
    └── Delivery Status  → no concentration found
    Result: structural, catalog-wide margin issue

Late-Delivery Rate tested against:
    ├── Cancelled orders in denominator  → distorted the rate (54.8% → 57.29% real)
    ├── Shipping mode                     → revealed TWO separate problems
    ├── Region (21 regions)               → ruled out (~55-60% everywhere)
    ├── Customer segment                  → ruled out (<0.5pt variance)
    └── Time (33 months)                  → ruled out (flat trend)
    Result: schedule-design + one execution gap (Second Class)
```

---

## 📁 Repository Structure

```
Supply-chain-analysis-python-project/
│
├── Supply_chain_python_project_v2.ipynb
└── README.md
```

**Dataset:** [DataCo Smart Supply Chain (Kaggle)](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis) — not included in this repo due to size. Download separately and place the CSV in the same folder as the notebook before running.

---

## 🔗 Connect

**Fares Mubarak** — Data Analyst

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/fares-mubarak)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Fares-Mubarak)
[![Portfolio](https://img.shields.io/badge/Portfolio-1E3C73?style=for-the-badge)](https://fares-mubarak.super.site)

---

*Built to demonstrate rigorous elimination-based analysis — ruling out causes systematically rather than confirming the first plausible explanation.*
