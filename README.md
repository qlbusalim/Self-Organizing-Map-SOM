# Self-Organizing Map (SOM) for Customer Segmentation

A machine learning project implementing Self-Organizing Maps (SOM) to perform customer segmentation analysis on the Online Retail dataset from the UCI Machine Learning Repository.

## 📋 Project Overview

This project uses Self-Organizing Maps (SOM), an unsupervised learning technique, to identify and visualize customer segments based on their purchasing behavior. The analysis is performed on transactional data from a UK-based online retail store.

## 🎯 Objectives

- Perform customer segmentation using Self-Organizing Maps
- Identify distinct customer groups based on purchasing behavior
- Analyze customer characteristics using RFM (Recency, Frequency, Monetary) features
- Visualize customer clusters on a 2D map

## 📊 Dataset

**Source:** [UCI Machine Learning Repository - Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)

**Features:**
- `InvoiceNo`: Transaction identifier
- `StockCode`: Product identifier
- `Description`: Product name
- `Quantity`: Number of items per transaction
- `InvoiceDate`: Transaction timestamp
- `UnitPrice`: Product price per unit (in sterling)
- `CustomerID`: Unique customer identifier
- `Country`: Customer's country

**Dataset Size:** 541,909 transactions

## 🛠️ Technologies Used

- **Python 3.x**
- **Libraries:**
  - `pandas` - Data manipulation
  - `numpy` - Numerical operations
  - `matplotlib` - Data visualization
  - `scikit-learn` - Data preprocessing and scaling
  - `minisom` - Self-Organizing Map implementation
  - `ucimlrepo` - Dataset fetching

## 🔧 Installation

1. Clone the repository:
```bash
git clone https://github.com/qlbusalim/Self-Organizing-Map-SOM.git
cd Self-Organizing-Map-SOM
```

2. Install required packages:
```bash
pip install pandas numpy matplotlib scikit-learn minisom ucimlrepo
```

## 📁 Project Structure

```
Self-Organizing-Map-SOM/
├── Data/
│   └── Online Retail.xlsx          # Raw dataset
├── models/                          # Saved models directory
├── SOM.ipynb                        # Main Jupyter notebook
├── Asesmen Individu 2.docx         # Project documentation (Word format)
├── Asesmen Individu 2.pdf          # Project documentation (PDF format)
└── README.md                        # This file
```

## 🚀 Usage

1. Open the Jupyter notebook:
```bash
jupyter notebook SOM.ipynb
```

2. Run the cells sequentially to:
   - Load and explore the dataset
   - Preprocess the data
   - Engineer customer features
   - Train the SOM model
   - Visualize and analyze results

## 📈 Methodology

### 1. Data Preprocessing
- **Missing Values Handling**: Remove transactions without CustomerID
- **Data Cleaning**: Filter out negative quantities and prices (returns/cancellations)
- **Duplicate Removal**: Eliminate duplicate transactions

### 2. Feature Engineering
Created comprehensive customer features including:
- **Recency**: Days since last purchase
- **Frequency**: Number of unique transactions
- **Monetary**: Total spending amount
- **Average Quantity**: Mean items per transaction
- **Product Variety**: Number of unique products purchased
- **Tenure**: Customer lifetime (days between first and last purchase)
- **Country**: Customer location (encoded)

### 3. Feature Transformation
- **Log Transformation**: Applied to skewed features (Frequency, Monetary, Total_Quantity, Product_Variety)
- **Outlier Removal**: IQR method (1.5 × IQR) to remove extreme outliers
- **Standardization**: StandardScaler for feature normalization

### 4. SOM Configuration
- **Map Size**: 10×10 grid
- **Learning Rate**: 0.5 (initial)
- **Sigma**: 1.5 (neighborhood radius)
- **Iterations**: 10,000
- **Neighborhood Function**: Gaussian

### 5. Model Evaluation
- **Quantization Error**: Measures data representation quality
- **Topographic Error**: Assesses topology preservation
- **Node Utilization**: Distribution of customers across map

## 📊 Results

The trained SOM successfully segments customers into distinct groups based on:
- Purchasing frequency and recency
- Average spending patterns
- Product diversity preferences
- Customer loyalty (tenure)

**Model Performance:**
- Final dataset: 3,879 customers with 7 features
- Node utilization: 100% (all nodes utilized)
- Training completed in ~0.38 seconds

## 🔍 Key Findings

The SOM analysis reveals several customer segments:
1. **High-Value Customers**: High frequency, monetary value, and product variety
2. **Occasional Buyers**: Low frequency but moderate spending
3. **New Customers**: Recent purchases with short tenure
4. **Dormant Customers**: High recency (haven't purchased recently)

## 📝 Preprocessing Pipeline Summary

| Stage | Records In | Records Out | Removed | % Loss |
|-------|------------|-------------|---------|--------|
| Initial | 541,909 | - | - | - |
| Missing Values | 541,909 | 406,829 | 135,080 | 24.93% |
| Data Cleaning | 406,829 | 392,692 | 14,137 | 3.47% |
| Feature Engineering | 392,692 → 4,338 customers | - | - |
| Outlier Removal | 4,338 | 3,879 | 459 | 10.58% |
| **Final** | **3,879 customers** | | | |

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📄 License

This project is available for educational and research purposes.

## 👤 Author

**qlbusalim**
- GitHub: [@qlbusalim](https://github.com/qlbusalim)

## 🙏 Acknowledgments

- UCI Machine Learning Repository for providing the dataset
- MiniSom library developers
- The open-source community

## 📚 References

- Kohonen, T. (1982). "Self-Organized Formation of Topologically Correct Feature Maps"
- UCI Machine Learning Repository: Online Retail Dataset
- MiniSom Documentation: https://github.com/JustGlowing/minisom

---

**Note**: This project is part of an individual assessment (Asesmen Individu 2).
