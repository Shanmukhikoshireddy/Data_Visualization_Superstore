# 📊 Superstore Sales Analysis in Power BI

This project provides a comprehensive Power BI dashboard built using the Superstore Sales dataset from Kaggle. The dashboard includes data cleaning, DAX expressions, and interactive visualizations for business insights.

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

## 🧩 Interactivity Features

- All visuals are dynamically linked using slicers.
- Tooltips provide rich drill-down details.
- Error-handling and formatting ensure clean, accurate visuals.

---

## 🚀 Getting Started

To run this project locally:

1. Download the Superstore dataset from the Kaggle link above.
2. Open Power BI Desktop.
3. Load the dataset → Apply the transformations.
4. Add DAX measures as listed above.
5. Create visuals on separate report pages or a unified dashboard.
6. Customize styles and interactions as needed.

---

## 📌 Screenshots

You can optionally include screenshots of your dashboard pages here.

---

## 📜 License

This project is provided for educational and analytical purposes. Dataset © Kaggle/Vivek468.
