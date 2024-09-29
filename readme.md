Retail Query Assistant
This is a simple Streamlit application designed to act as a Retail Query Assistant. The app allows users to query predefined product-related information like top-selling, least-selling, overstocked, and understocked products. The data is simulated using a fake database for demonstration purposes.

Features
View Top-Selling Products: Lists the products with the highest sales.
View Least-Selling Products: Displays products with the lowest sales.
View Overstocked Products: Shows products with higher-than-threshold stock levels.
View Understocked Products: Shows products with lower-than-threshold stock levels.
Uses a JSON file (queries.json) to store predefined queries and their descriptions.
Getting Started
Prerequisites
Make sure you have the following installed on your local machine:

Python 3.7 or higher
Streamlit
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/jatin009v/Retail-Query-Assistant.git
Navigate to the project directory:

bash
Copy code
cd Retail-Query-Assistant
Install the required packages:

bash
Copy code
pip install -r requirements.txt
Running the App
Start the Streamlit application:

bash
Copy code
streamlit run app.py
Open your browser and go to http://localhost:8501/ to see the application.

Project Structure
plaintext
Copy code
Retail-Query-Assistant/
├── app.py                # Main Streamlit application file
├── queries.json          # JSON file containing predefined queries
├── requirements.txt      # List of dependencies
└── README.md             # Project documentation
Example queries.json
The queries.json file should have the following structure:

json
Copy code
{
  "top-selling products": {
    "sql": "SELECT product_name, SUM(quantity_sold) as total_sold FROM sales GROUP BY product_name ORDER BY total_sold DESC LIMIT 5;",
    "description": "Fetches the top 5 products with the highest total sales."
  },
  "least-selling products": {
    "sql": "SELECT product_name, SUM(quantity_sold) as total_sold FROM sales GROUP BY product_name ORDER BY total_sold ASC LIMIT 5;",
    "description": "Fetches the bottom 5 products with the lowest total sales."
  },
  "overstocked products": {
    "sql": "SELECT product_name, stock FROM inventory WHERE stock > threshold ORDER BY stock DESC;",
    "description": "Fetches products with stock levels above a predefined threshold."
  },
  "understocked products": {
    "sql": "SELECT product_name, stock FROM inventory WHERE stock < threshold ORDER BY stock ASC;",
    "description": "Fetches products with stock levels below a predefined threshold."
  }
}
Usage
Run the application and select or type in a predefined query.
The app will display a SQL query associated with your input and simulate results using a fake database.
Example queries include:
top-selling products
least-selling products
overstocked products
understocked products
License
This project is licensed under the MIT License.

Contributing
If you wish to contribute, please feel free to open an issue or create a pull request.

