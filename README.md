# Credit Risk Modelling Framework

## Overview
This framework calculates credit risk metrics, including probabilities of default (PD) using multiple models, and prices financial instruments like risky bonds and credit default swaps (CDS). It supports the following default probability models:
- **Merton Model**: Structural approach based on a firm's asset and debt structure.
- **Hull-White Model**: Intensity-based approach.
- **Machine Learning Model**: A random forest classifier trained on features.

---

## Key Features
1. **Default Probability Models**:
   - Merton, Hull-White, or ML models can be selected via the `CONFIG` file.
2. **Pricing**:
   - **Risky Bond**: Incorporates default probabilities and recovery rates.
   - **Credit Default Swap (CDS)**: Calculates the CDS spread.
3. **Input Validation**:
   - Ensures data integrity with predefined column requirements.

---

## Project Structure
- **main.py**: Entry point to validate inputs, calculate default probabilities, and price financial instruments.
- **utils.py**: Core utility functions for calculating probabilities and pricing.
- **config.py**: Centralized configuration for model selection and parameters.

---

## Usage

1. **Input Data**:
   Prepare input data as a DataFrame with the following columns:
   - `Equity_Value`: Value of the firm’s equity.
   - `Debt_Value`: Firm’s debt obligations.
   - `Volatility`: Volatility of the firm’s equity value.
   - `Risk_Free_Rate`: Current risk-free interest rate.
   - `Feature1`, `Feature2`: Example features for the ML model.

2. **Configuration**:
   Update the `config.py` file to specify parameters:
   ```python
   CONFIG = {
       'time_horizon': 1,  # Time horizon in years
       'hull_white_lambda_0': 0.02,  # Initial intensity for Hull-White model
       'hull_white_sigma': 0.1,  # Volatility of intensity in Hull-White model
       'random_seed': 42,  # Random seed for reproducibility in ML model
       'default_probability_model': 'Merton'  # Default probability model: 'Merton', 'Hull-White', 'ML'
   }
