# Household Fair-Share Budget Assistant

## 1. Project Overview

The Household Fair-Share Budget Assistant is a Python application that helps two people divide shared monthly household expenses proportionally based on their take-home incomes.

The application uses Python to calculate financial contributions and the Gemini API to explain the results in simple English. A Gradio interface allows users to enter their financial information and view the results.

## 2. Problem Statement

Splitting household expenses equally may place a greater financial burden on a person with a lower income. This application provides an alternative by calculating each person's contribution according to their proportion of the combined household income.

## 3. Main Features

- Accepts two people's names and monthly take-home incomes in AUD.
- Accepts three predefined monthly expenses: rent, electricity and internet.
- Calculates each person's income proportion.
- Allocates shared expenses proportionally using Python.
- Displays an expense breakdown and monthly contribution totals.
- Uses Gemini AI to explain the calculated results.
- Validates user inputs and displays error messages.
- Handles Gemini API failures without preventing Python calculations.

## 4. Technologies Used

- Python — financial calculations, input validation and error handling.
- Google Colab — development and execution environment.
- Gradio — interactive user interface.
- Google Gemini API (`google-genai`) — AI-generated explanations.
- GitHub — version control, documentation and testing evidence.

## 5. Installation and Setup

1. Open `household_budget_assistant.ipynb` in Google Colab.
2. Install the required libraries by running:

   `!pip install -q gradio google-genai`

3. Create a Gemini API key using Google AI Studio.
4. In Google Colab, open **Secrets** and create a secret named `GEMINI_API_KEY`.
5. Paste the API key into the secret value and enable notebook access.
6. Run the notebook cells in order to define the Python functions, configure the Gemini API client and launch the Gradio interface.

**Security:** The API key must not be written directly into the notebook or committed to GitHub.

## 6. How to Use the Application

1. Launch the Gradio interface from Google Colab.
2. Enter Person A's and Person B's names.
3. Enter both monthly take-home incomes in AUD.
4. Enter the monthly rent, electricity and internet expenses.
5. Click **Calculate Contributions**.
6. Review the income proportions, expense breakdown, monthly totals and AI explanation.

## 7. Example Calculation

| Item | Person A | Person B |
|---|---:|---:|
| Monthly income | AUD 3,000 | AUD 2,000 |
| Income proportion | 60% | 40% |
| Rent contribution | AUD 720 | AUD 480 |
| Electricity contribution | AUD 120 | AUD 80 |
| Internet contribution | AUD 60 | AUD 40 |
| Total contribution | AUD 900 | AUD 600 |

Combined monthly income: **AUD 5,000**

Total shared monthly expenses: **AUD 1,500**

Python performs the financial calculations. Gemini explains the results rather than determining the contribution amounts.

## 8. Testing

The core Python functions were tested using 17 test cases during development.

The Gradio interface was manually tested with four scenarios:

- Normal proportional calculation.
- Negative monthly income.
- Zero combined income.
- Empty person name.

Gemini integration was also tested. The application successfully displayed an AI-generated explanation in Gradio. During development, a `503 UNAVAILABLE` API error was encountered, and retry configuration and exception handling were used to improve reliability.

Testing screenshots and further development details are available in `developers_diary.md` and the repository's evidence files.

## 9. Limitations

- Supports two people only.
- Uses three predefined expense categories rather than allowing users to add custom categories.
- Assumes both incomes and expenses are entered as monthly AUD amounts.
- Does not store financial data between sessions.
- Gemini explanations require an internet connection and an available API service.
- AI-generated explanations may occasionally contain inaccuracies; Python-calculated results should be treated as authoritative.
- The application is a budgeting aid, not professional financial advice.

## 10. Project Files

- `household_budget_assistant.ipynb` — Python application, tests, Gemini integration and Gradio interface.
- `README.md` — project overview and instructions.
- `developers_diary.md` — development progress, challenges, AI assistance and reflection.
- Testing screenshots — evidence of program functionality and error handling.

## 11. AI Assistance Declaration

ChatGPT was used as a development support tool for understanding Python concepts, troubleshooting errors, discussing testing scenarios, and assisting with documentation.

Google Gemini was integrated into the application to generate natural-language explanations of financial calculations.

The application was implemented and tested in Google Colab, with development progress and AI assistance documented in the Developer Diary.
