Infinity Data Downloader - README
This Python script provides functionalities to download and process data from an Oracle API.

Installation
This script requires the following Python libraries:

requests: Used to make API requests. Install with pip install requests.
pandas: Used for data manipulation. Install with pip install pandas.
datetime: Used for date manipulation. This library is part of the Python standard library.
Usage
1. Update Configuration
Replace OracleAPI_URL with the actual URL of your Oracle API endpoint.
This script expects the API to accept dates in the format YYYY-MM-DD. You can modify the date format logic in the validate_date function if needed.
2. Run the Script

Execute the script using Python:
Bash
python infinity_data_downloader.py

3. Optional: Command Line Arguments
You can optionally provide start and end dates as command-line arguments:
Bash
python infinity_data_downloader.py --start_date 2024-10-11 --end_date 2024-10-20

Functionality
The script performs the following steps:
1. Download Data:
Calls the download_data function with the API URL, output filename, and start/end dates.
Validates the provided dates.
Downloads data from the API in CSV format and saves it to a file with a timestamp.
2. Process Data:
Calls the processFile function with the downloaded data file and output filename.
3. Reads the downloaded CSV data using pandas.
Cleans the data by removing rows with missing values (NaN).
Extracts the URI and domain information from the "Destination URL" column.
Saves the processed data to a new CSV file with a descriptive name.
Output Files
4. The script generates two output files:

Raw Data File:
Named with a prefix InfinityData_ followed by the start date in YYYY-MM-DD format, an underscore, and "_raw.csv" extension.
Contains the unprocessed data downloaded from the API.
Processed Data File:
Named with the same prefix as the raw data file, but without the "_raw" extension.
Contains the cleaned and processed data with extracted information.