# Dividend Scout Application

A web application for tracking and displaying dividend stock information.

## Files

- `dividend-scout.html` - Frontend HTML page with search and display
  functionality
- `dividend-api.js` - Node.js backend API server
- `dividend-data.csv` - CSV data file with stock information
- `dividend-data.xlsx` - Excel data file with stock information (optional)
- `package.json` - Node.js dependencies

## Features

- Search for dividend stocks by symbol
- Display comprehensive dividend information
- Payment schedule details
- Support for both CSV and Excel data sources

## Setup

1. Install dependencies:

```bash
npm install
```

2. Prepare your data file:
   - **Option 1 (Excel)**: Create `dividend-data.xlsx` with the following
     columns:
     - Symbol
     - Company Name
     - Industry
     - Market Cap
     - Stock Price
     - PE
     - Div. Yield
     - Annual Payout
     - Payout Ratio
     - Payout Ratio Status
     - Growth Streak (Years)
     - Payment Frequency
     - Ex-Dividend Date
     - Next Payment Date
     - Record Date
     - Payment Amount
     - Annual Yield
     - Last Increase Date
     - 5-Year Growth (%)
     - Dividend King Status
     - Company Description

   - **Option 2 (CSV)**: Use the existing `dividend-data.csv` format

3. Start the API server:

```bash
npm start
```

4. Open `dividend-scout.html` in your browser

## API Endpoints

- `GET /api/dividend/:symbol` - Get dividend data for a specific stock
- `GET /api/stocks` - List all available stocks
- `POST /api/reload` - Reload data from Excel/CSV file
- `GET /health` - Health check

## Data Source Priority

The API will automatically use:

1. Excel file (`dividend-data.xlsx`) if it exists
2. Fall back to CSV file (`dividend-data.csv`) if Excel doesn't exist
3. Use mock data in frontend if API is not available

## Notes

- The frontend includes mock data so it can work without the backend
- Update your data file and call `/api/reload` to refresh without restarting the
  server
- Excel files are recommended for easier data management in spreadsheet
  applications
