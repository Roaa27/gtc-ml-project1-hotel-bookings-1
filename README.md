# GTC ML Project 1 - Hotel Booking Data Cleaning & Preprocessing

## 🎯 Objective
Build a robust data preprocessing pipeline for a hotel booking cancellation prediction model.  
The main goal is not to train a final model, but to prepare clean, ML-ready data.

---

## 🏨 Business Problem
The revenue team found that last-minute cancellations have a big impact on profitability.  
By cleaning and preprocessing the data properly, we can ensure better ML model performance in the future.

---

## 📂 Dataset
The dataset comes from our Property Management System (PMS):

- File: hotel_bookings.csv  
- Size: ~119,000 rows × 32 columns  

---

## ⚙️ Project Phases

### Phase 1: Exploratory Data Analysis (EDA)
- Loaded the dataset into Pandas DataFrame.
- Generated summary statistics using .shape, .info(), .describe(), and .head().
- Visualized missing values using missingno.

---

### Phase 2: Handle Missing Values
- agent & company → replaced NaN with 0.  
- country → replaced NaN with the mode (most frequent country).  
- children → replaced NaN with the median.  
- customer_type → replaced NaN with the mode.  
- adr → replaced NaN with the median.  
- parking & special_requests → replaced NaN with 0.  

---

### Phase 3: Outlier Detection & Handling
- Used boxplot to detect outliers in ADR.  
- Capped extreme values → adr > 1000 was set to 1000.

---

### Phase 4: Remove Duplicates
- Removed all exact duplicate rows.

---

### Phase 5: Fix Data Types
- Converted reservation_status_date → datetime.  

---

### Phase 6: Feature Engineering
Created new useful features:
- total_guests = adults + children + babies  
- total_nights = stays_in_weekend_nights + stays_in_week_nights  
- is_family = 1 if (children > 0 or babies > 0) else 0  

---

### Phase 7: Encoding Categorical Variables
- One-Hot Encoding for low-cardinality features:  
  meal, market_segment, distribution_channel, customer_type.  
- Frequency Encoding for high-cardinality feature: country.  

---

### Phase 8: Drop Data Leakage Columns
Removed columns not available at prediction time:
- reservation_status  
- reservation_status_date  

---

### Phase 9: Train/Test Split
- Train: 80%  
- Test: 20%  
- Used random_state=42 for reproducibility.  

---

## ✅ Final Note
The dataset is now:
- Cleaned  
- Preprocessed  
- Ready for Machine Learning 🚀  

---
