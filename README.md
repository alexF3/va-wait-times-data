
# VA Facility Wait Times Data

Automated daily collection of VA facility wait time data from [Access to Care](https://www.accesstocare.va.gov/).
Drawing data from over 1,100 facilities for longitudinal analysis of delays in access to care

## Data Files

- **`archived_data.csv`** - Complete historical dataset of all wait times
- **`wait_time_summary.csv`** - Latest summary of wait time data

## Data Schema

| Column | Description |
|--------|-------------|
| `ReportDate` | Date of the report |
| `facility_id` | VA facility station number |
| `AppointmentType` | Type of appointment |
| `EstablishedPatients` | Wait time for established patients (days) |
| `NewPatients` | Wait time for new patients (days) |
| `VA Facility Location` | Facility name |
| `state` | State abbreviation |

## Update Schedule

Data is automatically updated daily at 9:00 AM UTC (4:00 AM EST).

**Last updated:** Check the commit history for the latest update timestamp.

## Data Source

All data is collected from publicly available VA facility performance data at:
https://www.accesstocare.va.gov/

## Usage
```python
import pandas as pd

# Load the data
df = pd.read_csv('https://raw.githubusercontent.com/alexF3/va-wait-times-data/main/archived_data.csv')

# Convert date column
df['ReportDate'] = pd.to_datetime(df['ReportDate'])

# Analyze
print(df.describe())
```

## License

Data is provided as-is from public VA sources. No warranty expressed or implied.

## Contact

For questions or issues, please open an issue in this repository.
