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
