# Sales Dashboard Application

## Overview
This project is a Flask-based web application that serves a sales dashboard. It uses a SQLite database to store sales data from a CSV file (`HM-Sales-2018.csv`) and provides multiple API endpoints to fetch aggregated data for visualization purposes. The application uses Pandas and SQLAlchemy to interact with the database and render data in JSON format for front-end consumption.

## Features
- **Database Setup**: Reads sales data from a CSV file and stores it in a SQLite database (`demo.db`).
- **API Endpoints**:
  - `/`: Renders the main dashboard page (`index4.html`).
  - `/get-databar`: Returns total sales by sub-category for a bar chart.
  - `/get-datascatter`: Returns total profit by discount for a scatter chart.
  - `/get-datapie`: Returns total sales by category for a pie chart.
  - `/get-stackbar`: Returns total sales and profit by year and region for a stacked bar chart.
  - `/get-datastack`: Returns total sales by year, category, and customer ID for a bubble chart.
- **Technologies**:
  - Flask: Web framework for serving the application.
  - SQLite: Lightweight database for storing sales data.
  - Pandas: For data manipulation and CSV handling.
  - SQLAlchemy: For SQL query execution and database connection.

## Prerequisites
- Python 3.x
- Required Python packages:
  - `flask`
  - `pandas`
  - `sqlalchemy`
  - `sqlite3` (built-in with Python)

## Installation
1. Clone the repository or download the project files.
2. Install the required packages:
   ```bash
   pip install flask pandas sqlalchemy
   ```
3. Ensure the `HM-Sales-2018.csv` file is in the same directory as the `server4.py` script.
4. Run the application:
   ```bash
   python server4.py
   ```

## Usage
1. Start the Flask server by running `server4.py`. The application will be hosted at `http://127.0.0.1:5000` by default.
2. Open a web browser and navigate to `http://127.0.0.1:5000` to view the dashboard (`index4.html`).
3. The dashboard can fetch data from the API endpoints to display various charts:
   - Bar chart: `http://127.0.0.1:5000/get-databar`
   - Scatter chart: `http://127.0.0.1:5000/get-datascatter`
   - Pie chart: `http://127.0.0.1:5000/get-datapie`
   - Stacked bar chart: `http://127.0.0.1:5000/get-stackbar`
   - Bubble chart: `http://127.0.0.1:5000/get-datastack`

## File Structure
- `server4.py`: Main Flask application script that sets up the database, defines API endpoints, and serves the dashboard.
- `HM-Sales-2018.csv`: Input CSV file containing sales data.
- `index4.html`: Front-end HTML template for the dashboard (not included in the provided code but referenced in the Flask app).
- `demo.db`: SQLite database file (generated when the application runs).

## Notes
- The application runs in debug mode (`debug=True`) for development purposes. Disable this in production.
- Ensure the `HM-Sales-2018.csv` file is properly formatted with columns like `Sub-Category`, `Sales`, `Profit`, `Discount`, `Category`, `Year`, `Region`, and `CustomerID` for the SQL queries to work correctly.
- The front-end template (`index4.html`) is assumed to handle the JSON data returned by the API endpoints for rendering charts.

## Troubleshooting
- If the database connection fails, ensure the `demo.db` file is writable in the project directory.
- If the CSV file is missing or incorrectly formatted, the application may fail to load data. Verify the file's presence and structure.
- For issues with API endpoints, check the console logs for SQL query errors or Flask debug output.

## Future Improvements
- Add error handling for missing or malformed CSV files.
- Implement authentication for API endpoints.
- Enhance the front-end dashboard with interactive chart libraries (e.g., Chart.js or D3.js).
- Optimize database queries for large datasets.
