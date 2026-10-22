## 📌 Project Overview

This project is a data-driven analysis of maintenance and failure data for container-terminal equipment: **RTG** (Rubber Tyred Gantry), **STS** (Ship-to-Shore crane), **TT** (Terminal Tractor), **RS** (Reach Stacker) and **SP** (Spreader). The data covers work orders from **January to October 2026** (weeks 01–42).

The goal is to help reliability and maintenance teams:

- Reduce unplanned downtime and the share of **Emergency Repair (ER)** work.
- Identify the failure modes and individual assets that drive the most losses.
- Track the **maintenance backlog** (finished vs. open actions).
- Quantify the impact of corrective actions through **FMEA**, comparing Severity (S), Occurrence (O), Detectability (D) and **Risk Priority Number (RPN)** before and after improvement.

---

## 🖼️ Dashboard Preview

### Operations Overview
https://raw.githubusercontent.com/loayayman/FMEA/refs/heads/main/Images/ec909af9-ba4f-4708-8024-c914514f821c.png

### FMEA & Risk Analysis
https://raw.githubusercontent.com/loayayman/FMEA/refs/heads/main/Images/c352bbfa-5be3-4ad4-a798-18e3327283d7.png

<details>
<summary><b>More screenshots (filters, tooltips, drill-through)</b></summary>

#### Slicer Filter Panel
https://raw.githubusercontent.com/loayayman/FMEA/refs/heads/main/Images/66385dfb-d844-40b6-9a8f-a12c5ea5c755.png

#### Filtered FMEA View (Failure Mode selected, Drill Through enabled)
https://raw.githubusercontent.com/loayayman/FMEA/refs/heads/main/Images/27ce1a5c-7401-446f-a491-86d77730ab29.png

#### Tooltip: Downtime Trend – Week 32
https://raw.githubusercontent.com/loayayman/FMEA/refs/heads/main/Images/2de0e8ba-60a5-43d4-87f5-96f10bd1efa6.png

#### Tooltip: ER Work Orders (all equipment)
https://raw.githubusercontent.com/loayayman/FMEA/refs/heads/main/Images/86caa7bd-d2c2-4389-9e6d-d70696837fd0.png

#### Tooltip: RTG ER Work Orders
https://raw.githubusercontent.com/loayayman/FMEA/refs/heads/main/Images/94abd61f-58a9-477b-bf44-2703dadd97c4.png

#### Drill-Through: Work Order Detail Log
https://raw.githubusercontent.com/loayayman/FMEA/refs/heads/main/Images/71a0a484-498d-4983-b301-b2b74795e2a9.png

</details>

---

## 📊 Dashboard Structure

The report contains two main pages plus a drill-through detail page.

### 1. Operations Overview

- **High-level KPIs:** Total Downtime (**97.68 hrs**), Total Failures (**463**), Total ER Failures (**248**), MTTR (**0.22 hrs**, about 13 minutes) and High Risk Failures (**6**).
- **Downtime Trend:** Weekly work-order volume (bars) against downtime hours (line), June to October.
- **Failures & Downtime by Equipment Class:** ER vs. OP split for each asset class.
- **MTTR by Equipment Class:** Repair speed per class (STS 0.22, RTG 0.21, TT 0.30, RS 0.32).
- **ER Percentage:** 54% Emergency Repair vs. 46% Operational (OP).
- **Action Status:** 279 Finished vs. 184 Open actions, plus a breakdown by equipment class.

| Equipment Class | Failures (ER / OP) | Downtime hrs (ER / OP) | Finished / Open |
|:---|:---:|:---:|:---:|
| RTG | 163 / 188 | 34.7 / 37.6 | 195 / 156 |
| STS | 71 / 25 | 15.7 / 5.0 | 68 / 28 |
| TT | 9 / 0 | 2.7 / 0.0 | 9 / 0 |
| RS | 4 / 2 | 1.3 / 0.8 | 6 / 0 |
| SP | 1 / 0 | 0.0 / 0.0 | 1 / 0 |

### 2. FMEA & Risk Analysis

- **Improvement KPIs:** RPN improvement (**17.8%**), Occurrence improvement (**7.8%**) and Detectability improvement (**13.0%**).
- **FMEA Factors (before vs. after):** Average Severity, Occurrence and Detectability per equipment class, shown in a baseline chart and a "NEW" post-action chart.
- **RPN vs. New RPN:** Side-by-side comparison with the percentage improvement per class.
- **Failure Mode Pareto:** Cumulative analysis of the vital few failure modes.
- **Downtime Distribution:** Histogram showing that most repairs are short (under about 0.3 hrs), with a long tail of larger events.

| Equipment Class | Initial RPN | New RPN | Improvement |
|:---|:---:|:---:|:---:|
| STS | 86.9 | 69.6 | 20% |
| RTG | 79.1 | 65.6 | 17% |
| RS | 49.7 | 39.2 | 21% |
| TT | 27.1 | 21.9 | 19% |
| SP | 25.0 | 25.0 | 0% |

### 3. Work Order Detail Log (Drill-Through)

A detailed log reached through drill-through, listing **Equipment ID, Year, Month, Day, WO Type, Downtime (hr.), Description and Failure Effect** for the selected context, with a running downtime total.

---

## 🎛️ Interactive Features

| Feature | Description |
|:---|:---|
| **Slicer Filter Panel** | Slide-out panel (funnel icon) to filter by **Equipment Class**, **Date**, **WO Type** (ER / OP) and **Status** (Finished / Open). |
| **Report-Page Tooltips** | Hovering a visual shows a detailed mini-report: <br>• *Downtime Trend – Week N*: work orders and downtime by equipment unit for that week<br>• *ER Work Orders*: ER count and downtime per asset<br>• *RTG ER Work Orders*: the same view focused on RTGs |
| **Cross-Filtering** | Selecting a bar (e.g., a failure mode in the Pareto) filters every other FMEA visual and KPI. |
| **Drill-Through** | The **Drill Through** button opens the Work Order Detail Log for the current selection, showing the raw failure descriptions and effects. |

---

## 💡 Key Business Insights

- **Heavy reliance on emergency repairs:** ER work orders are **54%** of all failures (248 events, **54.36 hrs** of downtime). Moving part of this to planned or predictive maintenance is the largest improvement opportunity.
- **RTGs dominate the workload:** RTGs account for **351 of 463** failures (76%) and **72.3 of 97.68** downtime hours. They also hold the biggest backlog, with **156 open** work orders.
- **Worst individual assets (ER):** **STS01** leads with **19 WOs / 5.1 hrs**, followed by **RTG01** (14 WOs / 2.7 hrs) and **STS06** (13 WOs / 2.6 hrs).
- **Peak week:** **Week 32 (August)** recorded **45 work orders** and **7.81 hrs** of downtime, with RTG27 and RTG01 the main contributors.
- **Pareto concentration:** **Gantry, Control and Other** failure modes account for about **70%** of failures; adding **Hoist** brings it to about **88%**.
- **Recurring fault patterns:** The recent work-order log shows repeated *"no side-shift"* and *"skew not center"* faults on RTGs, and *"no boom down"*, *"no unlock"* and *"no control-on"* faults on STS units. Each is recorded with the same effect: loss of command response, an unsafe operating condition and immediate downtime.
- **FMEA actions are working:** Overall RPN fell by **17.8%**. Reach Stackers improved most (**21%**), then STS (**20%**), TT (**19%**) and RTG (**17%**). Most of the gain comes from better **Detectability** (13.0%) rather than lower **Occurrence** (7.8%), so there is more room to eliminate root causes.
- **Short repairs, high frequency:** MTTR is only about 13 minutes, so the downtime problem is the **frequency** of failures rather than repair duration.

---

## 🛠️ Technical Stack

- **Tool:** Power BI Desktop
- **Data Modeling:** Star-schema model (fact table of work orders with equipment, date, WO-type and status dimensions).
- **DAX (Data Analysis Expressions):** Measures for Total Downtime, Total Failures, ER Failures, ER %, MTTR, Finished/Open counts, RPN (S × O × D), New RPN, % Improvement for RPN / Occurrence / Detectability, and Pareto cumulative %.
- **Power Query:** ETL to clean work-order logs, standardize failure descriptions and compute downtime durations.
- **UX Customization:** Custom report-page tooltips, slide-out slicer panel, drill-through page and conditional formatting on improvement values.

---

## 📁 Repository Structure

```
.
├── FMEA.pbix   # Power BI report
└── Data/ 
    └── FMEA Visualization Last update..xlsm    # Source data
├── README.md
└── images/                           # Dashboard screenshots
    ├── 01_operations_overview.png
    ├── 02_slicer_panel.png
    ├── 03_fmea_risk_analysis.png
    ├── 04_fmea_pareto_filtered.png
    ├── 05_tooltip_downtime_week32.png
    ├── 06_tooltip_er_work_orders.png
    ├── 07_work_order_log.png
    └── 08_tooltip_rtg_er.png
```

---

## 🚀 How to Use

1. **Download:** Clone this repository and open `Equipment_Reliability_FMEA.pbix` in Power BI Desktop.
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   ```
2. **Filter:** Click the **funnel icon** (top right) to open the slicer panel and filter by Equipment Class, Date, WO Type or Status.
3. **Hover:** Move over the Downtime Trend or equipment-class charts to open the detailed tooltips.
4. **Cross-filter:** Click a failure mode in the Pareto chart to filter the FMEA page.
5. **Drill through:** With a selection active, click **Drill Through** to open the Work Order Detail Log. Use the back arrow to return.

---

## 👤 Author

**Loay Ayman**

- LinkedIn: [linkedin.com/in/loayayman](https://linkedin.com/in/loayayman)
- Portfolio: [loayayman.vercel.app](https://loayayman.vercel.app/)
