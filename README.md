# ASOS Product Catalogue Analysis

Exploratory data analysis of the ASOS product catalogue (~30,000 products) to extract actionable business insights on brand strategy, pricing, stock management and colour trends.

---

## 📁 Project Structure

```
asos-analysis/
├── data/
│   ├── raw/                  # Original dataset (products_asos.csv)
│   └── processed/            # Cleaned dataset (asos_clean.csv)
├── notebooks/
│   ├── cleaning.ipynb        # Data cleaning & feature engineering
│   └── analysis.ipynb        # Exploratory analysis & insights
└── README.md
```

---

## 🔧 Dataset & Feature Engineering

**Source** : [Kaggle — ASOS Product Dataset]([https://www.kaggle.com/](https://www.kaggle.com/datasets/trainingdatapro/asos-e-commerce-dataset-30845-products?resource=download))

Raw data contained product names, prices, colours and size availability strings.
The following features were engineered from scratch in `cleaning.ipynb` :

| Feature | Description |
|---|---|
| `brand` | Extracted from product name via whitelist + regex fallback |
| `brand_group` | Normalized brand variants (e.g. "ASOS DESIGN Tall" → "ASOS DESIGN") |
| `category` | Keyword-based classification (outerwear, top, bottom, dress, skirt) |
| `base_color` | Normalized to 11 base colours from raw colour strings |
| `nb_sizes_total` | Total number of sizes offered per product |
| `nb_sizes_available` | Number of sizes currently in stock |
| `has_out_of_stock` | True if at least one size is out of stock |
| `fully_out_of_stock` | True if all sizes are out of stock |
| `price_segment` | Bucketed price ranges (<£20, £20-50, £50-100, >£100) |

---

## 📊 Key Findings

### 1. Brand Strategy
- ASOS own-brands (ASOS DESIGN, ASOS EDITION, etc.) represent **~73% of the catalogue**
- ASOS DESIGN alone accounts for ~4,200 products — nearly 4x more than the second brand (Topshop)
- → ASOS operates a clear own-brand dominant strategy to control margins and reduce supplier dependency

### 2. Pricing
- The core offering sits between **£20–£50**, confirming a mid-market positioning
- Outerwear is the most expensive category (~£88 avg), tops the most accessible (~£29 avg)
- A small premium offer exists but remains marginal

### 3. Stock Management
- **53% of products** have at least one size out of stock
- On average, **~2 sizes out of 6.6 are unavailable** per product (~30% of the size offer)
- Out-of-stock rates are homogeneous across categories (40–60%) and brands (70–80% for top 10)
- → This points to a structural restocking issue across the entire catalogue, not isolated to specific categories

### 4. Colour Trends
- **Black dominates** at 26% of all products — consistent across all categories
- Green is notably overrepresented in dresses (1,036 products), suggesting a category-specific trend
- White performs strongly in tops (975 products), aligned with everyday basics demand

---

## 🛠️ Tools

- **Python** — Pandas, Matplotlib, Seaborn
- **Jupyter Notebook**

---

## 👤 Author

**Fernand Gatera** — Data Analyst in training @ BeCode Brussels (BXL-Bouman-10)  
[LinkedIn](https://www.linkedin.com/in/fernand-gatera-a11613345) · [GitHub](https://github.com/ndinhoo)
