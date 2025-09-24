# 🚗 Car Price Predictor

This project is a **Machine Learning web application** that predicts the price of a used car based on its **company, model, year, fuel type, and kilometers driven**. It combines data cleaning, a Linear Regression model, and a Flask web app with a simple Bootstrap frontend.

---

## 📂 Project Structure

- ├── application.py              # Flask web application
- ├── quikr_car.csv               # Raw dataset
- ├── Cleaned Car.csv             # Cleaned dataset
- ├── LinearRegressionModel.pkl   # Trained ML model
- ├── car_price_prediction.ipynb  # Jupyter Notebook for cleaning & training
- ├── templates/
- │   └── index.html              # Frontend (HTML + Jinja2)
- └── static/
- └── css/
- └── style.css           # Custom styles
- ├── Screenshot-Web.png          # Screenshot of the application
- ├── README.md         # Project documentation

---

## ⚙️ Tech Stack

-   **Python**
    -   `pandas`, `numpy`
    -   `scikit-learn`
    -   `pickle`
    -   `Flask`
-   **Frontend**
    -   HTML, CSS, Bootstrap
    -   JavaScript (AJAX for predictions)

---

## 🧹 Data Cleaning (in Jupyter Notebook)

The raw dataset (`quikr_car.csv`) contained messy and inconsistent values. The following steps were performed:

1.  **Removed invalid entries** like "Ask For Price", `NaN` values, and non-numeric year formats.
2.  **Converted** the `year`, `Price`, and `kms_driven` columns into integer data types.
3.  **Standardized car names** by keeping only the first 3 words.
4.  **Filtered out extreme price outliers** to improve model accuracy.
5.  **Exported the processed data** to `Cleaned Car.csv`.

---

## 🤖 Model Training

-   **Algorithm**: **Linear Regression**
-   **Features**: `name`, `company`, `year`, `kms_driven`, `fuel_type`
-   Used **OneHotEncoding** to handle categorical features.
-   Performed a train/test split and iterated through random states to maximize the **R² score**.
-   Saved the final trained pipeline as `LinearRegressionModel.pkl`.

---

## 🌐 Web Application

-   **Flask backend** loads the pre-trained model and the cleaned dataset to populate dropdowns.
-   **Frontend**:
    -   The user selects the car's company, model, year, and fuel type.
    -   The user enters the kilometers driven.
    -   An **AJAX** request sends the data to the backend, which returns a prediction that is instantly displayed on the page.
-   The prediction result (in Indian Rupees) is converted to **USD** for the final display.

---

## 🚀 How to Run Locally

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YoussefKamm/car-price-prediction.git](https://github.com/YoussefKamm/car-price-prediction.git)
    cd car-price-prediction
    ```

2.  **Create a virtual environment & install dependencies:**
    *(You will need to install Flask, pandas, numpy, and scikit-learn)*
    ```bash
    # Create the environment
    python -m venv .venv

    # Activate the environment
    source .venv/bin/activate      # On Linux/Mac
    .\venv\Scripts\activate      # On Windows

    # Install necessary packages
    pip install Flask pandas numpy scikit-learn
    ```

3.  **Run the Flask app:**
    ```bash
    python application.py
    ```

4.  **Open in your browser:**
    `http://127.0.0.1:5000/`

---

## 📸 Screenshot

The image below shows the web application's user interface with an example price prediction.(a 2016 Nissan Micra with 20,000 km driven.)


![image](https://github.com/YoussefKamm/Car-Price-Predictor/blob/main/Screenshot-Web.png)


---

## 📌 Future Improvements

-   Use more advanced ML models (Random Forest, XGBoost) for potentially higher accuracy.
-   Deploy the application to a cloud service like Render or AWS.
-   Incorporate more features into the model (e.g., transmission type, engine size).
-   Enhance the user interface with a more modern design or a dashboard.

---

## 📧 Contact

**Youssef Kammoun**

-   **Email**: `kammoun.youssef@outlook.com`
-   **LinkedIn**: `linkedin.com/in/your-profile`
