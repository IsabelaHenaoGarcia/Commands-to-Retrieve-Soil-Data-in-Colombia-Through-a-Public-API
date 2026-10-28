# Colombia Soil Data Retrieval Tool

A Python application that retrieves, processes, and displays open-source soil data across different municipalities and departments in Colombia using Socrata Open Data API (SODA).

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Modules](#modules)
- [License](#license)

## Overview

This project connects to Colombia's public open data portal (`datos.gov.co`) to query soil data collected by AGROSAVIA (Instituto Colombiano Agropecuario). Users can specify a department, municipality, crop type, and record limit to analyze soil characteristics such as pH, organic matter, phosphorus, and other chemical components.

## Features

- **Public API Integration:** Queries live soil dataset records using `sodapy`.
- **Interactive UI Console:** Prompt-driven interface for seamless querying.
- **Statistical Analysis:** Calculates key statistical metrics (median, mean) for numerical attributes across retrieved samples.
- **Data Structuring:** Formats data cleanly using `pandas` DataFrames.

## Project Structure

```text
Commands-to-Retrieve-Soil-Data-in-Colombia-Through-a-Public-API/
│
├── API_modulo.py    # Handles API connection and data queries
├── UI_modulo.py     # Manages user interface, input validation, and output formatting
└── main.py          # Application entry point
```

## Prerequisites

- Python 3.8 or higher
- Access to an internet connection to fetch public API data

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/Commands-to-Retrieve-Soil-Data-in-Colombia-Through-a-Public-API.git
   cd Commands-to-Retrieve-Soil-Data-in-Colombia-Through-a-Public-API
   ```

2. **Create a virtual environment (optional but recommended):**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install required dependencies:**

   ```bash
   pip install sodapy pandas
   ```

## Usage

To launch the application, execute the `main.py` file:

```bash
python main.py
```

Follow the on-screen prompts:
1. Enter the department name (e.g., `CUNDINAMARCA`, `ANTIOQUIA`).
2. Enter the municipality name.
3. Enter the crop type.
4. Specify the maximum number of records to retrieve.

The application will query the open data portal and display tabular results along with summary statistics.

## Modules

- **`API_modulo.py`**: Contains functions responsible for establishing a connection with `datos.gov.co` using `sodapy.Socrata` and filtering datasets according to user input.
- **`UI_modulo.py`**: Handles console inputs/outputs, constructs formatted tables using `pandas`, and computes median values for soil properties.
- **`main.py`**: Coordinates the pipeline by calling the UI module to gather input, invoking the API module to fetch data, and rendering results.

## License

This project is open-source and available under the [MIT License](LICENSE).
