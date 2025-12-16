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

## Business Questions (Buyer Advocacy + Investor Lens):
1. How did average sale prices move across 2016–2018 (trend + seasonality)?
2. Where are price premiums concentrated (Region/Suburb)?
3. What property profiles dominate sales volume (Rooms, Land Size)?
4. Which Region × Rooms combinations show stronger “value opportunity” signals vs price?
   
---

## Dashboard Components:

### 1) Average Sales Price (Monthly Trend):

<img width="1778" height="1047" alt="image" src="https://github.com/user-attachments/assets/7aaf5d68-1066-419b-b1b6-d0350e1f0149" />

**Insights:**
- **Trend (2016–2018)**: Prices rise steadily through 2016 into early 2017, then soften and largely stabilise from mid-2017 through early 2018, indicating a shift from growth to a more moderated market.
- **Seasonality & Volatility**:
  - Peaks cluster around early–mid 2017, with a noticeable dip in mid-2017. There were major policy and credit events around mid-2017 that linked to softer conditions in both Melbourne and Sydney, especially tighter mortgage lending and policy changes affecting demand.
  - After the sharp dip, the market rapidly mean-reverted back into the ~$1.2–$1.3M band, suggesting the dip was likely a short-lived shock or sales-mix effect rather than a sustained downturn.

---

### 2) Region / Suburb Price Map:

<img width="2528" height="1562" alt="image" src="https://github.com/user-attachments/assets/26ba9a69-d633-47d6-8416-2414a6638226" />

**Insights:**
- **Premium clusters**: The strongest premium cluster is concentrated in the **Southern Metropolitan inner-city** (e.g., postcode 3142 showing ~$3563k average), with adjacent inner-metro areas around the CBD also trending higher.
- **Affordable zones**: The most affordable zones are predominantly to the **north-west and far south-east** (lighter yellow areas), where averages are consistently lower and the premium intensity fades as distance increases.
  
---

### 3) Distribution of House Prices:

<img width="2482" height="1538" alt="image" src="https://github.com/user-attachments/assets/cc84276b-4683-4f40-bba1-fa882a5b6a3d" />

**Insights**
- **Skewness**: The price distribution is strongly right-skewed, with most transactions clustering in the lower-to-mid price bins, and a long tail stretching into higher prices.
- **Typical price range**:The highest transaction density sits roughly around **$600k–$1.5M**, with the mode concentrated near **$800k–$1.2M**.
- **Outliers**: There are clear high-end outliers (i.e., low frequency but very expensive sales) that can pull the average upward, so median or averages are more representative for “typical” buyers.

---

### 4) Distribution of Rooms:

<img width="1516" height="1562" alt="image" src="https://github.com/user-attachments/assets/441fc0ab-d1dd-481e-925f-63132493e452" />

**Key questions answered:**
- **Dominant number of bedrooms**: The market is overwhelmingly concentrated in **3-bedroom homes**, followed by 4-bedroom and 2-bedroom homes form a smaller but still meaningful share.
- **Niche segments**: **1-bedroom** and **6+ bedroom properties (6, 7, 8, 10, 12 rooms)** are very low volume and should be interpreted cautiously in pricing or value comparisons, as small sample sizes can create unstable averages.

---

### 6) Distribution of Land Size:

<img width="2050" height="1334" alt="image" src="https://github.com/user-attachments/assets/cb961f64-3343-40eb-a84a-c9a6fcde7213" />

**Insights:**
- **Typical land size**: Transactions are heavily concentrated in standard suburban block sizes, with the **highest frequency** around roughly **500–700 sqm**, and **most sales** falling broadly within **~200–900 sqm**.
- **Long-tail**: Distribution shows a strong right tail **>1,000 sqm**, extending into multi-thousand sqm with rare extreme lots, indicating a small volume of large-site transactions that can behave differently from typical residential and should be analysed separately for development or land-banking use cases.

---

### 7) Price by Region & Rooms Heatmap ($000s):

<img width="1602" height="432" alt="image" src="https://github.com/user-attachments/assets/bef96ab9-5c68-4b5f-9d85-78d6e4ff4c0f" />

**Insights:**
- **Premium zones for larger homes**: **Southern Metropolitan** is the clear premium market for larger homes, with 5–6 room homes reaching the **highest averages** (e.g., ~$2.6M for 5 rooms and ~$3.1M for 6 rooms). **Western Metropolitan** and **Eastern Metropolitan** also show higher pricing as the number of rooms increases, but at a lower tier than Southern Metro.
- **Strongest price jump per additional room**: In **Southern Metropolitan**, price jumps sharply when moving from 4 → 5 → 6 rooms. Smaller step-ups also appear in **Western Metropolitan** (especially 4 → 5 rooms) and **Eastern Metropolitan** (from 4 → 6 rooms), with smaller steep increases compared to Southern Metro.

---

### 8) Value Opportunity Heatmap:

<img width="1626" height="424" alt="image" src="https://github.com/user-attachments/assets/b8f3eeb9-5b5c-439d-8cd7-55a781a2b610" />

**Insights:**
-

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
