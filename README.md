# Bank Customer Churn Analysis

Why do some customers leave a bank while others stay? I explored this question using Python, starting with messy customer and account data.

This project covers data cleaning, exploratory analysis and feature preparation. My aim was to practise turning raw data into a useful dataset and explore patterns that could support further churn analysis.

## About the Data

The cleaned dataset contains **10,000 customers** from France, Germany and Spain. It includes customer details, credit scores, account balances, estimated salaries, product usage and membership activity.

The target column is `Exited`:
- **1** — the customer left the bank.
- **0** — the customer stayed.

## Tools Used

- **Python**
- **Pandas and NumPy** for cleaning and preparing data
- **Matplotlib and Seaborn** for visualisation
- **Jupyter Notebook** for the analysis

## What I Did

### 1. Combined and checked the data

I joined the customer and account sheets using `CustomerId`. After the merge, I removed duplicate rows and kept one tenure column, leaving 10,000 customer records.

### 2. Cleaned the dataset

The raw data contained several issues that needed attention:

- Removed euro symbols from balance and salary fields and converted them to numeric values.
- Filled three missing ages with the median age.
- Replaced missing surnames with `Missing`.
- Replaced invalid salary values of `-999999` with the salary median.
- Standardised `FRA`, `French` and `France` into one country label: `France`.

### 3. Explored customer churn

I used bar charts, box plots and histograms to explore churn alongside customer characteristics, including:

- Country and gender
- Active membership and credit card ownership
- Age and credit score
- Account balance and estimated salary
- Tenure and number of products

### 4. Prepared features for future modelling

I removed customer IDs and surnames from the modelling dataset and converted categorical columns into dummy variables.

I also created a `balance_v_income` feature by dividing account balance by estimated salary. This provided another way to explore customers’ balances relative to their estimated income.

## Dataset Summary

| Measure | Result |
|---|---:|
| Customers after cleaning | 10,000 |
| Customers who left | 2,037 |
| Customers who stayed | 7,963 |
| Overall churn rate | 20.37% |
| Customers in France | 5,014 |
| Customers in Germany | 2,509 |
| Customers in Spain | 2,477 |

Around **one in five customers** in this dataset left the bank. This also means the target classes are uneven, which will matter when evaluating a future prediction model.

These results describe the dataset; they do not establish why individual customers left.

## Project Files

| File | Description |
|---|---|
| `Untitled.ipynb` | Notebook containing cleaning, exploration and feature preparation |
| `Bank_Churn_Messy.xlsx` | Raw workbook used as the notebook’s input |
| `Bank_Churn.csv` | Additional bank churn dataset included in the repository |
| `Bank_Churn_Data_Dictionary.csv` | Descriptions of the dataset’s columns |

## How to Run

1. Download or clone this repository.
2. Keep the notebook and Excel workbook in the same folder.
3. Install the required packages:

   ```bash
   pip install pandas numpy matplotlib seaborn openpyxl jupyter
   ```

4. Open the notebook in Jupyter or VS Code.
5. Run the cells from top to bottom.

## What I Learned

This project helped me practise checking data after a merge, identifying invalid values and making inconsistent categories usable for analysis. It also gave me experience exploring customer behaviour through charts and preparing features for machine learning.

## Next Steps

The notebook currently ends at feature preparation. My next steps are to compare churn rates across customer groups more explicitly and build a baseline prediction model.

Before modelling, I would split the data into training and test sets and learn imputation values from the training data only. I would also review extreme balance-to-income ratios and evaluate precision, recall and F1-score alongside accuracy.

## Author

Hassan Ijaz
