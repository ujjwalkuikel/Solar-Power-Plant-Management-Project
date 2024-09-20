# Solar-Power-Plant-Management-Project

## Overview

This project aims to identify faulty inverters in a solar power system by analyzing various operational metrics. By diving deep into the daily yield, irradiation, DC and AC power, and specific fault events, we aim to detect anomalies that indicate inverter malfunction and understand their impact on overall system performance.

## Objectives

1. **Efficiency Tracking**: Analyze the overall efficiency (ETA) of the solar power system.
2. **Fault Detection**: Identify faulty inverters based on daily yield, irradiation, and power trends.
3. **Impact of Faults**: Measure the effect of inverter faults on the system's performance.

## Data and Visualizations

### 1. Daily Yield vs. Date-Time
This graph illustrates the daily power output of the system over time. It helps track the efficiency of the system on a day-to-day basis and spot any significant dips in power generation, potentially signaling inverter faults.

![alt text](<images/Daily yield date time.png>)
![alt text](<images/Daily Yield vs Date Time.png>)

### 2. Irradiation vs. Time of Day
The irradiation graph shows the amount of solar energy received at different times of the day. This is crucial for understanding how much energy the system should be generating, helping us isolate power losses that might be due to inverter faults rather than low irradiation.

![alt text](<images/irradiation vs time of day.png>)

### 3. DC and AC Power vs. Time of Day
This graph compares DC and AC power throughout the day. As we can see below PLANT_1 it's able to convert about only 9-10 % of DC POWER produced. It helps identify any discrepancies between input (DC) and output (AC) power that might indicate inverter inefficiencies or malfunctions.

![alt text](<images/PLANT1_DATA - Graph Builder.png>)

### 4. Fault Analysis 
We can clearly observe that inverters 1BY6WEcLGh8j5v7 and bvBOhCH3iADSZry are underperforming relative to the other inverters. These units may need maintenance or could require replacement. However, before delving deeper into the specifics of these underperforming inverters, let's first examine the common issues affecting the entire plant by reviewing the DC power generation during daylight hours over the past 34 days.

![alt text](<images/faulty inverter.png>)

## June 7 (Inverter Fault)
On June 7, an inverter fault was detected. The dc power produced by the inverter goes quickly to 0 exactly during maximum sunlight hours, between 11 am and 16 pm. This can only be due to a fault in the inverter, so maybe these inverters requires to be fixed or replaced. The graph below highlights the anomaly in system performance, showing a significant deviation from expected output. 

![alt text](<images/june 7 inverter fault.png>)

## June 14 (Inverter Fault)
Similarly, on June 14, another inverter fault was identified. The dc power produced by the inverter goes quickly to 0 exactly during maximum sunlight hours, between 11 am and 16 pm. This can only be due to a fault in the inverter, so maybe these inverters requires to be fixed or replaced. This graph outlines the fault event, allowing us to compare with the fault on June 7 to determine if the same inverter is responsible.

![alt text](<images/june 14 inverter fault.png>)


## Methodology

1. **Efficiency (ETA) Calculation**: 
   - The overall efficiency was calculated by comparing the daily yield to the expected power based on irradiation data. This helped establish a baseline for the system’s performance.
   
2. **Spline Smoothing for Fault Detection**: 
   - We applied a spline smoothing technique to the power vs. time data to clearly observe the trends and detect outliers indicating inverter faults.

3. **Fault Event Analysis**:
   - The two main inverter fault events (June 7 and June 14) were analyzed by comparing the yield and power output before, during, and after the events. This comparison helped isolate the faulty inverter's behavior and quantify its impact.

## Conclusion

By analyzing the data, we successfully identified inverter faults on specific dates (June 7 and June 14). The discrepancies between DC and AC power and the dips in daily yield allowed us to isolate faulty inverters and assess their impact on the overall efficiency of the solar power system.

---

### Future Work

- **Automated Fault Detection**: Implement machine learning algorithms to automatically detect anomalies in real-time.
- **Deeper Analysis**: Conduct a more granular analysis of fault patterns over extended periods to predict future failures.
