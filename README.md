# Instant Personalized Quote Generator Using ML & LLM

## Project Overview
**Objective:** Provide customers with instant, personalized insurance quotes using Machine Learning (ML) and Large Language Models (LLM).

**Key Features:**
- Predicts customer insurance risk using historical data
- Calculates personalized insurance premiums
- Provides customer-friendly explanations using AI/LLM
- Fully automated, end-to-end workflow

---

## Use Case
**Use Case Name:** Instant Personalized Quote Generator  
**Customer Problem:** Customers find traditional quoting slow and generic  
**Primitive Functions:** `extractData()`, `lookupValue()`, `calculate()`, `applyFormula()`, `displayInformation()`  
**Function Composition:**
1. Extract user data
2. Lookup base rates
3. Calculate risk factors
4. Apply premium formula
5. Display quote  

**Tools/Functions Required:** Calculator API, Risk assessment engine, Location data service  
**Prompt Strategy:** Acts as a personal insurance advisor. Gathers necessary info step-by-step and generates tailored quotes.  
**Solution:** Provides instant, personalized quotes without human intervention, increasing conversion.

---

## Dataset
**Columns:** `customer_id`, `age`, `vehicle_type`, `location`, `claim_history`, `base_rate`, `risk_multiplier`

**Sample Data:**
| customer_id | age | vehicle_type | location | claim_history | base_rate | risk_multiplier |
|------------|-----|--------------|---------|---------------|-----------|----------------|
| C001       | 58  | Car          | Urban   | 2             | 5001      | 1.6            |
| C002       | 32  | Car          | Rural   | 0             | 5885      | 1.0            |
| C003       | 65  | Car          | Rural   | 3             | 4565      | 1.5            |
| C004       | 19  | Car          | Urban   | 1             | 5534      | 1.3            |
| C005       | 56  | Car          | Rural   | 1             | 5966      | 1.2            |

---

## Project Pipeline
1. **Load Data:** Loaded CSV dataset using pandas.
2. **Encode Categorical Variables:** Converted `vehicle_type` and `location` to numerical values using LabelEncoder.
3. **ML Model Training:** Random Forest Classifier predicts `risk_level` based on `age`, `vehicle_type`, `location`, `claim_history`.
4. **Premium Calculation:**  
   `Premium = base_rate * risk_multiplier * coverage_factor`  
   Coverage factors example: Car=1.2, Bike=1.0
5. **LLM Explanation:** Falcon 7B Instruct LLM explains risk and premium in customer-friendly language.
6. **Full Pipeline:** Input → Risk Prediction → Premium Calculation → Explanation (LLM)

---

## Sample Output
**Input:**  
Age=40, Vehicle=Car, Location=Urban, Claim History=2, Base Rate=5500, Risk Multiplier=1.4  

**Output:**  
- Predicted Risk: Medium  
- Final Premium: ₹7700  
- LLM Explanation: The insurance premium for this customer is ₹7700 because their age, claim history, and location classify them as medium risk. This ensures they are covered adequately while keeping the premium fair.

---

## Graphical Insights
1. **Risk Distribution:** Quickly see how many customers are high, medium, or low risk. Great for executives to understand the risk profile.
2. **Premium vs Age:** Shows how premium varies with age and risk level. Highlights that older customers or higher-risk customers have higher premiums.

---

## Key Features / Takeaways
- Data-Driven: ML predicts risk using historical data
- End-to-End: Input → Risk → Premium → Explanation
- Customer-Friendly: LLM explains complex calculations in plain language
- Automated & Scalable: Handles thousands of customers
- Business-Relevant: Quick, personalized quotes improve conversion

---

## Tools & Libraries
- Python 3.12  
- Pandas: Data processing  
- Scikit-learn: ML model & preprocessing  
- Transformers (HuggingFace): Falcon LLM for explanations  
- Joblib: Save/load ML models  
- Matplotlib & Seaborn: Graphs and visualizations  
- FPDF: Generate PDF report

---

## How to Run
1. Clone the repository:
```bash
git clone <repository-url>
