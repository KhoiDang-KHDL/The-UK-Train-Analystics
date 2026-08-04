# UK Train Reporting — Improving Operational Efficiency

> Analysis of UK train ticketing and journey data to identify the root causes of delays/cancellations, optimize refund costs, and improve customer satisfaction through customer segmentation.

---

## 1. Business Problem

The company has observed an increasing trend of train delays and cancellations, which has led to higher refund costs and lower customer satisfaction. Root-cause analysis is needed to understand *why* trips fail, how customers behave when purchasing tickets and traveling, and how operations can be optimized to reduce financial losses and improve the overall customer experience.

**Current situation:**
- On-time performance sits around **87%**, meaning **13%** of trips are unsuccessful (delayed or cancelled).
- **~26.8%** of unsuccessful trips result in a refund request, costing the company **~5.2% of total ticket revenue (£38,702)**.

---

## 2. Objective

The project is structured around two main pillars: **minimizing the impact of unsuccessful trips** and **enhancing customer satisfaction through segmentation**.

### 2.1 Minimizing the effect of unsuccessful trips
- **Reducing Delay & Cancellation Cases** — What are the main causes of delays/cancellations? When and where do they occur most frequently?
  - Metrics: Delay/Cancel Rate (%), Average Delay Time, Root Cause Distribution, On-time Performance
- **Optimizing Refund Cost** — How much does the company spend on refunds, and which failure reasons drive the highest refund cost?
  - Metrics: Refund Rate (%), Average Refund Amount per Ticket, Refund Reason Breakdown, Refund Cost / Total Revenue

### 2.2 Enhancing customer satisfaction through customer segmentation
- **Understanding Purchase Behavior** — How do customers purchase tickets (channel, payment method, booking lead time), and how can this inform pricing and sales channel optimization?
  - Segmented by: Date/Time of Departure, Purchase Type, Purchase Method, Ticket Information
- **Understanding Travel Behavior** — How do customers travel (trip length, time of day, ticket class), and what add-ons or experience packages could be proposed for each segment?
  - Segmented by: Date/Time of Departure, Trip Length, Ticket Information

### 2.3 Key questions answered in the analysis
1. Which factors contribute to the 13% unsuccessful trip rate, and when do they peak?
2. What are the main reasons behind refund payments, and which ones are the most costly?
3. What drives the shift in purchase channel (Online vs. Station) over time, and why?
4. When do customers travel the most, and what trip types/fare categories do they prefer?

### 2.4 Project Goals
- Reduce delay & cancellation rate from **15% → 5–10%**
- Decrease avoidable refund costs from **~26% → 15%**
- Improve customer satisfaction and trip profitability through better operational insights

---

## 3. Tools Used

| Category | Tool |
|---|---|
| Data cleaning & transformation | Python |
| Data modeling & DAX calculations | Power BI / Excel Power Pivot) |
| Dashboard & visualization | Power BI |
| Reporting & presentation | Canva |

---

## 4. Key Results & Recommendations

### 4.1 Operational Insights
- **On-time performance: 87%**, with 13% of trips unsuccessful (53% delayed, 47% cancelled). The delay–cancel ratio stays stable across months.
- **Weather (32.9%)** is the top external cause of delay; **Signal Failure (23.3%)** and **Technical Issues (16.9%)** are the main operational factors.
- **Average delay is 42 minutes** — Staff Shortage causes the longest average delay (75 mins), while Technical Issues resolve fastest.
- **Morning** records the highest share of unsuccessful trips (41.9%), mainly driven by Weather and Signal Failure.
- **26.8%** of failed trips request refunds, costing **5.2% of total revenue (£38,702)**. Cancelled trips generate more refund *requests*, but only 41.9% of the refund *value* compared to Delayed trips.
- **Technical Issues (388 requests)** is the top refund driver, followed by Signal Failure, Staffing, and Traffic — together accounting for **86.6%** of total refund cost.

### 4.2 Strategic Recommendations

**A. Minimizing the effect of unsuccessful trips**

| Recommendation | Objective | Implementation |
|---|---|---|
| Reduce Signal Failure & Technical Issues | Minimize delays and operational losses | Regular signal system checks; early warning monitoring at key stations (Manchester Piccadilly, Liverpool Lime Street, London stations) |
| Address Staffing / Staff Shortage | Ensure sufficient staff, reduce cancellations and delays | Adjust shifts during peak hours; enhance HR retention and fast-track hiring; train multi-skilled staff |
| Manage Weather Impact | Mitigate weather disruptions, maintain customer experience | Integrate weather forecasts; auto-adjust schedules; send advance notifications via App/SMS |

**B. Enhancing customer satisfaction via customer segmentation**

Five customer segments were identified — **Daily Commuters, Convenience Seekers, Weekend Leisure & Social Travelers, Long-Distance Value Seekers, and Assisted/Supported Travelers** — each with tailored recommendations such as commuter season-ticket bundles, express station counters, off-peak group discounts, bundled long-trip offers, and dedicated support staff for assisted travelers. (See Section 6 for full detail.)

---

## 5. Dataset and Data Modeling

### 5.1 About the Dataset
The dataset contains detailed information about each train ticket transaction, including purchase details, journey information, and operational outcomes. It records when and how tickets were purchased, the journey schedule (departure/arrival stations and times), and the actual performance of each trip (delays, cancellations, refunds).

### 5.2 Data Dictionary

| Column Name | Description |
|---|---|
| `Transaction_ID` | Unique identifier for each transaction |
| `Date_of_Purchase` | Date when the ticket was purchased |
| `Time_of_Purchase` | Time when the ticket was purchased |
| `Purchase_Type` | Whether the ticket was purchased online or at the station |
| `Payment_Method` | Method of payment used (e.g., credit card, cash) |
| `Price` | Price of the ticket |
| `Departure_Station` | Station from which the journey begins |
| `Arrival_Destination` | Final destination station |
| `Date_of_Journey` | Date when the journey takes place |
| `Departure_Time` | Scheduled departure time |
| `Arrival_Time` | Scheduled arrival time |
| `Actual_Arrival_Time` | Actual arrival time at the destination |
| `Journey_Status` | Status of the journey (e.g., completed, cancelled) |
| `Reason_for_Delay` | Reason for any delays encountered |
| `Refund_Request` | Indicates whether a refund was requested |
| `Railcard` | Indicates if a railcard was used for the purchase |
| `Ticket_Class` | Class of the ticket (e.g., First Class, Standard) |
| `Ticket_Type` | Type of ticket (e.g., Single, Return) |

### 5.3 Derived Metrics / Definitions

| # | Metric | Formula |
|---|---|---|
| 01 | On-time Performance | Number of On-time Trips / Total Trips |
| 02 | Delay Time | Actual Arrival Time − Scheduled Arrival Time |
| 03 | Refund Request Ratio (%) | Refund Requests / Unsuccessful Trips |
| 04 | Refund Cost Ratio (%) | Refund Cost / Total Revenue |
| 05 | Travel Length | Arrival Time − Departure Time |
| 06 | Days Advanced | Date of Journey − Date of Purchase |

### 5.4 Analytical Framework

The overall approach breaks the goal of **"Improving Operational Efficiency"** into two branches:

- **Minimizing the effect of unsuccessful trips** → Reducing Delay & Cancel Cases + Optimizing Refund Cost
- **Enhancing customer satisfaction via customer segmentation** → Understanding Purchase Behavior + Understanding Travel Behavior

![Approaches / Analytical Framework](images/slide-05.png)

---

## 6. Detailed Process

Each section below pairs a short description of the analysis step with the corresponding slide from the report as visual illustration.

### 6.1 Project Overview
Business context, goals, and target KPIs for the project.

![Project Overview](images/slide-03.png)

### 6.2 Dataset Overview
Structure and fields of the ticketing dataset used for analysis.

![Dataset Overview](images/slide-04.png)

### 6.3 Terms & Definitions
Standardized formulas used throughout the analysis (on-time performance, delay time, refund ratios, travel length, booking lead time).

![Terms/Definition Overview](images/slide-06.png)

---

### 6.4 Pillar A — Minimizing the Effect of Unsuccessful Trips

**6.4.1 Unsuccessful Trip Overview** — On-time performance is ~87%; March recorded the highest number of unsuccessful trips (1,137) in the four-month period.

![Unsuccessful Trip Overview](images/slide-15.png)

**6.4.2 Delay Reasons Analysis** — Weather, Signal Failure, and Technical Issues are the top delay drivers; Staff Shortage causes the longest average delays (75 mins).

![Delay Reasons Analysis](images/slide-16.png)

**6.4.3 Journey Issues Over Time** — Morning has the highest incident volume; Afternoon/Evening share similar operational issues; Late Night incidents are weather-driven.

![Journey Issues Over Time](images/slide-17.png)

**6.4.4 Refund Cost Overview** — 26.8% of unsuccessful trips requested refunds, totaling £38,702 (5.2% of revenue); refund costs peaked in Months 1 & 3.

![Refund Cost Overview](images/slide-18.png)

**6.4.5 Refund Reason Analysis** — Technical Issues, Signal Failure, Staffing, and Traffic together account for 86.6% of total refund costs.

![Refund Reason Analysis](images/slide-19.png)

---

### 6.5 Pillar B — Enhancing Customer Satisfaction via Segmentation

**6.5.1 Purchase Behavior — by Purchase Type** — Online remains the dominant channel (58.51%), but Station purchases have grown from 32.35% to 41.83% over four months.

![Purchase Behavior by Purchase Type](images/slide-21.png)

**6.5.2 Purchase Behavior — by Purchase Type & Railcard** — The shift toward Station is driven by "No Info" railcard customers, while Disabled and Senior customers show rising preference for Online.

![Purchase Behavior by Purchase Type & Railcard](images/slide-22.png)

**6.5.3 Purchase Behavior — by Ticket Class & Ticket Type** — 90.34% of customers purchase Standard-class tickets; Online purchases stay above 55% share across all ticket classes/types.

![Purchase Behavior by Ticket Class & Ticket Type](images/slide-23.png)

**6.5.4 In-Depth Price Analysis** — Online consistently offers lower prices than Station purchases; price-sensitive customers favor Online, while premium fare customers lean toward Station.

![In-Depth Price Analysis](images/slide-24.png)

**6.5.5 Purchase Behavior — by Payment Method** — Credit Card and Contactless capture ~95% of transaction volume, but Debit Card carries the highest average ticket price (£31.47).

![Purchase Behavior by Payment Method](images/slide-25.png)

**6.5.6 Purchase Behavior — Payment Method Price Distribution** — Contactless purchases cluster below £30 (daily commutes); Debit Card shows a secondary cluster of premium purchases (£50–£150).

![Purchase Behavior Payment Method Distribution](images/slide-26.png)

**6.5.7 Purchase Behavior — Booking Lead Time** — Customers purchase tickets ~1.66 days before departure on average; low-medium fare groups book earlier, while high-fare/First Class customers book closer to departure.

![Purchase Behavior — Booking Lead Time](images/slide-27.png)

**6.5.8 Travel Behavior — by Weekday & Hour** — Short and Quick trips dominate (93.8% combined); peak travel occurs at 6–9 AM and 4–7 PM.

![Travel Behavior by Weekday and Hour](images/slide-28.png)

**6.5.9 Travel Behavior — Delay Distribution by Time of Day** — Morning commuter surges drive severe delay spikes (1,375 delayed trips); Long Trips occur exclusively in Afternoon/Evening, avoiding peak congestion.

![Travel Behavior Delay Distribution](images/slide-29.png)

**6.5.10 Travel Behavior — by Class Price Group** — Quick/Short trips anchor in the cheapest Standard tiers; Medium trips show the highest willingness to pay; Long trips prioritize cost efficiency.

![Travel Behavior by Class Price Group](images/slide-30.png)

**6.5.11 Travel Behavior — by Ticket Type** — Short & Medium trips drive ~82% of total revenue despite Quick Trips carrying the most passengers; weekend Off-Peak shift causes a ~10% dip in average ticket price.

![Travel Behavior by Ticket Type](images/slide-31.png)

---

### 6.6 Recommendations Summary

**Detailed recommendations for minimizing unsuccessful trips** (action, location, timing, and expected impact for each initiative):

![Detailed Recommendation — Minimizing Unsuccessful Trips](images/slide-33.png)

**Detailed recommendations for enhancing customer satisfaction**, mapped by customer segment (demographics, purchase behavior, travel behavior, demand, and tailored recommendation):

![Detailed Recommendation — Customer Segmentation Part 1](images/slide-34.png)

![Detailed Recommendation — Customer Segmentation Part 2](images/slide-35.png)

---

## Repository Structure

```
.
├── README.md
├── images/                # Slide images used as visual illustrations in this README
│   └── slide-XX.png
└── Final_Report.pdf       # Full presentation report
```

---

*Report presented by Đăng Khôi.*
