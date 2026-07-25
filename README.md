# Supply Chain Audit: Diagnosing a 57.29% Late-Delivery Rate & an 18.71% Loss-Making Order Rate 📈

## 📌 Project Overview
A data audit of **180,519 supply chain transactions**, investigating two separate questions: why **18.71%** of orders lose money, and why the dataset's reported **54.8% late-delivery rate** doesn't hold up once cancelled orders and shipping-mode differences are accounted for. Both findings point away from a single fixable cause and toward structural, catalog-wide and schedule-wide issues.

## 📊 Key Insights & Results

* **The Loss Isn't Concentrated Anywhere:** 18.71% of orders (33,784 of 180,519) lose money. Category, product, discount rate, order quantity, and delivery status were all tested individually — none of them explain it, the loss rate stays around 18-19% no matter how the data is sliced. This points to thin margins spread across the catalog, not one fixable lever (product, discount, or category).

* **The Real Late-Delivery Rate Is Higher, Not Lower:** After excluding cancelled orders from the denominator, the true late rate among orders that actually shipped is **57.29%** — not the reported 54.8%. Orders that do run late are late by **1.62 days** on average.

* **Two Different Delay Problems:** First Class and Same Day look "late" almost every time mainly because their scheduled windows (1 day / 0 days) are unrealistically tight — a **promise problem**. Second Class, scheduled for 2 days but running 2.5 days over on 79.8% of orders, is a genuine **execution problem** — the one mode that actually needs an operational review.

* **Region and customer segment were ruled out:** late rate stays within ~55-60% across 21 regions and within half a point across customer segments, and both loss rate and late rate stayed flat across 33 months with no trend — both problems look systemic, not tied to one product, place, customer type, or time period.

## 🚀 Recommendations

* **Treat the loss rate as a pricing/margin issue, not an operational one.** No single product, category, or discount level explains it — a category-level margin audit (not just profit) is the right next step.
* **Split the delivery fix in two:** review Second Class operations specifically (it's the one mode with a genuine execution gap), and separately re-set the promised delivery windows for First Class and Same Day, since it's the promise — not the fulfillment — driving their numbers.
* **Protect investment in Fishing, Cleats, and Camping & Hiking** — they show the largest losses in raw dollar terms, but that's a volume effect; they're also the most profitable categories overall.

## 🛠️ Tools Used
* **Python** (Pandas, NumPy)
* **Data Visualization** (Matplotlib, Seaborn)
* **Exploratory Data Analysis** (group comparisons, distribution profiling, time-trend checks)

## 📂 File Structure
* `Supply_chain_python_project_v2.ipynb`: Full analysis and visualization.
* `README.md`: Project summary and findings.

*Dataset: [DataCo Smart Supply Chain (Kaggle)](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis). Not included in this repo due to size — download separately and place the CSV in the same folder as the notebook before running.*

---

## 🔗 Connect with Me
* **Portfolio:** [https://fares-mubarak.super.site/]
* **LinkedIn:** [https://www.linkedin.com/in/fares-mubarak/]
