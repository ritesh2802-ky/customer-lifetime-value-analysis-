Customer Lifetime Value Analysis — Strategic Segmentation

Which customers should a business invest in, and which ones are silently draining the marketing budget?

This project answers that question using real e-commerce transaction data (541K+ transactions, 4,300+ customers) to segment customers, predict their future value, and deliver actionable marketing recommendations.


Key Findings

 Segment        % of Customers        Avg Spend      (£)Avg Frequency   Strategy
Champions             22%            £6,000              11 order      Protect & reward — VIP loyalty programLoyal 
Customers             23%            £1,500              4 order       Upsell & deepen — referral program
At Risk               15%            £1,200              3.5 order     Urgent win-back — reactivation campaign
Lost                  19%            £200                1 order       Stop spending — reallocate budget

The insight: Champions (22% of customers) spend 4x more per person than any other segment. Meanwhile, Lost customers (19%) average just £200. Redirecting marketing spend from Lost to At-Risk offers the highest ROI opportunity.

Methodology
1. Data Cleaning

Removed 135K+ rows with missing Customer IDs (guest checkouts)
Filtered out cancelled orders and zero-value transactions
Engineered a Revenue column (Quantity × Unit Price)

2. RFM Analysis
Scored every customer on three dimensions:

Recency — How recently did they purchase?
Frequency — How often do they purchase?
Monetary — How much do they spend?
Each customer scored 1–5 on each dimension, then classified into 7 business segments.

3. CLV Prediction
BG/NBD Model — Predicts the probability a customer is still "alive" and how many future purchases they'll make
Gamma-Gamma Model — Predicts average monetary value per transaction
Combined to forecast 6-month Customer Lifetime Value for every customer

4. Strategic Recommendations
Translated analytical outputs into segment-level marketing strategies with specific actions and expected ROI.

Tech Stack
Tool                      Purpose
Python (Pandas, NumPy)    Data cleaning and manipulation
Lifetimes library         BG/NBD and Gamma-Gamma CLV models
Matplotlib, Seaborn       Statistical visualisations
Scikit-Learn              Supporting analysis
Power BI                  Interactive executive dashboard

Project Structure
├── CLV_Project.ipynb          # Full analysis notebook (run this)
├── README.md                  # You're reading this
├── dashboard_screenshot.png   # Power BI dashboard preview
├── data/
│   └── Online Retail.xlsx     # Raw dataset (UCI ML Repository)
├── outputs/
│   ├── clv_dashboard_data.csv       # Cleaned data for Power BI
│   ├── clv_segment_summary.csv      # Segment-level summary
│   └── clv_top_100_customers.csv    # Top 100 customers by predicted CLV
└── visuals/
    ├── rfm_segments.png       # RFM segmentation charts
    └── clv_predictions.png    # CLV prediction distributions

How to Run

Clone this repository

bash  
git clone https://github.com/ritesh2802-ky/customer-lifetime-value-analysis.git
cd customer-lifetime-value-analysis

Install dependencies

bash   
pip install pandas numpy matplotlib seaborn lifetimes openpyxl scikit-learn

Download the dataset

Go to UCI Online Retail Dataset
Download Online Retail.xlsx and place it in the data/ folder


Run the notebook

bash   
jupyter notebook CLV_Project.ipynb

Dashboard
The Power BI dashboard provides an interactive view of:
        
Customer distribution across segments (donut chart)
Average monetary value by segment (bar chart)
Frequency vs. monetary scatter plot showing segment positioning
KPI cards: Avg CLV, total revenue, customer count


What I Learned

80/20 is real: A minority of customers drive the majority of revenue. Quantifying this changes how you think about marketing spend.
RFM is powerful because it's simple: Executives don't need complex models — they need segments they can act on.
The model isn't the deliverable: The strategic recommendation is. A CLV number means nothing until you translate it into "invest here, cut there."
Data cleaning is 60% of the work: The raw dataset had 135K+ rows with missing customer IDs, cancellations mixed with purchases, and zero-value transactions. The analysis is only as good as the cleaning.


Dataset
UCI Machine Learning Repository — Online Retail Dataset
Real transaction data from a UK-based online retailer. 541,909 transactions across 38 countries, December 2010 – December 2011.

Author
Ritesh Kumar Yadav
Master of Business Analytics @ Deakin University


This project was completed as part of building a strategic analytics portfolio. The goal was not just to run models, but to translate data into business decisions — the skill that separates analysts from strategic advisors.
