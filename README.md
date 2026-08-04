# UK Train Reporting — Improving Operational Efficiency

> Analysis of UK train ticketing and journey data to identify the root causes of delays/cancellations, optimize refund costs, and improve customer satisfaction through customer segmentation.

---

## 1. Business Problem

The company has observed an increasing trend of train delays and cancellations, which has led to higher refund costs and lower customer satisfaction. Root-cause analysis is needed to understand *why* trips fail, how customers behave when purchasing tickets and traveling, and how operations can be optimized to reduce financial losses and improve the overall customer experience.

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
| Data cleaning & transformation | [Python](./code/PreProcessing.ipynb) |
| Data analysis | [Python](./code/Analyst.ipynb) |
| DAX calculations | Power BI / Excel Power Pivot) |
| Dashboard & visualization | Power BI |
| Reporting & presentation | Canva |

---

## 4. Key Results & Recommendations

### 4.1 Operational Insights
![Minimizing the effect of unsuccessful trips](images/7.png)
![Minimizing the effect of unsuccessful trips](images/8.png)

### 4.2 Customer Behaviors Insights

![Customer Behaviors Insights](images/9.png)
![Customer Behaviors Insights](images/10.png)

### 4.2 Strategic Recommendations

**A. Minimizing the effect of unsuccessful trips**

![Minimizing the effect of unsuccessful trips](images/11.png)

**B. Enhancing customer satisfaction via customer segmentation**

Five customer segments were identified — **Daily Commuters, Convenience Seekers, Weekend Leisure & Social Travelers, Long-Distance Value Seekers, and Assisted/Supported Travelers** — each with tailored recommendations such as commuter season-ticket bundles, express station counters, off-peak group discounts, bundled long-trip offers, and dedicated support staff for assisted travelers.
![Minimizing the effect of unsuccessful trips](images/12.png)
![Minimizing the effect of unsuccessful trips](images/13.png)

---

## 5. Dataset

### 5.1 About the Dataset
![About the Dataset](images/4.png)

### 5.3 Key Metrics / Definitions

![Key Metrics / Definition](images/6.png)

### 5.4 Analytical Framework

The overall approach breaks the goal of **"Improving Operational Efficiency"** into two branches:

- **Minimizing the effect of unsuccessful trips** → Reducing Delay & Cancel Cases + Optimizing Refund Cost
- **Enhancing customer satisfaction via customer segmentation** → Understanding Purchase Behavior + Understanding Travel Behavior

![Approaches / Analytical Framework](images/5.png)

---

## 6. Detailed Analysis

Each section below pairs a short description of the analysis step with the corresponding slide from the report as visual illustration.

### 6.1 A — Minimizing the Effect of Unsuccessful Trips

**6.1.1 Unsuccessful Trip Overview** — On-time performance is ~87%; March recorded the highest number of unsuccessful trips (1,137) in the four-month period.

![Unsuccessful Trip Overview](images/15.png)

**6.1.2 Delay Reasons Analysis** — Weather, Signal Failure, and Technical Issues are the top delay drivers; Staff Shortage causes the longest average delays (75 mins).

![Delay Reasons Analysis](images/16.png)

**6.1.3 Journey Issues Over Time** — Morning has the highest incident volume; Afternoon/Evening share similar operational issues; Late Night incidents are weather-driven.

![Journey Issues Over Time](images/17.png)

**6.1.4 Refund Cost Overview** — 26.8% of unsuccessful trips requested refunds, totaling £38,702 (5.2% of revenue); refund costs peaked in Months 1 & 3.

![Refund Cost Overview](images/18.png)

**6.1.5 Refund Reason Analysis** — Technical Issues, Signal Failure, Staffing, and Traffic together account for 86.6% of total refund costs.

![Refund Reason Analysis](images/19.png)

---

### 6.2 Pillar B — Enhancing Customer Satisfaction via Segmentation

**6.2.1 Purchase Behavior — by Purchase Type** — Online remains the dominant channel (58.51%), but Station purchases have grown from 32.35% to 41.83% over four months.

![Purchase Behavior by Purchase Type](images/21.png)

**6.2.2 Purchase Behavior — by Purchase Type & Railcard** — The shift toward Station is driven by "No Info" railcard customers, while Disabled and Senior customers show rising preference for Online.

![Purchase Behavior by Purchase Type & Railcard](images/22.png)

**6.2.3 Purchase Behavior — by Ticket Class & Ticket Type** — 90.34% of customers purchase Standard-class tickets; Online purchases stay above 55% share across all ticket classes/types.

![Purchase Behavior by Ticket Class & Ticket Type](images/23.png)

**6.2.4 In-Depth Price Analysis** — Online consistently offers lower prices than Station purchases; price-sensitive customers favor Online, while premium fare customers lean toward Station.

![In-Depth Price Analysis](images/24.png)

**6.2.5 Purchase Behavior — by Payment Method** — Credit Card and Contactless capture ~95% of transaction volume, but Debit Card carries the highest average ticket price (£31.47).

![Purchase Behavior by Payment Method](images/25.png)

**6.2.6 Purchase Behavior — Payment Method Price Distribution** — Contactless purchases cluster below £30 (daily commutes); Debit Card shows a secondary cluster of premium purchases (£50–£150).

![Purchase Behavior Payment Method Distribution](images/26.png)

**6.2.7 Purchase Behavior — Booking Lead Time** — Customers purchase tickets ~1.66 days before departure on average; low-medium fare groups book earlier, while high-fare/First Class customers book closer to departure.

![Purchase Behavior — Booking Lead Time](images/27.png)

**6.2.8 Travel Behavior — by Weekday & Hour** — Short and Quick trips dominate (93.8% combined); peak travel occurs at 6–9 AM and 4–7 PM.

![Travel Behavior by Weekday and Hour](images/28.png)

**6.2.9 Travel Behavior — Delay Distribution by Time of Day** — Morning commuter surges drive severe delay spikes (1,375 delayed trips); Long Trips occur exclusively in Afternoon/Evening, avoiding peak congestion.

![Travel Behavior Delay Distribution](images/29.png)

**6.2.10 Travel Behavior — by Class Price Group** — Quick/Short trips anchor in the cheapest Standard tiers; Medium trips show the highest willingness to pay; Long trips prioritize cost efficiency.

![Travel Behavior by Class Price Group](images/30.png)

**6.2.11 Travel Behavior — by Ticket Type** — Short & Medium trips drive ~82% of total revenue despite Quick Trips carrying the most passengers; weekend Off-Peak shift causes a ~10% dip in average ticket price.

![Travel Behavior by Ticket Type](images/31.png)

---

### 6.6 Recommendations Summary

**Detailed recommendations for minimizing unsuccessful trips** (action, location, timing, and expected impact for each initiative):

![Detailed Recommendation — Minimizing Unsuccessful Trips](images/33.png)

**Detailed recommendations for enhancing customer satisfaction**, mapped by customer segment (demographics, purchase behavior, travel behavior, demand, and tailored recommendation):

![Detailed Recommendation — Customer Segmentation Part 1](images/34.png)

![Detailed Recommendation — Customer Segmentation Part 2](images/35.png)

---

---
## 🚀 Dashboard 
![Overview Dashboard](images/Operation.png)
![Finance Dashboard](images/Finance.png)
![Customer Dashboard](images/Customer.png)
---

## 📁 Project Structure

```
├── data
├── code
|   ├──PreProcessing.ipynb
|   ├── Analyst.ipynb
├── Final Report.pdf
└── README.md
```


*Report presented by Đăng Khôi.*
