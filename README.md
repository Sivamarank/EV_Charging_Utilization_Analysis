# ⚡ EV Charging Station Utilization & Forecasting Project

**Author:** Maran  
**Date:** July 05, 2025  
**Tools Used:** Python (Pandas, Matplotlib), Power BI  
**Dataset:** Simulated EV Charging Data (1000+ records)  
**Goal:** Analyze and visualize Electric Vehicle (EV) charging patterns and forecast utilization trends

---

## 🗂️ Project Structure

```
📁 ev-charging-analysis/
├── data/
│   └── ev_charging_data.csv
├── notebooks/
│   └── eda_analysis.ipynb
├── powerbi/
│   └── EV_Charging_Dashboard.pbix
├── images/
│   └── preview_dashboard.png
├── README.md
```

---

## 📌 Objective

- Understand how EV charging stations are utilized across time, location, and connector/vehicle types.
- Analyze total energy dispensed, session durations, and usage patterns.
- Create an interactive dashboard using Power BI.
- Prepare for future forecasting using Python (optional extension).

---

## 🧪 Python: Exploratory Data Analysis (EDA)

Performed EDA using **Pandas** and **Matplotlib**.

### Key Steps:

- Data cleaning: Removed nulls, converted timestamp
- Feature engineering: Extracted hour, weekday, session duration
- Aggregations:
  - Energy usage by day and station
  - Peak hours of usage
  - Average session durations
  - Revenue estimates

### Sample Python Code:

```python
import pandas as pd
df = pd.read_csv("ev_charging_data.csv")

# Convert timestamp
df['Timestamp'] = pd.to_datetime(df['Timestamp'])

# Add hour and weekday
df['Hour'] = df['Timestamp'].dt.hour
df['DayOfWeek'] = df['Timestamp'].dt.day_name()

# Calculate duration in minutes
df['Session_Duration'] = (df['End_Time'] - df['Start_Time']).dt.total_seconds() / 60
```

---

## 📊 Power BI Dashboard
![image alt](https://github.com/Sivamarank/EV_Charging_Utilization_Analysis/blob/b67b0e3fa1852d9d3188f3b28c0ccf69f47a3998/Screenshot%202025-07-05%20200304.png
)



### ✅ Features:

- KPI Cards: Total Sessions, Total Energy (kWh), Avg Duration, Revenue
- Visuals:
  - Sessions by Hour
  - Energy by Day of Week
  - Connector Type Usage (Donut)
  - Vehicle Type vs Energy (Bar)
- Slicers:
  - Location
  - Date Range
  - Connector Type
  - Vehicle Type

### 🎨 Design:
- Background: EV charging station at night
- Text: White & Aqua
- Colors:
  - CCS: `#00CFFF`
  - CHAdeMO: `#FFA500`
  - Type 1: `#00FF88`
  - Type 2: `#FFD700`

---

## 🧠 Insights

- Peak charging hours are between 10 AM – 2 PM
- Sundays and Fridays have the highest energy usage
- CCS and CHAdeMO are the most used connector types
- Trucks and 3W consume more energy than 2W or 4W

---

## 🔮 Next Steps (Forecasting)

- Use **Prophet** or **ARIMA** to predict future station demand
- Use Python to forecast energy demand or session growth over months

---

## 🗂 Files to Include in GitHub

| File                                 | Description                           |
|--------------------------------------|---------------------------------------|
| `ev_charging_data.csv`              | Raw dataset                           |
| `eda_analysis.ipynb`                | Python notebook with EDA              |
| `EV_Charging_Dashboard.pbix`        | Interactive dashboard (Power BI)      |
| `preview_dashboard.png`             | Screenshot of dashboard               |
| `README.md`                         | This full project summary             |

---

## 🧭 How to Run

1. Open Jupyter or VS Code → Run `eda_analysis.ipynb`
2. Explore charts and aggregates in Python
3. Open `EV_Charging_Dashboard.pbix` in Power BI
4. Interact with filters and visuals

---

## ✅ Conclusion

This project combines Python and Power BI to deliver deep insights into EV station usage. It's a great foundation for smart grid planning, city infrastructure, and energy optimization.

