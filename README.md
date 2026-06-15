# 🚀 AI & Machine Learning Internship Projects


Welcome to the **Internship**  repository! This directory contains a diverse collection of machine learning, deep learning, and artificial intelligence projects developed during the AI/ML Internship at DevelopersHub Corporation. 

These projects showcase a progression from foundational Exploratory Data Analysis (EDA) to advanced, production-ready Natural Language Processing (NLP) and predictive modeling pipelines.

Below is an overview of the projects included in this repository. Please explore their respective directories for comprehensive code, datasets, Jupyter notebooks, and detailed documentation.

---

## 📂 Project Directory

### 1. 📈 [Future Stock Prices Prediction](./Future%20Stock%20Prices%20Prediction/)
**Objective**: Develop an automated data retrieval and machine learning system to predict the next day's closing price of stocks.
- **Methodology**: Ingests real-time financial time-series data using the `yfinance` API. Applies feature engineering (lagged features) and compares baseline Linear Regression against ensemble Random Forest Regressors to capture market trends.
- **Highlights**: Time-Series Forecasting, Scikit-Learn, yfinance API, Financial Analytics.

### 2. 🏥 [Health Chatbot (MedGuide)](./Health%20Chatbot/)
**Objective**: Build an advanced conversational agent to provide safe, concise, and reliable medical information while enforcing strict ethical guardrails.
- **Methodology**: Bridges high-performance LLMs (via OpenRouter API) with rigorous safety engineering. Implements "Safety Gate" architecture using Regex-based pattern matching to immediately detect emergencies and reject out-of-domain prompts.
- **Highlights**: Responsible AI, LLM Orchestration, Prompt Engineering, Safety Guardrails.

### 3. 🫀 [Heart Disease Prediction (CardioGuard AI)](./Heart%20Disease%20Prediction/)
**Objective**: Create a robust Binary Classification Pipeline designed to predict the likelihood of cardiovascular disease based on clinical biomarkers.
- **Methodology**: Utilizes Scikit-Learn Pipelines for automated preprocessing (imputation, scaling, encoding). Evaluates Logistic Regression against Decision Trees, optimizing strictly for Recall (Sensitivity) and ROC-AUC to minimize clinical False Negatives.
- **Highlights**: Medical Diagnostics, Scikit-Learn Pipelines, Classification Metrics, Feature Interpretability.

### 4. 🌸 [Iris EDA Visualization ML](./Iris%20EDA%20Visualization%20ML/)
**Objective**: Perform comprehensive Exploratory Data Analysis (EDA) and establish a baseline classification model on the multivariate Iris dataset.
- **Methodology**: Employs statistical visualization techniques (Seaborn, Matplotlib) to uncover patterns and multicollinearity in botanical measurements. Implements a highly interpretable Logistic Regression model to achieve near-perfect species classification.
- **Highlights**: Exploratory Data Analysis (EDA), Statistical Visualization, Multiclass Classification.

### 5. 🧠 [Mental Health Support Chatbot (SerenityAI)](./Mental%20Health%20Support%20Chatbot/)
**Objective**: Develop an empathetic conversational agent fine-tuned to provide emotionally resonant support for everyday stress and anxiety.
- **Methodology**: Fine-tunes a causal language model (`GPT-Neo 125M`) using PyTorch and Hugging Face Transformers on the Facebook EmpatheticDialogues dataset. Incorporates mixed precision (`fp16`) training and strict safety redirection for high-risk inputs.
- **Highlights**: Deep Learning, LLM Fine-Tuning, Hugging Face Transformers, NLP.
---

## 🛠️ Technologies & Frameworks Utilized
Across these projects, a variety of industry-standard tools and frameworks were utilized:
- **Programming Language**: Python (3.8+)
- **Deep Learning / NLP**: PyTorch, Hugging Face Transformers, OpenRouter API
- **Machine Learning**: Scikit-Learn
- **Data Engineering**: Pandas, NumPy, yfinance
- **Data Visualization**: Matplotlib, Seaborn
- **Model Serialization**: Joblib
---
**Developed with ❤️ by Aneeb-Ur-Rehman during the AI/ML Internship at 𝐃𝐞𝐯𝐞𝐥𝐨𝐩𝐞𝐫𝐬𝐇𝐮𝐛 𝐂𝐨𝐫𝐩𝐨𝐫𝐚𝐭𝐢𝐨𝐧.**