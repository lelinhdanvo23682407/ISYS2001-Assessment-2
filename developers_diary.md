# Developer Diary - Household Fair-Share Budget Assistant

## 12 October 2026 - Core Python Development and Testing

### Work Completed 
- Defined the problem, target users, inputs, outputs, and calculation rules.
- Designed the algorithm and worked through a manual example.
- Implemented Python functions for input validation, income proportions, expense allocation, total verification, and result display.
- Used programming concepts practised in ISYS2001, including functions, loops, dictionaries, conditional statements, and error handling.
- Tested the calculator using 17 test cases. All 17 tests passed.

### Challenges and Solutions
My initial implementation included Python methods that I could not confirm were covered in the course materials. I reviewed my ISYS2001 notebooks and revised the code to use familiar programming concepts.

Another challenge was handling monetary rounding. I converted monetary values into integer cents and used integer arithmetic to allocate expenses while ensuring the individual contributions matched the total expenses.

### AI Assistance
I used ChatGPT to help review the algorithm, explain programming concepts, identify possible errors, and develop test cases. I compared the suggested code with my ISYS2001 learning materials and tested the revised implementation in Google Colab.

### Reflection
This stage improved my understanding of modular programming, input validation, and software testing. Although all 17 tests passed, additional testing will be required when the user interface and Gemini API are implemented.

### Evidence
![Screenshot 1](additional_tests.png/Screenshot%202026-10-12%20225258.png)

![Screenshot 2](additional_tests.png/Screenshot%202026-10-12%20225355.png)

![Screenshot 3](additional_tests.png/Screenshot%202026-10-12%20225417.png)

![Screenshot 4](additional_tests.png/Screenshot%202026-10-12%20230054.png)

## 15 October 2026 - Gradio Interface Implementation and Testing

### Work Completed

- Developed a Gradio user interface for the Household Fair-Share Budget Assistant.
- Created input fields for two individuals' names, monthly take-home incomes, and three predefined expenses: rent, electricity, and internet.
- Connected the Calculate Contributions button to the existing Python calculation functions.
- Successfully displayed the income proportions, individual expense allocations, and monthly contribution totals.

### Testing

Four interface scenarios were tested:

1. Normal calculation using the 60/40 income example.
2. Negative monthly income.
3. Zero combined monthly income.
4. Empty person name.

All four tests produced the expected results. Invalid inputs displayed error messages without crashing the interface.

### Challenges and Solutions

During development, the program initially raised a `NameError` because the core Python functions had not been executed in the current Google Colab runtime. I resolved this by running the function-definition cells before the Gradio interface.

### AI Assistance

I used ChatGPT to help connect the Gradio interface to the existing Python functions, understand the event handler, troubleshoot the `NameError`, and develop interface test scenarios. I ran the tests in Google Colab and checked the results.

### Reflection

This stage helped me understand how a Python application can be connected to an interactive interface. It also demonstrated the importance of input validation and testing both successful and invalid inputs.

### Evidence

Screenshots of the normal calculation and three invalid-input test scenarios are stored in the repository's testing evidence folder.
### Evidence

The following screenshots provide evidence of the Gradio interface testing:

1. [Gradio Test 1 — Normal Calculation](New%20folder/Screenshot%202026-10-15%20124704.png)
2. [Gradio Test 2 — Negative Income](New%20folder/Screenshot%202026-10-15%20125252.png)
3. [Gradio Test 3 — Zero Combined Income](New%20folder/Screenshot%202026-10-15%20125407.png)
4. [Gradio Test 4 — Empty Name](New%20folder/Screenshot%202026-10-15%20125449.png)

All four tests produced the expected results. The screenshots demonstrate successful calculation, input validation, and error handling.

## 15 October 2026 - Gemini API Integration and Testing

### Work Completed

- Integrated the Gemini API into the Household Fair-Share Budget Assistant using the `google-genai` Python library.
- Stored the API key securely using Google Colab Secrets instead of hardcoding it into the notebook.
- Developed the `explain_budget_with_ai()` function to generate explanations of the household expense-sharing results.
- Created `calculate_budget_with_ai()` to connect the existing Python calculations with Gemini.
- Updated the Gradio interface to display both the financial calculations and AI-generated explanations.
- Configured automatic API retries following the lecturer's guidance.

### Testing and Results

The application was tested using the following scenario:

- Person A's monthly income: AUD 3,000
- Person B's monthly income: AUD 2,000
- Rent: AUD 1,200
- Electricity: AUD 200
- Internet: AUD 100

Python calculated an income-based split of 60% for Person A and 40% for Person B, with total monthly contributions of AUD 900 and AUD 600 respectively.

Gemini successfully generated an explanation using these results. The AI explanation was also displayed within the Gradio interface.

### Challenges and Solutions

During integration, an initial API request failed because the selected Gemini model was unavailable to new users. I resolved this by switching to an available model.

I subsequently encountered a `503 UNAVAILABLE` error caused by high demand on Google's servers. Following the lecturer's guidance, I added automatic retry settings to the API client.

I also retained exception handling so that the application could continue displaying Python-calculated financial results when the Gemini API was unavailable.

### AI Assistance

I used ChatGPT to help understand the Gemini API integration process, develop the explanation function, troubleshoot API errors, configure retry handling, and connect the AI functionality to Gradio.

I executed the code in Google Colab, tested the integration, and checked the AI-generated figures against the Python calculation results.

### Reflection

This stage helped me understand how an external AI API can be integrated into a Python application. I learned that API availability cannot always be guaranteed and that error handling is important for application reliability.

Separating Python calculations from AI-generated explanations also helped ensure that the application's financial results did not depend on the AI service.

### Evidence

Screenshots were captured showing the Gemini API response, the `503 UNAVAILABLE` error, and the successful AI explanation displayed in Gradio.
