# Melbourne House Tableau Sales Dashboard (2016–2018): 

A descriptive analytics dashboard built for a buyer’s advocacy use case, using Melbourne real estate sales data (2016–2018). The dashboard helps identify price patterns, location premiums, buyer demand segments, and potential “value opportunity” zones for real estate investors.
  
[View on Tableau Public](https://public.tableau.com/app/profile/hoang.thanh.truc.nguyen/viz/MelbourneHouseSalesDashboard2016-2018/Dashboard1)

<img width="3414" height="1642" alt="image" src="https://github.com/user-attachments/assets/062d33c6-8f79-4f79-ae50-114ba2f57eae" />

---

## Dataset

Dataset source: [Melbourne Housing Market (Kaggle)](https://www.kaggle.com/datasets/anthonypino/melbourne-housing-market)

Dataset fields:
- Suburb, RegionName, Price (AUD - $000s), Date sold, Rooms (bedrooms), Distance (km to CBD), Postcode, LandSize (sqm), MarketValueIndex

---

## Business Questions (Buyer Advocacy + Investor Lens)
1. How did average sale prices move across 2016–2018 (trend + seasonality)?
2. Where are price premiums concentrated (Region/Suburb)?
3. What property profiles dominate sales volume (Rooms, Land Size)?
4. Which Region × Rooms combinations show stronger “value opportunity” signals vs price?

---

## Tools
- Tableau (Dashboard build and publishing)
- Excel (data sanity checks / optional supplementary stats)
- GitHub (project documentation and reproducibility)

---

## Setup / How to View (similar to the reference repo’s “Setup/Run” sections)  [oai_citation:5‡GitHub](https://github.com/Nidheesh-Panchal/melbourne-housing)
### Option A — View Online
Open the Tableau Public link:
https://public.tableau.com/views/MelbourneHouseSalesDashboard2016-2018/Dashboard1

### Option B — Open Locally (Recommended for recruiters)
1. Download `tableau/MelbourneHouseSalesDashboard_2016_2018.twbx`
2. Open in Tableau Desktop (or Tableau Reader)
3. If prompted, refresh the extract / reconnect data

---

## Dashboard Walkthrough (Component-by-Component)
This section follows the portfolio style of the reference repo: concise screenshots + what each visual answers.  [oai_citation:6‡GitHub](https://github.com/Nidheesh-Panchal/melbourne-housing)

### 1) Filters Panel
**What it does:** supports market segmentation for buyer scenarios (budget, location, property type proxy).
- Date range (Month & Year)
- RegionName
- Price Range
- Distance from CBD
- Rooms
- Land Size
- Postcode (granular targeting)

![Filters](assets/filters_panel.png)

**Why it matters (buyer advocacy):**
Helps tailor recommendations to different buyer profiles (first-home buyers vs family upgraders vs investors).

---

### 2) Average Sales Price (Monthly Trend)
**Chart:** line chart of average price over time.

![Trend](assets/trend_avg_price.png)

**Key questions answered:**
- Is the market trending up/down in 2016–2018?
- Are there seasonal peaks/dips worth noting?

---

### 3) Region / Suburb Price Map
**Chart:** filled/area map showing relative price intensity.

![Map](assets/map_region_suburb.png)

**Key questions answered:**
- Where are premium clusters vs affordable zones?
- How does the pattern change after filtering by Distance, Rooms, Land Size?

---

### 4) Distribution of House Prices
**Chart:** histogram of Price.

![Price Hist](assets/hist_price.png)

**Key questions answered:**
- Is the distribution skewed? (usually right-skewed in housing)
- Are there outliers that distort averages?
- What does the “typical” price band look like?

---

### 5) Distribution of Rooms (Bedrooms)
**Chart:** histogram of Rooms.

![Rooms Hist](assets/hist_rooms.png)

**Key questions answered:**
- What bedroom counts dominate the market?
- Which segments are niche (low volume) and should be treated carefully?

---

### 6) Distribution of Land Size
**Chart:** histogram of Land Size with a sensible bin range (e.g., 0–2000 sqm) for typical residential blocks.

![Land Hist](assets/hist_landsize.png)

**Key questions answered:**
- What is the “typical” lot size band in this dataset?
- How large is the long-tail (development/land-banking style lots)?

---

### 7) Heatmap — Price by Region & Rooms
**Chart:** Region (rows) × Rooms (columns), colored by Avg Price.

![Price Heatmap](assets/heatmap_price.png)

**Investor use:**
Shows where larger homes command a premium, and where incremental rooms increase price significantly.

---

### 8) Heatmap — Value Opportunity Score (Region × Rooms)
**Chart:** Region × Rooms, colored by Value Opportunity Score.
(Define clearly how Value Score is computed; e.g., a scaled ratio using MarketValueIndex relative to Price.)

![Value Heatmap](assets/heatmap_value_score.png)

**Investor use:**
Highlights segments that may be “better value” relative to benchmark signals (MarketValueIndex), not simply the most expensive.

---

## Key Insights (Fill with your observed outcomes)
From the dashboard views (after checking with filters):
1. **Trend:** Average sales prices were [stable/rising/volatile] across 2016–2018 with [notable dip/spike] around [month/year].
2. **Location premium:** Higher prices cluster in [regions/suburbs], while [regions] remain relatively affordable after controlling for Distance/Rooms.
3. **Demand profile:** Most sales concentrate in [3–4] bedroom homes and [~400–700 sqm] lots (indicative of family demand).
4. **Value opportunities:** Stronger Value Scores appear in [Region × Rooms] combinations, which may be attractive for investor screening (validate with sales counts).

---

## Recommendations (PropertyExperts Buyer Advocacy)
1. Use the **Value Opportunity Heatmap** to create an initial investor shortlist, then validate with transaction volume (avoid thin-sample cells).
2. Use **Distance-from-CBD** + **Rooms** to differentiate:
   - “Lifestyle premium” zones (inner/near-CBD)
   - “Yield/value” zones (mid/outer ring, family stock)
3. Treat extreme price / land size observations as a separate “development site” lens; do not mix with typical residential buyer guidance.

---

## Assumptions & Limitations
- Price unit interpretation (AUD vs AUD $000s) must be explicitly stated.
- MarketValueIndex methodology is not provided; Value Score is used as a **screening signal**, not a formal valuation model.
- Cells with low count in heatmaps can be unstable; add a minimum-sales-count rule if extending.

---

## Files in This Repo
- `/assets` screenshots used in README
- `/tableau` packaged workbook + build notes
- `/docs` business context and data dictionary
