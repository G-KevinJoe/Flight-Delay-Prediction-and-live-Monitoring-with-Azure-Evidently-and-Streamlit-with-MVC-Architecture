# 🛫 Hypersense Flight AI Predictor

This project is a **Flight Delay Prediction and Monitoring application** built with **Streamlit**, following the **MVC (Model-View-Controller) architecture**.  
It predicts flight delays using an **XGBoost model** and integrates **Evidently AI** to monitor **data drift, target drift, model performance, and data quality**.

---

## 📊 Project Rating
After reviewing the project’s architecture, ML design, code quality, and usability:

**⭐ Overall Rating: 7.5 / 10**  

- **Architecture (MVC separation): 8/10**  
- **Machine Learning Design: 6/10**  
- **Code Quality: 7/10**  
- **User Experience (Streamlit UI): 7/10**  
- **Innovation & Practical Use: 8/10**  

👉 With improvements (dynamic pipeline handling, error handling, caching, scalable feature engineering), this can easily reach **9/10**.

---

## ✨ Features
- **Flight Delay Prediction** using a pre-trained XGBoost model.
- **MVC Architecture** for clean separation of logic:
  - Model → Handles ML training, prediction, monitoring reports.  
  - View → Streamlit UI for inputs, outputs, and reports.  
  - Controller → Orchestrates interaction between Model & View.  
- **Evidently AI Reports** for:
  - Regression Performance  
  - Target Drift  
  - Data Drift  
  - Data Quality  
- **Retraining Capability** on new data batches.  
- **Interactive Streamlit Interface** with sidebar for inputs.  

---

## 🛠️ Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/hypersense-flight-ai-predictor.git
cd hypersense-flight-ai-predictor
```

### 2. Create a virtual environment (recommended)
Using Conda:
```bash
conda create -n flightdelay python=3.10 -y
conda activate flightdelay
```

Or with `venv`:
```bash
python -m venv venv
source venv/bin/activate  # (Linux/Mac)
venv\Scripts\activate   # (Windows)
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Project Structure
```
├── app.py                       # Streamlit entry point
├── src/
│   ├── controller/
│   │   └── flight_delay_controller.py
│   ├── model/
│   │   └── flight_delay_model.py
│   └── view/
│       └── flight_delay_view.py
├── models/
│   └── best_model.pkl           # Pre-trained XGBoost model
├── data/
│   └── Monitoring_data.csv      # Monitoring dataset
├── requirements.txt
```

### 5. Run the app
```bash
streamlit run app.py
```

---

## 🔗 Usage

### 🔹 Prediction Mode
1. Select **Make Predictions** from the sidebar.  
2. Enter flight details (date, carrier, origin, destination, delays, etc.).  
3. Click **Predict Flight Delay** → get predicted delay (minutes).  

### 🔹 Monitoring Mode
1. Select **Monitor Data and Model** from the sidebar.  
2. Choose a **date range** for monitoring data.  
3. Select reports to generate: Performance, Drift, or Data Quality.  
4. Click **Submit** → Evidently reports are generated and displayed.  

---

## ⚠️ Notes & Limitations
- **Hardcoded feature list** → prediction may break if columns change.  
- **Model retraining** currently uses only numerical features (categoricals ignored).  
- **Data Quality report** may take up to **10 minutes** to compute in Streamlit.  
- Works best with prepared data (`Monitoring_data.csv`) and a valid model file (`best_model.pkl`).  

---

## 🚀 Future Improvements (Roadmap to 9/10)
- Save and load full **preprocessing pipeline** instead of hardcoded features.  
- Add error handling for missing/empty datasets.  
- Use **Streamlit expanders** for long reports.  
- Cache expensive operations (`st.cache_data`) to improve responsiveness.  
- Improve retraining pipeline to handle **categorical features** properly.  

---

## 📜 License
MIT License – free to use and modify with attribution.
