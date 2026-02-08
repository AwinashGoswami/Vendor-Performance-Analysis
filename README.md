# Vendor Performance Analysis

A comprehensive data analytics project for analyzing vendor performance, inventory management, and sales metrics. This project leverages data ingestion, exploratory data analysis, and statistical insights to optimize vendor relationships and inventory decisions.

## 📋 Project Overview

This project performs end-to-end analysis of vendor performance by:
- Ingesting raw inventory, purchase, and sales data into a SQL Server database
- Generating comprehensive vendor performance summaries with profitability metrics
- Conducting exploratory data analysis to identify trends, anomalies, and opportunities
- Providing actionable insights through statistical analysis and visualization

**Key Metrics Analyzed:**
- Gross profit and profit margins by vendor
- Sales and purchase volumes and dollars
- Stock turnover and inventory efficiency
- Freight costs and logistics optimization
- Pricing analysis and cost-benefit relationships

## 📁 Project Structure

```
Vendor Performance Analysis/
├── README.md                              # Project documentation
├── get_vendor_summary.py                  # Vendor summary aggregation script
├── ingestion_db.py                        # Database ingestion utility
├── Vendor Performance Analysis.ipynb       # Main analysis notebook
├── Exploratory Data Analysis.ipynb        # EDA exploration notebook
├── vendor_analysis.ipynb                  # Additional analysis notebook
├── Vendor Performance Dashboard.pbix      # Power BI dashboard
├── vendor_sales_summary.csv               # Aggregated vendor summary (CSV)
├── vendor_sales_summary.xlsx              # Aggregated vendor summary (Excel)
├── data/                                  # Raw data directory
│   └── New folder/
│       ├── begin_inventory.csv            # Starting inventory snapshot
│       ├── end_inventory.csv              # Ending inventory snapshot
│       ├── purchase_prices.csv            # Purchase pricing reference
│       ├── purchases.csv                  # Purchase transactions
│       ├── sales.csv                      # Sales transactions
│       └── vendor_invoice.csv             # Vendor invoice details
├── logs/                                  # Application logs
└── __pycache__/                           # Python cache files
```

## 🚀 Getting Started

### Prerequisites

- Python 3.7+
- SQL Server with LocalDB or Express edition
- ODBC Driver 17 for SQL Server
- Jupyter Notebook or VS Code

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd "Vendor Performance Analysis"
   ```

2. **Install required Python packages**
   ```bash
   pip install pandas sqlalchemy pyodbc numpy matplotlib seaborn scipy
   ```

3. **Configure database connection** (if needed)
   - Edit `ingestion_db.py` to update your SQL Server connection string
   - Default: `localhost\SQLEXPRESS01` with database `inventory`

## 📊 Usage

### 1. Data Ingestion

Ingest raw CSV files into the SQL Server database:

```bash
python ingestion_db.py
```

This script will:
- Read all CSV files from the `data/` directory
- Create corresponding tables in the `inventory` database
- Log ingestion details to `logs/ingestion.log`

### 2. Generate Vendor Summary

Create an aggregated vendor performance summary:

```bash
python get_vendor_summary.py
```

This script will:
- Merge multiple data tables using complex SQL queries
- Calculate key metrics (gross profit, margins, turnover, etc.)
- Export results to `vendor_sales_summary.csv`
- Log execution details to `logs/get_vendor_summary.log`

### 3. Run Analysis

Open and run the Jupyter notebooks to explore the data:

- **Vendor Performance Analysis.ipynb** - Main analysis with EDA, visualizations, and statistical tests
- **Exploratory Data Analysis.ipynb** - Detailed EDA and data quality assessment
- **vendor_analysis.ipynb** - Additional analytical insights

## 📈 Key Features

### Data Processing
- **Multi-table aggregation** - Combines purchases, sales, inventory, and invoice data
- **Quality filtering** - Removes negative profits and zero-quantity items for clean analysis
- **Calculated metrics** - Derives gross profit, profit margins, stock turnover, and efficiency ratios

### Analysis Capabilities
- **Distribution analysis** - Histograms and KDE plots for numerical columns
- **Outlier detection** - Boxplots and statistical outlier identification
- **Statistical testing** - T-tests and correlation analysis
- **Trend identification** - Sales patterns, seasonal variations, and vendor performance trends

### Insights Generated
- Vendor profitability rankings
- Product performance by category
- Inventory optimization opportunities
- Logistics cost analysis
- Pricing strategy recommendations

## 📝 Data Dictionary

### Vendor Sales Summary Table

| Column | Description |
|--------|-------------|
| VendorNumber | Unique vendor identifier |
| VendorName | Vendor company name |
| Brand | Product brand/category |
| Description | Product description |
| PurchasePrice | Historical purchase price per unit |
| ActualPrice | Current purchase price per unit |
| Volume | Purchase volume tier |
| TotalPurchaseQuantity | Total units purchased |
| TotalPurchaseDollars | Total purchase dollar amount |
| TotalSalesQuantity | Total units sold |
| TotalSalesDollars | Total sales dollar amount |
| GrossProfit | Total gross profit (Sales - Purchase) |
| ProfitMargin | Profit margin percentage |
| FreightCost | Freight and shipping costs |
| StockTurnover | Sales quantity / Purchase quantity ratio |

## 🔍 Key Findings

- **Negative Profits**: Some vendors show negative gross profits, indicating below-cost sales or high operational expenses
- **Premium Products**: Select products command significantly higher prices (up to $7,500), representing premium offerings
- **Freight Variability**: Shipping costs range from $0.09 to $257K, suggesting opportunities for logistics optimization
- **Stock Turnover**: Values >1 indicate faster sales fulfillment from older inventory; Values near 0 suggest slow-moving or obsolete stock
- **Data Quality**: Zero sales quantities and profit margin anomalies require business logic validation

## 📊 Visualizations

- Distribution plots for all numerical columns
- Boxplots for outlier detection
- Correlation matrices for variable relationships
- Vendor performance comparison charts
- Profit/loss analysis by vendor and product
- Inventory turnover analysis

## 🛠️ Technologies Used

- **Python 3** - Data processing and analysis
- **Pandas** - Data manipulation and aggregation
- **SQLAlchemy** - SQL query interface
- **SQL Server** - Data warehouse
- **Matplotlib & Seaborn** - Data visualization
- **SciPy** - Statistical analysis
- **Jupyter Notebook** - Interactive analysis environment
- **Power BI** - Dashboard and reporting (optional)

## 📋 Logging

The project includes comprehensive logging for operational visibility:

- **logs/ingestion.log** - Data ingestion details and timing
- **logs/get_vendor_summary.log** - Vendor summary generation logs
- **logs/** - Additional operational logs

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👤 Author

Created as part of a comprehensive data analytics initiative focused on vendor performance optimization and inventory management.

## 📞 Support

For issues, questions, or suggestions, please open an issue in the repository or contact the project maintainer.

## 🗺️ Roadmap

- [ ] Add automated data refresh scheduling
- [ ] Implement real-time dashboard updates
- [ ] Expand statistical modeling (predictive analytics)
- [ ] Add vendor benchmarking comparisons
- [ ] Implement cost optimization algorithms
- [ ] Add export functionality to multiple formats
- [ ] Create API for external integrations

## 📚 References

- [SQL Server Documentation](https://docs.microsoft.com/sql/)
- [Pandas Documentation](https://pandas.pydata.org/)
- [SciPy Statistics](https://docs.scipy.org/doc/scipy/reference/stats.html)
- [SQLAlchemy](https://www.sqlalchemy.org/)

---

**Last Updated**: February 2026
