# 📊 Superstore Sales Analysis in Power BI

This project provides a comprehensive Power BI dashboard built using the Superstore Sales dataset from Kaggle. The dashboard includes data cleaning, DAX expressions, and interactive visualizations for business insights.This Power BI dashboard offers a data-driven narrative of retail performance based on the Superstore Sales dataset. It uncovers trends, inefficiencies, and profit-driving segments using interactive visuals, allowing stakeholders to make informed decisions with clarity and confidence.

🔗 Dataset Source: [Kaggle – Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)  
📈 Total Records: 110,527 rows  
📁 Columns: 14  

---

## 🛠️ Dataset Preparation

Before creating visualizations, the dataset undergoes transformation and formatting in Power BI’s Power Query Editor:

1. 🔄 Normalize Date Formats
   - Order Date and Ship Date columns had inconsistent formats like 04-26-2016 and 2/18/2025.
   - Used:  
     ```m
     Text.Replace([Order Date], "-", "/")
     ```
   - Converted column type from Text to Date.
   - Removed any rows with conversion errors (Right-click column → Remove Errors).

2. 🔢 Convert Numeric Columns
   - Transformed Discount, Profit, Quantity, and Sales from text to whole numbers or decimal where necessary.

3. ✅ Applied all transformations using Close & Apply.

---
## 🔍 Business Objective
- To analyze sales, profit, and shipping performance across different regions, product categories, and time periods in order to:

- Identify high-performing segments and products

- Monitor delivery and shipping trends

- Optimize sales strategy based on time and region

- Evaluate profit margins and discount effects
## 🧮 DAX Measures and Calculated Columns

DAX (Data Analysis Expressions) was used to generate key business metrics:

| Column / Measure     | Formula                                        |
|----------------------|------------------------------------------------|
| Total Sales          | `SUM('Supersales'[Sales])`                     |
| Total Quantity       | `SUM('Supersales'[Quantity])`                  |
| Total Profit         | `SUM('Supersales'[Profit])`                    |
| Average Discount     | `AVERAGE('Supersales'[Discount])`             |
| Order Year           | `YEAR('Supersales'[Order Date])`              |
| Delivery Days        | `DATEDIFF([Order Date], [Ship Date], DAY)`    |

---

## 📈 Visualizations in Power BI

The report includes the following interactive and informative visuals:

1. 📊 Column Chart  
   - X-axis: State  
   - Y-axis: Average Delivery Days  
   - 📌 Purpose: Identify states with delayed shipments.

2. 🧮 KPI Cards  
   - Metrics: Total Sales, Total Profit, Total Quantity, Average Discount  
   - 📌 Purpose: High-level snapshot of business performance.

3. 🎛️ Slicers  
   - Fields: Order Year, Region, Ship Mode  
   - 📌 Purpose: Filter all visuals dynamically based on user selection.

4. 🍩 Donut Chart  
   - Values: Ship Mode  
   - Details: Segment  
   - 📌 Purpose: Understand distribution of orders by shipping method and customer segment.

5. 🌳 Tree Map  
   - Group: Category  
   - Details: Sub-Category  
   - Values: Sum of Sales  
   - 📌 Purpose: Visualize sales contribution by product hierarchy.

6. 📉 Waterfall Chart  
   - Category: Sub-Category  
   - Y-axis: Total Profit  
   - 📌 Purpose: Show how each product contributes positively or negatively to total profit.

7. 📈 Line Chart  
   - X-axis: Order Month (derived from Order Date)  
   - Y-axis: Sales  
   - 📌 Purpose: Analyze monthly sales trends over time.

---
## 🗣️ Dashboard Insights: The Story Behind the Numbers

Let’s take a walk through our latest **Superstore Sales Dashboard** and unpack the story the data is telling us. Here are the highlights:

---

### 1. 🟦 Regional Delivery Performance
We started by looking at **how delivery times vary across states**. What’s reassuring is that states like **New York, California, and others show very consistent delivery days**. There's no major outlier here, which speaks well of our logistics and supply chain performance. This consistency means we likely have **a standardized shipping process working smoothly across regions**.

---

### 2. 📅 Monthly Sales Trend
Next, the sales trend over time told an interesting story:  
**January is our peak performer** — both in terms of **sales volume and profit**. This could be due to **new-year promotions, budget resets**, or just consumer behavior after the holidays.  
If we’re not already doing it, we should consider **doubling down on January campaigns** to ride that wave even more effectively.

---

### 3. 📈 Key Performance Indicators
Zooming out to our KPIs:
- **Total Profit**: 218  
- **Total Quantity Sold**: 2 million units  
- **Sales Transactions**: 218  
- **Discount Events**: 218

These are solid baseline numbers. While the exact volume may be sample-based here, the key takeaway is that we're seeing **steady performance** in terms of sales and profitability. This gives us a reliable top-level view to compare against specific timeframes or campaigns.

---

### 4. 📦 Category & Sub-Category Breakdown
The **tree map visualization** showed something valuable:  
**Technology and Office Supplies are our major drivers**.  
Within that, **Phones, Copiers, Binders, and Chairs** stand out in volume. This helps us know where to focus our inventory, marketing, and promotions. If any of these are running low or have limited deals, we might be missing out on easy wins.

---

### 5. 💰 Profitability Breakdown
Now, profit tells a slightly different story than just volume.  
The **waterfall chart** highlights both the heroes and the underperformers:
- **Phones and Copiers** are **profit stars** — high margin and high volume.
- But **Binders and Machines** are dragging us down, possibly due to **heavy discounts** or poor pricing strategy.

This is a strong signal to **review pricing or bundling options** for the low performers and **amplify what’s working well**.

---

### 6. 🚚 Shipping & Customer Segments
Finally, one more big insight:  
**60% of our orders come from the Consumer segment, and most of them use Second Class shipping.**  
That’s an opportunity. We might consider **upselling to First Class or Same Day shipping**, or we could **target Corporate clients more aggressively** — they’re underrepresented and could be a high-value segment if tapped correctly.

---

### 📌 In Summary:
- We’re **operationally solid**, especially on the delivery front.
- **January is gold** – let’s lean into it more.
- **Phones and Copiers** are leading the way in profit.
- There’s untapped potential in **shipping upgrades** and **underperforming categories**.

## ⚙️ Interactivity and UX Features
- Slicers for Year, Region, and Ship Mode enable dynamic filtering.

- Tooltips and hover info allow deeper insight without cluttering visuals.

- Unified dashboard design ensures intuitive navigation and data exploration.

## 📌 Business Implications
- Focus marketing efforts in January for maximum ROI.

- Re-evaluate pricing or discount strategies for loss-making sub-categories.

- Optimize inventory and delivery strategies for top-selling items like Phones and Chairs.

- Promote Consumer segment offerings further with personalized campaigns.


## 🚀 Getting Started

To run this project locally:

1. Download the Superstore dataset from the Kaggle link above.
2. Open Power BI Desktop.
3. Load the dataset → Apply the transformations.
4. Add DAX measures as listed above.
5. Create visuals on separate report pages or a unified dashboard.
6. Customize styles and interactions as needed.

---


## 📜 License

This project is provided for educational and analytical purposes. Dataset © Kaggle/Vivek468.
