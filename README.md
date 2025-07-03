# 📊 Kenyan Monthly Inflation Forecast Dashboard (2005–2025)

Forecasting Kenyan monthly inflation rates using **Seasonal ARIMA (SARIMA)** and **Facebook Prophet** models.  
Deployed as an interactive **Streamlit dashboard** for data-driven insights.

## 🎯 **Project Overview & Goal**

This project was created to:
- Analyze and forecast monthly inflation rates in Kenya from 2005–2025.
- Apply two popular time series models:
  - SARIMA (Seasonal ARIMA)
  - Facebook Prophet
- Compare their forecasting performance.
- Present results in a clean, interactive dashboard using Streamlit & Plotly.

The final goal is to make the analysis:
- Understandable for policymakers, students, and analysts.
- Shareable as a **portfolio project** in data science and actuarial science.

## 🧪 **Why this matters**

Inflation directly affects:
- Cost of living
- Monetary policy
- Business planning & risk management

By forecasting inflation, we help decision-makers plan ahead

## 🛠 **Project Context & Data**

- Data: Monthly inflation rates for Kenya, 2005–2025.
- Data source: Compiled from World Bank and local statistical releases.
- Columns:
  - Year
  - Month
  - Annual Average Inflation
  - 12-Month Inflation (target variable)

For modeling, we transform:
- Year + Month → single datetime column
- Focus on `12-Month Inflation` as target (`inflation_rate`)


## 📈 **Dashboard Features & Components**

| Component                  | Streamlit Element             | Purpose                                                                 |
|--------------------------:|------------------------------:|------------------------------------------------------------------------:|
| Title & description      | `st.title()`, `st.markdown()` | Introduce project goal, data & audience                                 |
| Model selector           | `st.selectbox()`              | Choose ARIMA or Prophet                                                 |
| Trend chart              | `plotly`                      | Plot actual vs forecast with confidence intervals                       |
| Forecast table           | `st.dataframe()`              | Show predicted values and CI                                            |
| Model accuracy metrics   | `st.metric()`                 | Display MAE & RMSE                                                      |
| Data explorer (optional) | `st.expander()` + dataframe   | View raw data                                                           |
| Download forecast        | `st.download_button()`        | Export forecast as CSV                                                  |
| Sidebar                  | `st.sidebar().markdown()`     | Explain model assumptions, data split & methodology                     |


## 🔍 **Exploratory Data Analysis (EDA)**

Performed in the Jupyter notebook:
- Visualized inflation trends (2005–2025)
- Computed rolling mean & rolling standard deviation
- Conducted Augmented Dickey-Fuller test (ADF) for stationarity
- Observed seasonal patterns (annual cycles)

📓 See `notebooks/kenya_monthly_inflation_forecast.ipynb` for detailed EDA.



## 🧰 **Project Structure**
kenya-inflation-forecast/
├── app/
│ └── app.py # Streamlit dashboard
├── src/ # Modular Python scripts
│ ├── data_preprocessing.py
│ ├── eda.py
│ ├── modeling_arima.py
│ ├── modeling_prophet.py
│ └── evaluation.py
├── data/
│ └── kenya_monthly_inflation.csv # Monthly inflation data (2005–2025)
├── notebooks/
│ └── kenya_monthly_inflation_forecast.ipynb
├── requirements.txt
├── .gitignore
└── README.md

## 📊 **Models & Methodology**

| Step                        | Details                                                                  |
|---------------------------:|--------------------------------------------------------------------------:|
| Models used               | SARIMA (Seasonal ARIMA), Facebook Prophet                                |
| Train period              | 2005–2023                                                                 |
| Test period               | 2024–2025                                                                 |
| Forecast horizon          | 24 months (monthly)                                                        |
| Seasonal cycle           | 12 months                                                                  |
| Target variable           | `12-Month Inflation` column                                               |
| Evaluation metrics       | Mean Absolute Error (MAE), Root Mean Squared Error (RMSE)                   |


## 📐 **Model Assumptions & Choices**

**Why Prophet?**
- Handles multiple seasonality
- Robust to missing data & holidays

**Why SARIMA?**
- Classical statistical approach
- Well-suited for seasonal economic data

**Assumptions:**
- Inflation follows roughly annual seasonality
- No external regressors (e.g., oil price, FX) in baseline
- Data quality is reliable for forecasting
"# Financial-Time-Series-Analysis" 
"# Financial-Time-Series-Analysis" 
