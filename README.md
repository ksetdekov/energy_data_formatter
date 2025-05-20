# Energy_data_formatter

Format data for use with https://re.jrc.ec.europa.eu/pvg_tools/en/tools.html

This project analyzes and normalizes power consumption data from a meter, comparing it to a reference example from the JRC PVGIS tool. The workflow is implemented in a Jupyter Notebook (`power_cons_norm.ipynb`) using Python and common data science libraries.

## Files

- `power_cons_norm.ipynb`: Main notebook for data processing, analysis, and visualization.
- `power_meter_xavier_average_1_hour.txt`: Raw power meter data (space-separated, with columns for power and time).
- `hourconsumption_norm.csv`: Reference example data for normalized hourly consumption (single column: ratio).
- `normalized_power.csv`: Output file containing the calculated normalized power values (single column, no header).
- `requirements.txt`: List of required Python packages.

## Workflow Overview

1. **Import Libraries**: Uses `pandas`, `numpy`, and `matplotlib` for data manipulation and plotting.
2. **Load Example Data**: Reads `hourconsumption_norm.csv` as a reference for normalized hourly consumption.
3. **Read Meter Data**: Loads and parses the power meter data from `power_meter_xavier_average_1_hour.txt`.
4. **Preprocessing**: Converts time strings to datetime objects for analysis.
5. **Visualization**: Plots the raw power consumption over time.
6. **Hourly Averaging**: Calculates the average power consumption for each hour of the day.
7. **Normalization**: Computes normalized power by dividing each hourly average by the total sum.
8. **Export**: Writes the normalized power data to `normalized_power.csv` in the same structure as the example.
9. **Comparison Plot**: Plots both the calculated normalized power and the example data for visual comparison.

## Usage

1. Place your raw meter data in `power_meter_xavier_average_1_hour.txt` and the reference in `hourconsumption_norm.csv`.
2. Open and run the cells in `power_cons_norm.ipynb`.
3. The notebook will generate plots and output the normalized data to `normalized_power.csv`.

## Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
```

## Notes

- Ensure the input files are formatted as expected (see above).
- The notebook is designed for exploratory analysis and can be adapted for other datasets with similar structure.
- Used to interact with <https://re.jrc.ec.europa.eu/pvg_tools/en/tools.html#api_5.3> to get the normalized power consumption data for more accurate results of solar panels calculation.
