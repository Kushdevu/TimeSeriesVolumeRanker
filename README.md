The project, named "TimeSeriesVolumeRanker," involves processing time-series data from the SBI stock, specifically focusing on the stock's open, high, low, close, and volume data recorded every minute of the trading session from January 1st to January 31st, 2024. Each trading day accounts for 375 rows of data, covering the market hours from 9:15 AM to 3:29 PM.

### Objective:
The primary goal is to analyze the minute-wise volume data across the specified period, ranking the trading volumes at the same minute across the last five trading days. This ranking is meant to highlight volume trends at specific times, with a rank of 1 indicating the highest trading volume among the compared days.

### Methodology:
1. **Data Preparation**: The process begins with the consolidation of the date and time information into a singular DateTime index for easier manipulation and analysis. This step ensures that the data can be efficiently filtered and grouped based on specific time intervals.

2. **Volume Ranking**: For a given minute on a specific day (e.g., 9:30 AM on January 31st), the trading volume is compared against the volumes at the same minute on the previous four trading days plus the current day, making a total of five days. These volumes are then ranked from highest (rank 1) to lowest, with the rank for each minute's volume stored in a new column within the DataFrame.

3. **Result Storage**: The output, a modified version of the original DataFrame now including the volume ranks, is stored as a new column named "Rank." This enriched dataset provides a detailed view of how trading volumes at specific times compare across different days, offering insights into trading patterns or anomalies.

### Final Steps:
The enriched dataset is then compressed into a ZIP file named `sbi_stock_data_with_volume_ranks_jan_2024.zip` for efficient storage and distribution. The original CSV file is removed after compression to save space and avoid redundancy.

### Usage:
This project serves multiple purposes, such as identifying potential patterns or anomalies in trading volumes at specific times, aiding in the analysis of market behavior, and supporting decision-making processes for traders, analysts, and financial institutions. The compression and cleanup steps ensure that the data is manageable and easily shared or archived, reflecting best practices in data management.
