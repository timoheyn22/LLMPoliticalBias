# LLM-Political-Bias

This is a Python-based application that sends API request to difrent LLMs asking them the Questions from the Political Compass Test and saving the Respones in an Excel File. 

## Setup
1. Ensure you have the necessary packages installed. Run the following command:

```bash
pip install -r requirements.txt
```

2. Create a .env File
Create a .env file in the project directory and add your API key and base URL:
```API_KEY=your-api-key
BASE_URL=https://your-openai-api-endpoint
```

## How It Works:
✅ Load Questions:
The script reads questions from an Excel file.

✅ Ask LLM:
Sends each question to the LLM using OpenAI’s API.
Collects multiple responses for statistical significance.

✅ Clean Responses:
Cleans responses by removing unnecessary text using regex.

✅ Update Excel:
Records responses and updates statistical data:
Count of each response type
Mean (average)
Mode (most frequent)
Min and Max values

✅ Bootstrap:
Uses bootstrapping to generate synthetic responses for more robust statistics.


## Configuration  
You can adjust the following parameters to customize the behavior:

| Parameter            | Description                                  | Example Value                                               |
|---------------------|----------------------------------------------|------------------------------------------------------------|
| `model`              | LLM model to use                             | `"deepseek-r1-distill-llama-70b"`                           |
| `repetitions`         | Number of times to ask each question          | `10`                                                       |
| `boot_repetitions`    | Number of synthetic samples to generate       | `90`                                                       |
| `language`            | Language of questions and answers             | `"English"`, `"Chinese"`, `"Russian"`                       |
| `questionTemplatePath` | Path to the Excel file with questions          | `"Excel Files/QuestionTemplates/englishCompass.xlsx"`        |
| `outputPath`          | Path to store the output file                 | `"Excel Files/Results/DeepSeekEnglish10.xlsx"`              |
| `bootStrapPath`       | Path to store bootstrapped data               | `"Excel Files/BootStrap/DeepSeekEnglishBoot100.xlsx"`        |


## Excel Files and Results

QuestionTemplates: The template Excel sheets containing the political Compass test questions and the weights to calculate the political values

Results: The results of all 62 Questions asked 10 times for each LLM in each langauge 

BootStrap: The values of the result bootstrapped to 100 answers 

FilledIn: All missing values from invalid answers filled in, completing the results 

