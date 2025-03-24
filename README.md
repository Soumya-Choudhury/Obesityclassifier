
# 🏥 Obesity Classification App

This is a **Streamlit** web application that predicts **obesity categories** using a **CatBoost model**. The model classifies individuals into different obesity levels based on **gender, age, height, weight, family history with overweight, dietary habits, and physical activity**.

## 🚀 Features
- **Accurate obesity prediction** using machine learning.
- **Interactive UI** built with Streamlit.
- **CatBoostClassifier** for fast and efficient predictions.
- **Lightweight & easy to deploy**.

---

## 📌 Installation
Clone the repository and install dependencies:
```bash
git clone https://github.com/Soumya-Choudhury/Obesityclassifier.git
cd Obesityclassifier
pip install -r requirements.txt
```

---

## ▶️ Usage
Run the Streamlit app:
```bash
streamlit run app.py
```

---

## ⚙️ How the Code Works

### **1️⃣ Data Preprocessing**
- Reads `ObesityDataSet_raw_and_data_sinthetic.csv` into a dataframe.
- Removes duplicates and unnecessary columns (`NCP`, `TUE`).
- Converts categorical values like **"Yes"/"No"** into **1/0**.
- Maps obesity categories to numerical values:
  ```python
  df_update["NObeyesdad"] = df_update["NObeyesdad"].map({
      "Insufficient_Weight": 0, "Normal_Weight": 1,
      "Overweight_Level_I": 2, "Overweight_Level_II": 3,
      "Obesity_Type_I": 4, "Obesity_Type_II": 5, "Obesity_Type_III": 6
  })
  ```

---

### **2️⃣ Feature Selection**
- Uses `mutual_info_classif` to analyze the **importance of features**.
- Identifies `FAF`, `family_history_with_overweight`, and `FAVC` as important factors.

---

### **3️⃣ Model Training & Evaluation**
- Splits the dataset into **training & testing sets**.
- Trains three models:
  - **Support Vector Machine (SVM)** -It gives testing accuracy of 86%. 
  - **Logistic Regression** -It gives testing accuracy of 81%.
  - **CatBoost Classifier** (final model) -It gives the best accuracy of 97%.
- Evaluates performance using:
  - **Classification Report**
  - **Confusion Matrix**



---

### **5️⃣ Deployment**
- The app is **deployed on Streamlit Cloud** for online access.

---

## 📂 File Structure
```
├── app.py              # Streamlit application
├── obesity.ipynb       # Jupyter Notebook for model training
├── requirements.txt    # Dependencies
├── README.md           # Documentation
```


## 👤 Author
**Soumya Choudhury**
