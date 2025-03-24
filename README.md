# IPL 2025 Unsold Players Data Analysis

## Overview
This project analyzes IPL match data to identify top-performing batsmen and bowlers who went unsold in the IPL 2025 auction. The analysis is performed using Apache Spark (PySpark) within a Databricks environment.

## Features
- **Batsman Statistics:** Calculates total runs, balls faced, strike rate, and boundaries (fours & sixes) for each batsman.
- **Bowler Statistics:** Computes wickets taken, economy rate, and runs conceded for each bowler.
- **Auction Analysis:** Identifies players who went unsold in the IPL 2025 auction.
- **Data Transformation:** Formats player names correctly using UDFs.
- **Top Performers Analysis:** Lists the top unsold batsmen and bowlers based on performance metrics.

## Technologies Used
- **Databricks**: For cloud-based data processing.
- **Apache Spark (PySpark)**: For large-scale data processing and transformation.
- **Python**: Used for data manipulation and analysis.

## Dataset
The project uses three CSV datasets:
1. `matches.csv` - Contains match details.
2. `deliveries.csv` - Ball-by-ball delivery data.
3. `ipl_2025_auction_players.csv` - List of players and their auction status.

## Data Processing Steps
1. **Load Data**: Reads CSV files into Spark DataFrames.
2. **Compute Batting Stats**:
   - Group by batsman to calculate runs, balls faced, strike rate, and boundaries.
   - Filter batsmen who have faced at least 50 balls.
3. **Compute Bowling Stats**:
   - Count valid wickets (excluding run outs) for each bowler.
   - Compute economy rate based on runs conceded and overs bowled.
4. **Format Player Names**:
   - Use UDFs to standardize player names.
   - Convert full names to initials-based format for consistency.
5. **Identify Unsold Players**:
   - Filter out players marked as "Unsold" in the auction dataset.
6. **Join Data**:
   - Merge unsold players with batting and bowling statistics.
7. **Display Top Performers**:
   - List top 10 unsold batsmen based on strike rate and boundaries.
   - List top 10 unsold bowlers based on wickets and economy rate.

## How to Run
1. Upload the datasets (`matches.csv`, `deliveries.csv`, `ipl_2025_auction_players.csv`) to Databricks.
2. Run the provided Databricks notebook in a PySpark environment.
3. Use `display()` commands to visualize top performers.

## Results
- Identifies underrated players who performed well but went unsold in the auction.
- Highlights top batsmen with high strike rates and boundary counts.
- Lists top bowlers with good wicket-taking ability and economy rates.
![Screenshot 2025-03-24 091603](https://github.com/user-attachments/assets/79b9e9a7-3692-4d00-9182-8ece10c2c690)
![Screenshot 2025-03-24 091638](https://github.com/user-attachments/assets/042d86d8-1f06-476c-995c-9083cd7cfeee)

## Future Enhancements
- Integrate real-time IPL data streaming using Kafka.
- Implement a machine learning model to predict future auction trends.
- Enhance data visualization using Power BI or Amazon QuickSight.

## Author
Chetan Sunku

