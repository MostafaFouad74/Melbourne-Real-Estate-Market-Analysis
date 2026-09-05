# Melbourne Real Estate Market Analysis

> An end-to-end data analytics and machine learning project exploring the Melbourne housing market, identifying key factors influencing property prices, and transforming data into actionable business insights.

---

## 📌 Project Overview

This project was developed as an individual final capstone project for the **Data Analysis Using AI** training program by **Orange Digital Center Egypt**, in coordination with **Digital Hub**.

The project analyzes the **Melbourne Real Estate Market** using Python, Machine Learning, and Power BI to understand:

- What factors are associated with higher property prices?
- How does location affect property value?
- How do property types and characteristics influence prices?
- Can machine learning effectively classify properties into different price categories?
- How can analytical results be transformed into clear business insights?

The project follows an end-to-end analytical workflow:

**Data Cleaning → Exploratory Data Analysis → Feature Engineering → Machine Learning → Business Insights → Interactive Dashboard**

---

## 🎯 Project Objectives

The main objectives of this project were to:

1. Clean and prepare the Melbourne housing dataset.
2. Explore relationships between property prices and property characteristics.
3. Identify geographic and market patterns.
4. Engineer meaningful features for analysis and modeling.
5. Build and compare multiple machine learning models.
6. Identify the most important factors associated with property price categories.
7. Build an interactive Power BI dashboard for business-oriented analysis.
8. Use Generative AI as an analytical collaborator throughout the workflow.

---

## 📊 Dataset

The project uses the **Melbourne Housing Market** dataset.

### Dataset Size

- **13,580 rows**
- **21 original columns**
- Target variable: `Price`
- Geographic information: Latitude, Longitude, Suburb, Region
- Property information: Rooms, Bedrooms, Bathrooms, Car, Landsize, BuildingArea, YearBuilt
- Market information: Property Type, Method, Distance from CBD

The dataset contains property transactions across different Melbourne suburbs and regions.

---

# 🧹 Data Cleaning & Preparation

The dataset required several preprocessing steps before analysis.

### Missing Values

Missing values were identified in several variables, including:

- `BuildingArea`
- `YearBuilt`
- `CouncilArea`
- `Car`

Different strategies were applied depending on the variable type and analytical context.

### Cleaning Steps

The preprocessing workflow included:

- Handling missing numerical values using median imputation.
- Replacing missing `CouncilArea` values with `"Unknown"`.
- Converting `Date` into a proper datetime format.
- Checking for duplicate records.
- Detecting and treating statistical outliers using the IQR method.
- Applying logical checks to identify unrealistic property characteristics.
- Removing unnecessary columns.
- Creating new analytical features.

### Feature Engineering

Several features were created to improve the analysis:

- `Sale_Year`
- `Sale_Month`
- `Property_Age`
- `Total_Rooms`
- `Price_Category`

The `Price_Category` variable was created by using the median property price as the threshold:

- `1` → Expensive
- `0` → Affordable

---

# 🔎 Exploratory Data Analysis

The exploratory analysis focused on understanding the relationship between property prices, location, property characteristics, and market segments.

### Key Findings

#### 📍 Location Matters

Properties closer to the Melbourne CBD generally showed higher prices, while properties farther away tended to have lower prices.

Geographic location, represented by **Latitude and Longitude**, emerged as one of the strongest predictors in the machine learning analysis.

#### 🏠 Property Type

Different property types showed clear differences in average prices.

In general:

**Houses > Townhouses > Units**

#### 📈 Price Distribution

Property prices showed a right-skewed distribution, with a smaller number of very high-priced properties influencing the upper end of the market.

#### 🌍 Regional Differences

The Southern and Eastern Metropolitan regions showed relatively higher average property prices compared with several other regions.

---

# 🤖 Machine Learning

To evaluate whether machine learning could distinguish between relatively expensive and affordable properties, the continuous `Price` variable was transformed into a binary classification target called `Price_Category`.

Five models were trained and compared:

| Model | Accuracy |
|---|---:|
| 🌲 Random Forest | **89.9%** |
| SVM | **88.7%** |
| Logistic Regression | **87.1%** |
| Linear Regression | **86.4%** |
| Decision Tree | **85.3%** |

### 🏆 Best Performing Model

**Random Forest achieved the highest classification accuracy at 89.9%.**

The models were evaluated using classification metrics, including:

- Accuracy
- Confusion Matrix

> **Important:** The 89.9% figure represents the accuracy of classifying properties into the engineered `Price_Category` classes. It is not a direct prediction accuracy for the continuous property price.

---

# 🌟 Feature Importance

The Random Forest model highlighted several important features associated with the price category.

The strongest features included:

1. **Latitude**
2. **Longitude**
3. **Property Type**
4. **Distance from CBD**
5. **Landsize**
6. **BuildingArea**

### 💡 Main Insight

The analysis suggests that **location plays a stronger role in determining property price categories than simply having more rooms or a larger property**.

In other words:

> **Location, location, location.**

---

# 📊 Power BI Dashboard

An interactive Power BI dashboard was developed to transform the analytical results into a business-friendly format.

The dashboard contains three main pages:

### 1️⃣ Estate Market Dashboard

Provides a high-level overview of the Melbourne real estate market, including:

- Total Properties
- Average Price
- Median Price
- Average Distance from CBD
- Premium Property Percentage
- Average Price by Region
- Property Type Distribution
- Price Trends
- Sales Volume

![Dashboard Overview](visuals/dashboard_overview.png)

---

### 2️⃣ Property & Price Analysis

Explores the relationship between property characteristics and price.

Key metrics and visualizations include:

- Average Rooms
- Average Bathrooms
- Average Land Size
- Average Building Area
- Price vs. Rooms
- Price by Property Type
- Price vs. Distance from CBD
- Price by Bathrooms

![Property & Price Analysis](visuals/property_price_analysis.png)

---

### 3️⃣ Location & Market Opportunity

Focuses on geographic and market opportunities.

Includes:

- Top 7 suburbs by average price
- Bottom 7 suburbs by average price
- Geographic analysis
- Average price by location
- Property type distribution by location

![Location & Market Opportunity](visuals/location_market_opportunity.png)

---

# 📈 Model Comparison

The five machine learning models were compared based on their classification accuracy.

![Model Comparison](visuals/model_comparison.png)

The results show that **Random Forest performed best among the evaluated models**, achieving an accuracy of **89.9%**.

---

# 🧠 AI-Assisted Analytics

Generative AI was used as an analytical collaborator during the project.

AI assistance supported tasks such as:

- Comparing data cleaning approaches.
- Evaluating median vs. mean imputation decisions.
- Identifying potential anomalies.
- Supporting interpretation of analytical results.
- Generating and refining insights.
- Summarizing project findings.

The final analytical decisions were reviewed and incorporated into the overall workflow.

---

# 🛠️ Tools & Technologies

### Data Analysis
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn

### Machine Learning
- Scikit-learn
- Random Forest
- Support Vector Machine (SVM)
- Logistic Regression
- Linear Regression
- Decision Tree

### Business Intelligence
- Microsoft Power BI

### AI
- Generative AI / Claude

### Development Environment
- Google Colab / Jupyter Notebook

---

# 📁 Repository Structure

```text
Melbourne-Real-Estate-Market-Analysis/
│
├── dashboard/
│   └── Dashboard.pbix
│
├── data/
│   ├── raw/
│   │   └── melb_data.csv
│   │
│   └── cleaned/
│       └── melb_data_cleaned.csv
│
├── notebooks/
│   └── melbourne_real_estate_analysis.ipynb
│
├── presentation/
│   └── Melbourne_Real_Estate_Project.pptx
│
├── reports/
│   └── AI_Generated_Insights_Summary.docx
│
├── visuals/
│   ├── dashboard_overview.png
│   ├── property_price_analysis.png
│   ├── location_market_opportunity.png
│   └── model_comparison.png
│
└── README.md
