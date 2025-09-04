## Project 1 – Titanic Dataset: Data Cleaning & EDA

# Titanic Dataset: Data Cleaning & Exploratory Data Analysis (EDA)

## 📖 Overview
This project performs **data cleaning and exploratory data analysis (EDA)** on the famous [Titanic dataset](https://www.kaggle.com/c/titanic).  
The aim is to explore survival patterns, identify influential factors, and create meaningful visualizations.


## 🗂 Dataset
- **Train set**: 891 passengers, 12 features
- **Test set**: 418 passengers, 11 features
- **Gender submission file**: Survival predictions template

Key features include:
- PassengerId, Name, Sex, Age, Pclass, Fare, Cabin, Embarked
- Survival label (0 = did not survive, 1 = survived)

---

## 📁 Project Structure
titanic-eda/
│── data/
│ ├── train.csv
│ ├── test.csv
│ └── gender_submission.csv
│── notebooks/
│ └── titanic_eda.ipynb
│── README.md
│── requirements.txt


---

## 🔧 Data Cleaning
- **Age**: Missing values filled using median grouped by Sex & Pclass  
- **Embarked**: Filled with mode (most common value)  
- **Cabin**: Too many missing → created binary feature `HasCabin`  
- **New Features**:  
  - `FamilySize = SibSp + Parch + 1`  
  - `IsAlone` (binary)  
  - `Title` extracted from names  

---

## 📊 Exploratory Data Analysis
- **Univariate Analysis**: Survival distribution, Age distribution, Class distribution  
- **Bivariate Analysis**:  
  - Survival by Sex, Pclass, Embarked, FamilySize, Title  
- **Multivariate**: Correlation heatmap & categorical plots  

---

## 🔑 Key Findings
- Overall survival rate ≈ **38%**  
- **Sex**: Females ≈ 74% survival, Males ≈ 19%  
- **Class**: 1st ≈ 63%, 2nd ≈ 47%, 3rd ≈ 24%  
- **Age**: Children (<12) had higher survival, elderly (>60) much lower  
- **Family size**: Small families (2–4) did better, very large or solo travelers fared worse  
- **Cabin info**: Recorded cabin strongly linked to survival  
- **Titles**: Mrs, Miss, Master → higher survival; Rare titles → lower survival  

---

## ✅ Conclusion
- The strongest predictors of survival: **Sex, Pclass, and Age**  
- Results align with *“Women and children first”* policy during Titanic evacuation  
- Wealth and social status improved survival chances  

---

## ▶️ How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/titanic-eda.git
   cd titanic-eda
2. Install dependencies:
   pip install -r requirements.txt
3. Run the Jupyter notebook:
   jupyter notebook notebooks/titanic_eda.ipynb

## To-Do / Future Work

1.Build predictive survival models (Logistic Regression, Random Forest, XGBoost)
2.Perform feature importance ranking
3.Try deep learning survival prediction (Keras/TensorFlow)
4.Deploy a simple Titanic survival prediction web app

## Tools Used

1.Python (pandas, numpy, seaborn, matplotlib)
2.Jupyter/Colab for visualization

## License
This project is licensed under the MIT License – you are free to use, modify, and distribute it.


## Project 2 – Twitter Sentiment Analysis & EDA
# Twitter Sentiment Analysis & Exploratory Data Analysis (EDA)

## 📖 Overview
This project analyzes a **Twitter dataset** containing tweets labeled with entities (brands/products) and sentiment labels.  
It includes **data cleaning, sentiment analysis (TextBlob & VADER), visualization, and topic analysis**.

---

## 🗂 Dataset
- **Training set**: ~74,681 tweets (reduced to ~69k after cleaning)
- **Validation set**: 999 tweets
- Features: `tweet_id`, `entity`, `label`, `text`


  ## 📁 Project Structure
  twitter-sentiment-eda/
│── data/
│ ├── twitter_training.csv
│ └── twitter_validation.csv
│── notebooks/
│ └── twitter_sentiment_analysis.ipynb
│── README.md
│── requirements.txt


---

## 🔧 Data Cleaning
- Standardized headers (`text`, `label`, `entity`, `tweet_id`)  
- Removed duplicates and missing values  
- Cleaned text columns and normalized  

---

## 📊 Exploratory Data Analysis
1. **Sentiment Distribution** – Most tweets Neutral or Positive, fewer Negative  
2. **Polarity & Subjectivity (TextBlob)** –  
   - Polarity clustered between 0 and +0.3 (mild positivity)  
   - Subjectivity >0.5 → tweets are opinion-heavy  
3. **Entities/Brands** – Microsoft, Google, Twitter, Apple most mentioned  
4. **Word Cloud & Frequent Words** – mix of praise (“love”, “great”) and complaints (“bad”, “problem”)  
5. **Time Series Analysis** – Polarity trends across tweet IDs  
6. **Advanced Sentiment (VADER)** – Detected sarcasm and nuanced negatives better than TextBlob  
7. **Correlation** – Polarity (TextBlob) vs Compound (VADER) correlation ≈ 0.6  

---

## 🔑 Key Findings
- Overall sentiment on Twitter: **slightly positive, mostly neutral**  
- Brands differ in public perception – some lean positive (Google), others mixed (Twitter)  
- Strong correlation between TextBlob & VADER → combining improves reliability  
- Frequent negative terms highlight common complaints → useful for businesses  

---

## ✅ Conclusion
This project demonstrated how **NLP sentiment analysis** can be applied to real-world Twitter data.  
Insights can help brands monitor reputation, identify problem areas, and improve engagement.  
Future work: extend to **deep learning models (BERT, RoBERTa)** and **real-time monitoring**.

---

## ▶️ How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/twitter-sentiment-eda.git
   cd twitter-sentiment-eda
2. Install dependencies:
   pip install -r requirements.txt
3. Run the Jupyter notebook:
   jupyter notebook notebooks/twitter_sentiment_analysis.ipynb

## To-Do / Future Work
1. Train and evaluate deep learning sentiment models (BERT, RoBERTa, LSTM)
2. Deploy a real-time Twitter sentiment dashboard
3. Add multilingual sentiment analysis
4. Perform topic modeling (LDA, BERTopic) for deeper insights

##  Tools Used
1. Python (pandas, numpy, seaborn, matplotlib, plotly)
2. NLP Libraries: NLTK, TextBlob, VADER
3. WordCloud for text visualization

## License
This project is licensed under the MIT License – you are free to use, modify, and distribute it.

