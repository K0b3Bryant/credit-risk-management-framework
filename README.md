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

