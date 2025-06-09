# Forecasting-TimeSeries

## Deskripsi Proyek (Indonesia Ver.)
Proyek ini merupakan portofolio pribadi yang berfokus pada **time series forecasting** untuk data impor produk. Menggunakan pendekatan statistik dan machine learning, kami melakukan kajian komparatif terhadap tiga metode utama:
1. **ARIMAX (AutoRegressive Integrated Moving Average with eXogenous variables)**  
2. **SARIMAX (Seasonal ARIMAX)**  
3. **LSTM (Long Short-Term Memory Neural Network)**  

Setiap metode dievaluasi dalam berbagai skenario simulasi kondisi dengan menggunakan variabel eksogen (peubah luar) seperti fluktuasi nilai tukar, harga komoditas, dan indikator ekonomi makro.

## Struktur Repository
- `notebooks/`  
  Jupyter Notebook analisis eksploratori, pemodelan, dan visualisasi hasil forecasting.  
- `src/`  
  Kode Python modular untuk implementasi ARIMAX, SARIMAX, dan LSTM, serta utilitas evaluasi (MSE, MAE, RMSE).  
- `reports/`  
  Laporan singkat dan grafik perbandingan kinerja model di berbagai kondisi simulasi.  
- `requirements.txt`  
  Daftar pustaka Python yang diperlukan (pandas, statsmodels, keras, matplotlib, dll).

## Metodologi
1. **Pengumpulan Data**  
   - Data impor produk diambil dari sumber resmi (bea cukai, TradeMap dan BPS).  
   - Variabel eksogen dikumpulkan dari Bank Indonesia (nilai tukar), Bloomberg (harga komoditas), Efek Kalender, dan World Bank (indikator makro).  

2. **Pra-Pemrosesan**  
   - Pemeriksaan nilai null dan outlier.  
   - Transformasi stasioneritas (differencing, log-transform).  
   - Scaling untuk LSTM (Min–Max Scaling).

3. **Implementasi Model**  
   - **ARIMAX**: Penentuan urutan (p, d, q) melalui ACF/PACF dan kriteria AIC.  
   - **SARIMAX**: Penentuan komponen musiman (P, D, Q, s) dengan grid search musiman.  
   - **LSTM**: Desain arsitektur jaringan (unit tersembunyi, dropout), pelatihan dengan Adam optimizer.

4. **Simulasi Kondisi**  
   - Menjalankan simulasi dengan skenario peningkatan volatilitas nilai tukar.  
   - Uji sensitivitas terhadap lonjakan harga komoditas.  
   - Integrasi skenario makro-ekonomi ekstrem (resesi, pemulihan).

5. **Evaluasi & Perbandingan**  
   - Mengukur performa tiap model menggunakan MAPE dan RMSE.  
   - Analisis residual dan grafik prediksi vs realisasi.  
   - Rangkuman kondisi optimal untuk setiap metode.

## Project Description  (English Ver.)
This personal portfolio project is dedicated to **time series forecasting** of product import data. Employing both statistical and machine learning methodologies, a comparative study is conducted on three principal approaches:  
1. **ARIMAX (AutoRegressive Integrated Moving Average with eXogenous variables)**  
2. **SARIMAX (Seasonal ARIMAX)**  
3. **LSTM (Long Short-Term Memory Neural Network)**  

Each approach is rigorously evaluated under a variety of simulated scenarios utilizing exogenous covariates—such as exchange rate fluctuations, commodity price dynamics, and macroeconomic indicators—to assess model robustness and forecasting accuracy.

## Repository Structure 
- `notebooks/`  
  Contains Jupyter Notebooks for exploratory data analysis, model implementation, and visualization of forecasting outcomes.  
- `src/`  
  Provides modular Python scripts for the development of ARIMAX, SARIMAX, and LSTM models, as well as utility functions for computing evaluation metrics (MAPE, RMSE).  
- `reports/`  
  Includes concise reports and comparative charts illustrating model performance across different simulation scenarios.  
- `requirements.txt`  
  Lists all necessary Python libraries (e.g., pandas, statsmodels, TensorFlow/Keras, matplotlib).

## Methodology  
1. **Data Acquisition**  
   - Product import volumes are sourced from official databases (Customs Authority, TradeMap, and the National Statistics Agency).  
   - Exogenous variables are retrieved from Bank Indonesia (exchange rates), Bloomberg (commodity prices), calendar effect datasets, and the World Bank (macroeconomic indicators).  

2. **Preprocessing**  
   - Missing values and outliers are identified.  
   - Stationarity is enforced via differencing and logarithmic transformation.  
   - Numerical scaling (Min–Max normalization) is applied for LSTM inputs.  

3. **Model Implementation**  
   - **ARIMAX**: Order parameters (p, d, q) are selected based on ACF/PACF diagnostics and AIC minimization.  
   - **SARIMAX**: Seasonal order (P, D, Q, s) is determined through seasonal grid search optimization.  
   - **LSTM**: Network architecture is designed with configurable hidden units and dropout layers; training employs the Adam optimizer and early stopping criteria.  

4. **Scenario Simulation**  
   - Simulations incorporate elevated exchange rate volatility.  
   - Sensitivity analyses are performed to evaluate the impact of abrupt commodity price spikes.  
   - Extreme macroeconomic scenarios (e.g., recessionary and recovery phases) are integrated to test model resilience.  

5. **Evaluation & Comparison**  
   - Forecast accuracy is quantified using MAPE and RMSE metrics.  
   - Residual diagnostics and prediction-to-observation plots are analyzed.  
   - Optimal conditions for each modeling approach are summarized based on performance across simulated environments.  
