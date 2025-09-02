# GTC ML Project 1 - Hotel Booking Data Cleaning & Preprocessing

## 📌 Project Overview
This project analyzes the Hotel Bookings Dataset to perform data cleaning, exploratory data analysis (EDA), feature engineering, and preparation for machine learning tasks.  
The goal is to preprocess the dataset into a clean and structured format suitable for modeling.

---

## 📂 Phases

### Phase 1: Load Data
- Uploaded the dataset (`hotel_bookings.csv`) into Google Colab.  
- Loaded it into a Pandas DataFrame for analysis.  

---

### Phase 2: Exploratory Data Analysis (EDA)
- Checked dataset dimensions, column types, and summary statistics:
  - shape, info(), describe(), head()
- Visualizations:
  - Missing values (Missingno)  
  - Distribution of adr  
  - Correlation heatmap (numeric columns)  

---

### Phase 3: Handle Missing Values
- agent & company → filled with 0  
- country → filled with mode  
- children → filled with median  
- customer_type → filled with mode  
- adr → filled with median  
- required_car_parking_spaces & total_of_special_requests → filled with 0  

---

### Phase 4: Outlier Handling
- Detected outliers in adr using boxplot.  
- Capped values greater than 1000 (`adr > 1000` → set to 1000).  

---

### Phase 5: Remove Duplicates
- Dropped duplicate rows from the dataset.  

---

### Phase 6: Fix Data Types
- Converted reservation_status_date into datetime type.  

---

### Phase 7: Feature Engineering
Created new features to enrich the dataset:
- total_guests = adults + children + babies  
- total_nights = stays_in_weekend_nights + stays_in_week_nights  
- is_family = 1 if (`children > 0` or babies > 0`), else `0  

---

### Phase 8: Encoding
- One-Hot Encoding for categorical columns with few unique values:  
  - meal, market_segment, distribution_channel  
- Frequency Encoding for country (many unique categories).  

---

### Phase 9: Drop Leakage Columns
- Removed reservation_status and reservation_status_date to avoid data leakage.  

---

### Phase 10: Train/Test Split
- Split dataset into:
  - Train Set: 80%  
  - Test Set: 20%  

---


## ✅ Final Note
The dataset is now:
- Cleaned  
- Preprocessed  
- Ready for Machine Learning 🚀  

---
