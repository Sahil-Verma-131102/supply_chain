# Supply Chain Data Analysis Project

## Overview

This project provides an end-to-end data analysis solution for a supply chain scenario involving Company X and its courier partners. It demonstrates the use of Python (pandas, numpy) for cleaning, merging, and analyzing multiple real-world datasets, including sales orders, SKU master, warehouse-to-customer zone mapping, courier invoices, and courier rate cards.

The project is organized in a Jupyter Notebook (`sahil_supply_chain.ipynb`) for full transparency and reproducibility. The notebook guides the user through initial exploratory data analysis, cleaning, and groundwork for further supply chain optimization and cost analysis.

## Table of Contents

- [Project Structure](#project-structure)
- [Data Sources](#data-sources)
- [Key Steps & Features](#key-steps--features)
- [Getting Started](#getting-started)
- [Analysis Outline](#analysis-outline)
- [Potential Extensions](#potential-extensions)
- [Dependencies](#dependencies)
- [Contributing](#contributing)
- [License](#license)

---

## Project Structure

```
.
├── sahil_supply_chain.ipynb        # Main analysis notebook
├── Company X - Order Report.xlsx   # Order data (sample)
├── Company X - SKU Master.xlsx     # SKU master (sample)
├── Company X - Pincode Zones.xlsx  # Pincode-to-zone mapping
├── Courier Company - Invoice.xlsx  # Courier billing invoice
├── Courier Company - Rates.xlsx    # Courier rate card
└── README.md                       # This file
```

---

## Data Sources

### 1. **Order Report (`df1`)**
   - Columns: `ExternOrderNo`, `SKU`, `Order Qty`
   - 400 rows, 3 columns
   - Represents sales/orders data.

### 2. **SKU Master (`df2`)**
   - Columns: `SKU`, `Weight (g)`
   - 66 rows, 2 columns
   - Maps SKU codes to their weights.

### 3. **Pincode Zones (`df3`)**
   - Columns: `Warehouse Pincode`, `Customer Pincode`, `Zone`
   - 124 rows, 3 columns
   - Maps each customer pincode to a delivery zone (A/B/C/D/E).

### 4. **Courier Invoice (`df4`)**
   - Columns: `AWB Code`, `Order ID`, `Charged Weight`, `Warehouse Pincode`, `Customer Pincode`, `Zone`, `Type of Shipment`, `Billing Amount (Rs.)`
   - 124 rows, 8 columns
   - Shows how much was billed per order by the courier.

### 5. **Courier Rates (`df5`)**
   - Columns: [fwd/rto]_[zone]_[fixed/additional]
   - 1 row, 20 columns
   - Courier rate card for both Forward and RTO (Return To Origin) charges.

---

## Key Steps & Features

1. **Data Import and Initial Exploration**
    - Load all Excel files into pandas DataFrames.
    - Display sample data from each dataset.

2. **Null Value & Duplicate Checks**
    - Check for missing values in each DataFrame.
    - Check and count duplicate entries for key columns.
    - Remove duplicates.

3. **Data Cleaning**
    - Drop duplicate rows from all datasets.
    - Ensure consistency in SKU, order IDs, pincodes, etc.

4. **Preparation for Analysis**
    - The notebook is structured for further merging of order, SKU, zone, and invoice data for holistic supply chain cost analysis.

---

## Getting Started

### Prerequisites

- Python 3.x
- Jupyter Notebook (or JupyterLab)
- pandas, numpy, openpyxl (for reading Excel files)

### Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/Sahil-Verma-131102/supply_chain.git
   cd supply_chain
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy openpyxl
   ```
3. Launch the Jupyter notebook:
   ```bash
   jupyter notebook sahil_supply_chain.ipynb
   ```
4. Ensure all Excel files are present in the same directory.

---

## Analysis Outline

The current notebook (`sahil_supply_chain.ipynb`) covers:

- **Data Loading:** Import all datasets and display their head/tail for initial assessment.
- **Nulls & Duplicates:** Systematic checks and cleaning.
- **Summary Stats:** Print row and column counts for quick validation.
- **Data Consistency:** Ensure unique SKUs and Order IDs, clean up as necessary.

**Next Steps (for users to extend):**

- Merge order, SKU, and pincode data to compute the actual shipment weight per order.
- Compare courier billing weights with computed weights to identify discrepancies.
- Calculate expected vs actual courier charges using the rate card.
- Visualize order volumes, weight distributions, zone-wise costs, etc.

---

## Potential Extensions

- **Automated Cost Audit:** Compare calculated vs billed courier costs and flag discrepancies.
- **Zone/Weight Optimization:** Analyze if SKUs are grouped efficiently for shipping.
- **Demand/Cost Visualization:** Charts for order distribution by zone, cost per kg, etc.
- **Anomaly Detection:** Find outlier shipments (weight, cost, etc).
- **Dashboard Integration:** Deploy as a dashboard using Streamlit or Dash.

---

## Dependencies

- pandas
- numpy
- openpyxl (for `.xlsx` support)
- Jupyter Notebook (for interactive analysis)

Install all via pip:
```bash
pip install pandas numpy openpyxl
```

---

## Contributing

Contributions are welcome! Please fork the repo and submit pull requests for improvements, bugfixes, or new analysis modules.

---

## License

This project is licensed under the MIT License.

---

## Author

[Sahil Verma](https://github.com/Sahil-Verma-131102)
