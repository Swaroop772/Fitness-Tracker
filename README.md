# Personal Fitness Tracker

This **Personal Fitness Tracker** is a Python-based application designed to track and predict fitness data, including exercise routines and calories burned. The application uses **Random Forest ** to make predictions based on user inputs and historical data stored in two databases: one for **calories** and the other for **exercise routines**.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Random Forest  Model](#Random-forest-Regression-Model)
- [Databases](#databases)
- [Contributors](#contributors)

---

## Overview

The **Personal Fitness Tracker** helps users stay on top of their fitness goals by offering the following features:

- **Exercise Routine Prediction**: Using a **Random Forest ** model to predict the best exercise routine based on the user's goals, fitness level, and preferences.
- **Calories Burned Prediction**: By analyzing previous workouts, the system predicts the estimated calories burned for different types of exercises.
- **Tracking Progress**: Users can input their exercise activities, and the system will keep track of their progress over time.
- **Streamlit UI**: A simple and interactive user interface built using **Streamlit** for easy interaction with the application.

## Features

- Track daily exercise routines and calories burned.
- Predict calories burned based on exercise type and user input using **Random Forest **.
- Generate workout plans and suggest exercises based on user goals.
- Store and retrieve fitness data using a database for calories and exercises.
- User-friendly interface using **Streamlit** for easy interaction and visualization.

## Technologies Used

- **Python**: Core language for implementing the logic.
- **Streamlit**: For building the web-based UI to interact with the system.
- **Pandas**: For data manipulation and analysis.
- **Scikit-learn**: For implementing the **Random Forest ** model.
- **SQLite/MySQL/PostgreSQL**: Databases to store exercise and calorie data.
- **Matplotlib**: For visualizing progress and statistics.

## Setup and Installation

Follow these steps to set up the **Personal Fitness Tracker** on your local machine:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/PersonalFitnessTracker.git
   cd PersonalFitnessTracker
   ```

2. **Install Required Packages:**
   You can install the required dependencies using `pip`. Make sure you have Python 3.6 or above installed.
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up the Database:**
   Depending on your choice of database (SQLite, MySQL, PostgreSQL), you will need to set up the databases to store exercise and calorie data.
   
   - For SQLite, simply create the database file.
   - For MySQL/PostgreSQL, configure the connection in the `config.py` file.

4. **Run the Application:**
   After installing the required packages and setting up the database, you can start the Streamlit UI by running the following command:
   ```bash
   streamlit run app.py
   ```

   This will launch the application in your browser where you can interact with the fitness tracker UI.

---

## Usage

1. **User Interaction (Streamlit UI):**
   The system uses **Streamlit** to create a simple user interface where users can input their fitness data (exercise routines, calories burned, goals, etc.) through an interactive form.

2. **Predicting Calories:**
   After entering an exercise routine, the system predicts the number of calories burned using a **Random Forest ** model. The predictions are based on user input such as:
   - Exercise type
   - Duration of exercise
   - Intensity level

3. **Exercise Suggestions:**
   The system can suggest exercises based on user preferences and goals (e.g., weight loss, muscle gain, or endurance improvement).

4. **Visualizing Progress:**
   Streamlit also provides visualizations (using **Matplotlib**) to help users track their progress over time, such as calories burned per week or exercises performed.

---

## Random forest Regression Model

The **Personal Fitness Tracker** uses ** Random Forest Regression** to predict the number of calories burned during exercise routines. Here's an overview of how the model works:

1. **Data Collection**: The exercise and calorie datasets are collected, which include features such as:
   - Exercise type (e.g., running, cycling, weight lifting)
   - Duration of the exercise (in minutes)
   - Intensity level (e.g., low, medium, high)
   - Calories burned during exercise

2. **Feature Engineering**: 
   - Features like exercise type, duration, and intensity are used as input to the model.
   - Additional features can be added for more detailed predictions, like user information (age, weight, etc.).

3. **Model Training**: 
   - We use **Random Forest ** to train the model on historical data of exercise and calories burned.
   - The target variable (calories burned) is predicted based on the input features (exercise type, intensity, and duration).

4. **Prediction**: 
   - The trained Random Forest  model is used to predict the calories burned based on user input during exercises.
   - The system provides an estimate of calories burned, helping users understand the impact of their workouts.

---

## Databases

Two key databases are used in the system:

1. **Calories Database**: Stores information about calories burned during different exercises. This data can be used to make predictions or track progress.
   - Structure: `exercise_name`, `calories_burned_per_minute`, `duration_minutes`, etc.
   
2. **Exercise Database**: Contains information about different types of exercises, including recommended exercises for various fitness goals.
   - Structure: `exercise_id`, `exercise_name`, `type`, `target_muscle`, `intensity_level`, etc.

Both databases are queried during the prediction phase to help users track and predict calories burned based on the exercise data.
