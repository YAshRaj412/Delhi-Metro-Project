

## Delhi Metro Data Cleaning & EDA Project

This project involves a comprehensive cleaning and exploratory data analysis (EDA) of a Delhi Metro trip dataset. The primary goal is to take a raw, messy dataset, apply rigorous cleaning and transformation techniques using Pandas, and then perform a visual analysis with Matplotlib and Seaborn to uncover key insights and trends.

###  Key Activities

**1. Data Cleaning & Preparation (Pandas & NumPy)**

* **Handled Inconsistent Text:** Cleaned the `From_Station` column, which had ~30% of its values affected by leading/trailing whitespace and inconsistent casing (e.g., `"  MODEL TOWN  "` was standardized to `"Model Town"`).
* **Standardized Missing Values:** Converted non-standard nulls (like `'NA'` strings in `Ticket_Type` and blank strings in `Remarks`) to proper `np.nan` values for accurate analysis.
* **Data Imputation:** Filled missing `Passengers` values (approx. 1% of data) using the dataset's **median** value to maintain data integrity.
* **Corrected Inaccurate Data:** Performed targeted data correction by remapping specific erroneous entries (e.g., changing "Return" to "Tourist Card" for certain rows) to ensure consistency.

**2. Feature Engineering**

* Created a `Profit_per_passenger` column by calculating the difference between `Fare` and `Cost_per_passenger`.
* Engineered a total `Profit` feature for each trip by multiplying `Profit_per_passenger` by the number of `Passengers`.

**3. Exploratory Data Analysis & Visualization (Matplotlib & Seaborn)**

* **Station Analysis:** Identified and visualized the top 10 busiest stations based on both departure counts (`From_Station`) and total traffic (departures + arrivals).
* **Profit & Revenue:** Plotted a **7-day rolling average** of total daily profit to observe financial trends over time, smoothing out daily volatility.
* **Fare & Distance:** Investigated the relationship between `Distance_km` and `Fare` using a scatter plot and analyzed the overall `Fare` distribution with a box plot.
* **Passenger Behavior:** Visualized the distribution of `Passengers` per trip (Histogram) and the market share of different `Ticket_Type`s (Pie Chart).

**Final Output:**
The project concludes by saving the fully cleaned and engineered data into a new CSV file (`delhi_metro_cleaned_Dataset.csv`) for further use.

### Technologies Used
* **Python**
* **Pandas:** For data loading, cleaning, manipulation, and feature engineering.
* **NumPy:** For numerical operations and handling NaN values.
* **Matplotlib & Seaborn:** For a wide range of static visualizations, including bar charts, pie charts, histograms, scatter plots, and line charts.
