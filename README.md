markdown
Copy code
# Sentiment Analysis Application

This repository contains a simple sentiment analysis application built using Streamlit. The application allows users to enter a review and check its sentiment (positive or negative) using a pre-trained machine learning model.

## Features

- User input for review text.
- Real-time sentiment prediction.
- Simple and interactive web interface built with Streamlit.

## Requirements

- Python 3.x
- Streamlit
- pandas
- scikit-learn
- pickle

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/machphy/sentiment-analysis-
   
   cd sentiment-analysis
Create a virtual environment and activate it:

bash
Copy code
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
Install the required packages:

bash
Copy code
pip install -r requirements.txt
Place the model.pkl and scaler.pkl files in the project directory. These files should contain the pre-trained model and scaler, respectively.

Usage
Run the Streamlit application:

bash
Copy code
streamlit run app.py
Open your web browser and navigate to http://localhost:8501 to interact with the application.

Project Structure
app.py: Main application file containing the Streamlit app code.
model.pkl: Pre-trained machine learning model.
scaler.pkl: Scaler used for preprocessing the input data.
requirements.txt: List of required Python packages.
Example Code
Here is the main code for the Streamlit application (app.py):

python
Copy code
import pandas as pd 
import pickle as pk
from sklearn.feature_extraction.text import TfidfVectorizer
import streamlit as st

# Load the pre-trained model and scaler
model = pk.load(open('model.pkl', 'rb'))
scaler = pk.load(open('scaler.pkl', 'rb'))

# Streamlit app
st.title('Sentiment Analysis Application')

# User input
rajeev = st.text_input('Enter and check sentiment')

if st.button('Predict'):
    review_scale = scaler.transform([rajeev]).toarray()
    result = model.predict(review_scale)
    if result[0] == 0:
        st.write('Negative Review')
    else:
        st.write('Positive Review')
License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgments
Streamlit
scikit-learn
pandas
javascript
Copy code

Make sure to include a `requirements.txt` file with the necessary dependencies. Here’s an example:

```text
streamlit
pandas
scikit-learn

rajeevsharma2024
