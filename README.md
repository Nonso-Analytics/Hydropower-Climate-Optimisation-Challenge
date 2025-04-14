# Hydropower-Climate-Optimisation-Challenge
This repo contains my solution for the IBM Hydropower Climate Optimization Challenge hosted on Zindi. The objective is to forecast the total daily energy consumption (kWh) per data user for one month into the future.

## Objective
Build a model that accurately predicts energy load generation (in kWh), drawing on MHP data like voltage, current, power factors, and energy metrics, combined with climate indicators like temperature, dew point, wind speed, and precipitation. The goal is to uncover patterns and insights that can improve forecasting, optimise energy distribution, and enhance system reliability.
<br>
Predicting energy needs means less waste, fewer blackouts, and smarter resource management—all crucial for keeping the lights on in off-grid communities. Understanding how climate affects energy demand, and what that means for sustainable power planning, is a critical insight for sustainable power projects all over the world.

## 🧠 My Approach

### 1. Data Preprocessing and Exploratory Analysis
Aggregated climate and consumer device data on a daily level using groupby and agg for statistical summaries.<br>
Energy Consumption: Grouped by source and time (daily).

### 2. Feature Engineering
A comprehensive set of engineered features were created:<br>
Temperature: 24-hour rolling ranges, frost risk indicators, dew point spread.<br>
Wind: Speed magnitude, direction (via arctangent of U/V components), chill factor, wind anomalies.<br>
Precipitation: Snow-to-precipitation ratio, storm severity index.<br>
Voltage Stability: Phase voltage range and average balance.<br>
Interaction Features: Combined climate-electricity effects such as temperature-wind interaction and dew-temp ratio.

### 3. Model Building
**Time-Series Forecasting Using SARIMAX**
To forecast future energy consumption (kWh), I employed the usage of SARIMAX (Seasonal AutoRegressive Integrated Moving Average with eXogenous variables) model—a statistical approach well-suited for time-series data that incorporates both autoregressive trends and external influencing factors (exogenous features).<br>
Here, the previously feature engineered environmental and electrical variables were passed as exogenous inputs. These include, but are not limited to:<br>
**Meteorological factors:** temperature, dew point, precipitation, snow cover, wind direction/speed. <br>
**Engineered indicators:** frost risk flags, wind chill, voltage stability, storm intensity, and power factor.<br>
**Interaction terms:** e.g., temperature-wind interaction, dew-temperature ratio.<br>

### 4. Evaluation
RMSE - Root Mean Squared Error<br>
Achieved a public Leaderboard (LB) score of 7.264284982
<br>and Private Leaderboard (LB) score of 4.711854335 with a ranking of top 10% (14/444)

