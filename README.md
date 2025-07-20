# Customer Segmentation Analysis - CS434 Project

## Overview

This project performs comprehensive customer segmentation analysis on an online retail dataset using machine learning clustering techniques and RFM (Recency, Frequency, Monetary) analysis. The goal is to identify distinct customer segments to drive better customer relationship management strategies and business insights.

## Dataset

**Source**: Online Retail Dataset (Excel format)

- **Records**: ~540K transactions
- **Time Period**: 2010-2011  
- **Primary Market**: United Kingdom (with international customers)
- **Features**:
  - InvoiceNo: Transaction identifier
  - StockCode: Product code
  - Description: Product description
  - Quantity: Product quantity
  - InvoiceDate: Transaction date
  - UnitPrice: Product price
  - CustomerID: Customer identifier
  - Country: Customer location

## Project Structure

### 1. Data Exploration & Preprocessing

- **Data Loading**: Import and initial exploration of the retail dataset
- **Data Cleaning**:
  - Handle missing values (135K missing CustomerIDs)
  - Fix negative quantities by converting to absolute values
  - Remove zero unit prices
  - Detect and remove outliers (Quantity > 20K, UnitPrice > 10K)
- **Feature Engineering**:
  - Calculate profit (Quantity × UnitPrice)
  - Extract year and month from transaction dates
  - Text preprocessing for product descriptions

### 2. Exploratory Data Analysis (EDA)

- **Temporal Analysis**:
  - Yearly and monthly profit trends
  - Peak sales periods identification
- **Geographic Analysis**:
  - Country-wise order distribution
  - Revenue analysis by geography
  - Customer distribution across countries
- **Product Analysis**:
  - Top and least selling products
  - Price distribution analysis
- **Customer Behavior Analysis**:
  - Highest spending customers
  - Most frequent buyers
  - Purchase patterns

### 3. Customer Segmentation

#### RFM Analysis

- **Recency**: Days since last purchase
- **Frequency**: Number of transactions
- **Monetary**: Total amount spent

#### Clustering Techniques

1. **K-Means Clustering**
   - Optimal cluster determination using Elbow Method
   - Silhouette Score analysis
   - **Final Model**: 5 clusters with StandardScaler preprocessing

2. **Hierarchical Clustering**
   - Agglomerative clustering with Ward linkage
   - Dimensionality reduction using t-SNE
   - Euclidean distance metric

#### Customer Segments Identified

The analysis identifies 5 distinct customer segments based on purchasing behavior:

1. **Champions**: High recency, frequency, and monetary values
2. **Loyal Customers**: High frequency and monetary, moderate recency
3. **Potential Loyalists**: Recent customers with good monetary value
4. **New Customers**: Recent but low frequency/monetary
5. **At-Risk**: Low recency, previously high-value customers

### 4. Visualization & Insights

- 3D scatter plots for RFM visualization
- Cluster distribution plots
- Geographic heatmaps
- Temporal trend analysis
- Customer segment characteristics

## Key Findings

1. **Market Dominance**: UK represents ~90% of transactions and revenue
2. **Seasonal Patterns**: Strong seasonality with peaks in certain months
3. **Customer Concentration**: Small percentage of customers drive majority of revenue
4. **Geographic Diversity**: 37 countries represented, with significant international presence
5. **Product Portfolio**: Wide variety of products with clear bestsellers

## Technical Implementation

### Libraries Used

```python
- pandas, numpy: Data manipulation
- matplotlib, seaborn: Data visualization  
- scikit-learn: Machine learning algorithms
- sklearn.preprocessing.StandardScaler: Feature scaling
- sklearn.cluster: K-Means and Agglomerative clustering
- sklearn.decomposition.PCA: Dimensionality reduction
- sklearn.manifold.TSNE: Non-linear dimensionality reduction
```

### Model Performance

- **Optimal Clusters**: 5 (determined via Elbow Method and Silhouette Analysis)
- **Silhouette Score**: Optimized for best cluster separation
- **Preprocessing**: StandardScaler for feature normalization

## Business Applications

### Marketing Strategy

- **Personalized Campaigns**: Targeted marketing based on customer segments
- **Retention Programs**: Focus on at-risk customers
- **Loyalty Programs**: Reward champions and loyal customers

### Revenue Optimization

- **Cross-selling Opportunities**: Based on customer segment preferences
- **Pricing Strategy**: Segment-specific pricing models
- **Inventory Management**: Stock optimization based on customer demand patterns

### Customer Experience

- **Personalization**: Customized product recommendations
- **Service Levels**: Differentiated service based on customer value
- **Communication Strategy**: Segment-appropriate messaging

## Future Enhancements

1. **Additional Data Sources**:
   - Demographics (age, gender, income)
   - Psychographics (lifestyle, personality)
   - Geographic granularity (city-level analysis)

2. **Advanced Analytics**:
   - Customer Lifetime Value (CLV) modeling
   - Churn prediction models
   - Recommendation systems

3. **Real-time Segmentation**:
   - Dynamic customer segment updates
   - Real-time personalization engine
   - Automated marketing triggers

## Model Limitations

- **K-Means Sensitivity**: Requires pre-defining cluster count
- **Outlier Impact**: Sensitive to extreme values despite preprocessing
- **Static Analysis**: Segments based on historical data only
- **Missing Demographics**: Limited customer profile information

## Files Description

- `CS434.ipynb`: Main Jupyter notebook containing complete analysis
- `Online Retail dataset.xlsx`: Source dataset (not included in repo)
- `Project Goal.pdf`: Project objectives and requirements
- `README.md`: This documentation file

## Getting Started

1. **Environment Setup**:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```

2. **Data Preparation**:
   - Download the Online Retail dataset
   - Update file paths in the notebook
   - Mount Google Drive (if using Colab)

3. **Execution**:
   - Run cells sequentially in the Jupyter notebook
   - Adjust parameters as needed for your specific use case

## Author

**Course**: CS434 - Machine Learning/Data Science
**Analysis Period**: 2010-2011 Online Retail Data
**Implementation**: Python with scikit-learn

---

*This project demonstrates practical application of unsupervised machine learning techniques for business intelligence and customer analytics, providing actionable insights for retail strategy optimization.*
