# Distribution Network Efficiency: Optimizing Factory-to-Customer Shipping Routes

## 📌 Executive Summary & Background
This project analyzes the logistics and shipping efficiency of a national US candy distributor. By leveraging geospatial and sales data, this analysis identifies bottlenecks in the distribution network and provides actionable recommendations to optimize factory-to-customer delivery routes.
**Data Source:** US Candy Distributor dataset (via Maven Analytics).

## ❓ Business Questions
* Which factory-to-customer shipping routes are the most efficient?
* Which shipping routes are the most inefficient?
* Which products generate the best profit margins?
* Which products should be relocated to another factory to optimize shipping?

## 🛠 Tools & Methodology
* **Tools:** Power BI, Microsoft Excel.
* **Data Transformation:** Cleaned logistics data using Power Query, replaced decimal delimiters (converting dots to commas), and filtered strictly for United States operational areas.
* **Data Modeling:** Built a Star Schema connecting `Fact_Candy_Sales` with dimension tables (`Dim_Products`, `Dim_Locations`, `Dim_Date`).
* **Distance & Efficiency Calculation:** Instead of relying on basic mapping, I utilized the Haversine formula based on latitude and longitude coordinates to accurately calculate the spherical distance (in kilometers) between factories and customer locations. These distances were then scored to flag routes as "efficient" (< 1.1), "quite efficient" (1.1 - 1.5), or "inefficient" (> 1.5).

---

## 📊 Dashboard & Insights

### 1. Exploratory Data Analysis (EDA)
> *This section utilizes Exploratory Data Analysis (EDA) to uncover general insights and give a comprehensive overview of the underlying data.*

![EDA Dashboard](https://github.com/ulfazarina-coder/factory-shipping-optimization/blob/main/Exploratory%20Data%20Analysis.png?raw=true)

**Key Findings:**
* **Overall Performance:** The business sold 37.873K units across 8.389K orders, generating a total revenue of $138.83K.
* **Profitability:** Total gross profit stands at $91.51K, resulting in a profit margin of 65.91%, with an Average Order Value (AOV) of $16.55 per order.
* **Time Trends:** Sales and gross profit trends spanning from 2021 to 2024 display a fluctuating pattern, culminating in an upward trajectory toward the end of the period.
* **Product Performance:** Chocolate-based products continue to dominate, accounting for 95.95% of all orders. The *Wonka Bar - Triple Dazzle* secured the top spot for sales volume, while the *Wonka Bar - Nutty Crunch* fell to fifth place.
* **Geographical Distribution:** Texas and Illinois maintain their positions as the primary sales destinations, closely followed by emerging strong contributions from Ohio and California.
* **Factory Contribution:** The *Lot's O' Nuts* factory processes the majority of the orders at 55.66%, followed by *Wicked Choccy's* at approximately 40%.

### 2. Efficient Factory Analysis
> *This section is designed to evaluate shipping route efficiency, highlighting the most and least optimal delivery paths from factories to customers.*

![Efficient Factory Details](https://github.com/ulfazarina-coder/factory-shipping-optimization/blob/main/Efficient%20Factory%20Details.png?raw=true)

**Key Findings:**
* **Overall Route Efficiency:** Delivery routes show a near-even split in optimization, with 52.41% of orders successfully fulfilled by the nearest available factory. Conversely, 47.59% of orders were dispatched from further locations.
* **Distance Score Breakdown:** 4.2K orders are categorized as "efficient" with a score below 1.1. However, a substantial volume of 3.5K orders is classified as "inefficient" (scoring above 1.5), leaving 0.7K orders in the "quite efficient" range.
* **Average Shipping Distance:** *Sugar Shack* and *The Other Factory* record the longest average shipping distances at 2.6K KM. Meanwhile, *Secret Factory* maintains the shortest average distance at 1.8K KM.
* **Optimal vs. Inefficient Routing:** The analysis identifies that the most efficient shipping routes occur when *Lot's O' Nuts* fulfills orders for the Western region, and *Wicked Choccy's* serves the Eastern region. The most inefficient routes happen when *Lot's O' Nuts* ships products all the way to the Eastern region, and when *Wicked Choccy's* ships to the Western region.
* **Profit Margin Leaders:** While *Everlasting Gobstopper* (80%) and *Hair Toffee* (78%) hold the highest individual percentage margins, their sales volumes are minimal. Among high-volume drivers, *Wonka Bar - Nutty Crunch Surprise* (71%) and *Wonka Bar - Scrumdiddlyumptious* (69%) deliver the strongest margins while generating the bulk of actual profit.

---

## 💡 Strategic Recommendations

1. **Optimize Distribution Routes by Relocating Production:** The most inefficient shipping routes occur when the *Lot's O' Nuts* factory ships to the Eastern US, where the majority of customer orders are located. To resolve this, the production of *Wonka Bar - Fudge Mallows*, *Wonka Bar - Nutty Crunch Surprise*, and *Wonka Bar - Scrumdiddlyumptious* should be relocated from *Lot's O' Nuts* to *The Other Factory*, which is geographically closer to the East.
2. **Focus Marketing on High-Margin Chocolate Products:** Chocolate-based products heavily dominate the business, making up 95% of all orders. The company should prioritize marketing efforts on *Wonka Bar - Nutty Crunch Surprise* and *Wonka Bar - Scrumdiddlyumptious*, as they provide the best balance of high customer demand and strong profit margins.
3. **Align Inventory with Peak Seasons:** The historical 5-year monthly trend reveals two consistent high seasons occurring every year in March and May. The supply chain team should ramp up production and stock up on top-selling chocolate products ahead of these specific months to capture maximum revenue and prevent stockouts.
