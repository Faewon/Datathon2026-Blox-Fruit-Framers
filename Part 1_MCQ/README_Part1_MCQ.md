# 📋 Part 1 — Multiple Choice Questions (MCQ)

**Notebook:** `vintelligent_datathon_2026_MCQ.ipynb`  
**Team:** Blox Fruit Farmers  
**Competition:** VinTelligent Datathon 2026

---

## Description

This notebook solves all **10 multiple-choice questions** by performing direct calculations on the raw data — no guessing. Each question includes code that verifies the result.

---

## Input Data

Place all required CSV files in the **same directory** as the notebook (or update file paths in the code):


```
orders.csv
order_items.csv
products.csv
promotions.csv
payments.csv
returns.csv
customers.csv
geography.csv
inventory.csv
web_traffic.csv
sales.csv
```


---

## How to Run

**Run locally (Jupyter Notebook / VS Code):**

1. Put all CSV files in the same folder as the notebook.  
2. Open `vintelligent_datathon_2026_MCQ.ipynb`.  
3. Choose **Run All** (or `Kernel → Restart & Run All`) to execute cells from top to bottom.  
4. Each cell prints the computed result and confirms the correct answer.

> ⚠️ No extra configuration required — the notebook uses relative paths, so just ensure the CSVs are in the same folder.

---

## Answer Summary

| Q  | Question | Answer | Value |
|----|----------|--------|-------|
| Q1 | Median days between two consecutive purchases | **C) 144 days** | Median gap = 144.0 days |
| Q2 | Segment with highest gross margin | **D) Standard** | Gross margin ~31.3% |
| Q3 | Most common return reason (Streetwear) | **B) wrong_size** | 7,626 times |
| Q4 | Traffic source with lowest bounce rate | **C) email_campaign** | avg bounce = 0.004458 |
| Q5 | Share of order_items with promotions | **C) 39%** | Exact 38.7% |
| Q6 | Age group with highest avg orders | **A) 55+** | avg ~5.41 orders/customer |
| Q7 | Region with highest total revenue | **C) East** | ~7.29 billion VND |
| Q8 | Most common payment method (cancelled orders) | **A) credit_card** | 28,452 orders |
| Q9 | Size with highest return rate | **A) S** | return rate = 5.65% |
| Q10| Installment plan with highest avg value | **C) 6 periods** | avg ~24,446 VND |

---

## Required Libraries

```bash
pip install pandas numpy

