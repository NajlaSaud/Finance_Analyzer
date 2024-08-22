# Finance_Analyzer

## Overview
This project leverages OpenAI's GPT-3.5 model to analyze financial data from an Excel file. This script is designed to interact with OpenAI's GPT model (specifically `gpt-3.5-turbo`) to analyze financial data stored in the Excel file (`finance_data.xlsx`). The script performs the following tasks:

1. **Summarizes the contents** of the provided financial data file.
2. **Forecasts the expected income** for the second quarter of 2023 based on the historical financial data.

## Prerequisites

### Python Libraries

Before running the script, ensure you have the following Python libraries installed:

- `openai`: For interacting with OpenAI's API.
- `pandas`: For handling and manipulating Excel data.

You can install these libraries using `pip`:

```bash
pip install openai pandas
```

### OpenAI API Key

The script requires an OpenAI API key to function. You need to set this API key as an environment variable:

```bash
export OPENAI_API_KEY="your_api_key_here"
```

Alternatively, you can replace the placeholder `"YOUR_API_KEY_HERE"` directly in the script with your actual API key.


### Sample Output
```Python
prompt = f"""
Give me a summary for the file below:

File: '''{data_file}'''
"""
response = get_completion(prompt)
print(response)
```

```plaintext
The file contains data on income for each month of the year. The table has three columns: year, month, and income. The income values are provided for the months of January to December, with the corresponding year indicated in the first column. The income values are given in numerical format. The table has a total of 276 rows.
```

```Python
year = 2023
quarter = 2
prompt = f"""
Based on the financial data in file below,
What will be the income in the second quarter 2023.

Forecast the provided data for the previuous quarters.
Then, predict the expected income for the quarter: {quarter} in {year}.

Format your answer as follow:
The expected income = predicted_income_here

File: '''{data_file}'''
"""
response = get_completion(prompt)
print(response)
```

```plaintext
To forecast the income for the previous quarters, we can use a time series forecasting method such as linear regression or exponential smoothing. However, since we don't have any historical data or trend information, we will assume that the income for each month in the previous quarters is the same as the income in the corresponding month of the previous year.

Using this assumption, we can calculate the expected income for the previous quarters as follows:

- First quarter 2022: 44361.625074
- Second quarter 2022: 12106.134700
- Third quarter 2022: 31767.138947
- Fourth quarter 2022: 35704.493935
- First quarter 2023: 38463.495879

To predict the expected income for the second quarter 2023, we will assume that the income in the second quarter of 2023 will be the same as the income in the second quarter of 2022. Therefore, the expected income for the second quarter 2023 is:

The expected income = 12106.134700
```

## Customization

- **Model Selection**: You can change the GPT model used by modifying the `model` parameter in the `get_completion` function.

- **Temperature Parameter**: The `temperature` parameter controls the randomness of the model's output. It is currently set to `0` for deterministic results but can be adjusted according to your needs.

- **Year and Quarter Variables**: You can change the values of `year` and `quarter` variables to test the output for another quarter and year.


## License

This project is licensed under the MIT License. See the LICENSE file for more details.
