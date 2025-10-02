🚢 Awesome Chocolate Shipment & Sales Analytics Dashboard
A Powerful Power BI Solution Built to Drive Data-Driven Decisions

About This Project
Working on the Awesome Chocolate shipment and sales dashboard gave me the opportunity to combine strong data modeling skills with business insight. The goal? To equip the supply chain and sales teams with clear, timely, and actionable intelligence that helps them optimize performance and increase profitability.

With thoughtfully designed DAX measures and an intuitive data model, this dashboard makes complex logistics and financial data easy to understand, fast to analyze, and simple to act upon.

***

## Features & Highlights

- **Dynamic Month-over-Month Analysis**  
  Measure growth and changes in shipments, sales, costs, and box counts for every month—aiding proactive business decisions.

- **Profit Intelligence & Target Tracking**  
  Real-time monitoring of profit margins, benchmarking against targets, and intelligent status flags to highlight achievements or risks.

- **Shipment Segmentation**  
  Analyze shipment size patterns, identify small-load trends, and optimize operations using the LBS % metric.

- **Fully Parameterized Model**  
  Advanced DAX logic adapts automatically to the latest available data; no manual intervention required.

***

## Core DAX Measures

| Measure Name                    | Description                                                         |
|---------------------------------|---------------------------------------------------------------------|
| **Total Shipments**             | Total number of shipments                                           |
| **Total Sales**                 | Aggregate revenue from shipments                                    |
| **Total Cost**                  | Sum of shipment costs                                              |
| **Total Profit**                | Net profit: Total Sales minus Total Cost                            |
| **Total Boxes**                 | Total number of boxes shipped                                       |
| **LBS Count / LBS %**           | Shipments with fewer than 50 boxes (count & percent)                |
| **MoM Shipments Change %**      | Month-over-month change in shipment count                           |
| **MoM Sales Change %**          | Month-over-month sales percentage change                            |
| **MoM Boxes Change %**          | Month-over-month box count percentage change                        |
| **MoM Cost Changes %**          | Month-over-month cost percentage change                             |
| **Profit %**                    | Profit margin (%)                                                   |
| **Profit Target**               | Target profit margin (default: 60%)                                 |
| **Profit Target Indicator**     | 2 = Above Target, 1 = Near Target, 0 = Below Target                 |

***

## Business Value

- **Optimize Efficiency:**  
  Instantly detect changes in shipments, cost, or margin. Take action before problems grow.

- **Executive-Ready Reporting:**  
  KPIs are tailored for fast, clear presentation with trend highlights and status indicators.

- **Scalable Design:**  
  All measures auto-update with new data. Extend or refresh for seamless insights.

***

## Sample DAX Calculations

```DAX
-- Total Shipments
Total Shipments = COUNTROWS(shipments)

-- Total Sales (Latest Month)
Total Sales Latest Month =
VAR ld = [latest date]
RETURN CALCULATE([Total Sales], 'calendar'[Start of Month] = ld)

-- Month-over-Month Sales Change %
latest MoM Sales Change % =
VAR ld = [latest date]
VAR this_month_sales = [Total Sales Latest Month]
VAR prev_month_sales = CALCULATE([Total Sales], 'calendar'[Start of Month] = EDATE(ld, -1))
RETURN DIVIDE(this_month_sales - prev_month_sales, prev_month_sales)
```

***

## Model Design Principles

- **Star-Schema Modeling:**  
  Robust relationships connect shipments and calendar tables for accurate, flexible time intelligence.

- **Readable & Maintainable:**  
  Measures are clearly named and documented, so others can quickly understand and extend the solution.

- **Performance Focus:**  
  DAX follows best practices for efficiency and scalability—ideal for real-world deployment.

***

## Getting Started

1. Connect to your shipments and calendar datasets.
2. Ensure calendar table [Start of Month] is a valid date field matching shipment data.
3. Refresh your data in Power BI—automatic calculations deliver fresh results instantly.

***

## Final Thoughts

This project is a showcase of practical analytics expertise and a business-driven mindset. The dashboard is ready to impress and deliver real value, standing out for its technical rigor and meaningful insights.

***
