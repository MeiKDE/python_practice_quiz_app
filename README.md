# Quiz Application

This project is a simple **Quiz Application** built using Python. The app allows users to answer a series of True/False questions in a graphical interface. It showcases concepts like OOP (Object-Oriented Programming), GUI development with Tkinter, and data handling.

---

## Features

- **Graphical User Interface**: Built using Tkinter, the app offers an interactive experience.
- **Dynamic Question Handling**: The quiz retrieves questions and displays them dynamically.
- **Score Tracking**: Keeps track of the user's score as they progress.
- **Feedback Mechanism**: Provides immediate feedback on whether an answer is correct or not.
- **Encapsulation and Reusability**: Organized into modular classes for better structure and maintainability.

---

## Project Structure

The project consists of the following modules:

### 1. `question_model.py`

Defines the `Question` class for encapsulating question text and answers.

```python
class Question:
    def __init__(self, q_text, q_answer):
        self.text = q_text
        self.answer = q_answer
```

### 2. `data.py`

Contains the `question_data`, a list of dictionaries representing questions and their answers.

```python
question_data = [
    {"question": "Sample Question 1", "correct_answer": "True"},
    {"question": "Sample Question 2", "correct_answer": "False"},
    # Add more questions here
]
```

### 3. `quiz_brain.py`

Handles the core logic of the quiz, such as tracking the current question, verifying answers, and scoring.

### 4. `ui.py`

Creates the graphical interface using Tkinter and integrates it with the `QuizBrain` logic.

---

## Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/your-repo/quiz-app.git
   cd quiz-app
   ```

2. **Install Dependencies**:
   Ensure you have Python 3.x installed.

   ```bash
   pip install -r requirements.txt
   ```

   *(Note: If there are no external dependencies, you can skip this step.)*

3. **Run the Application**:

   ```bash
   python main.py
   ```

---

## Usage

1. **Start the Quiz**: Run the application to see the first question displayed in the interface.
2. **Answer Questions**: Click the **True** or **False** button to answer.
3. **Track Progress**: The app will display your score after each question.
4. **Completion**: At the end of the quiz, you will see a summary of your final score.

---

## File Structure

```
quiz-app/
│
├── question_model.py  # Defines the Question class
├── data.py            # Contains quiz data
├── quiz_brain.py      # Core quiz logic
├── ui.py              # Graphical user interface
├── main.py            # Main application entry point
├── images/            # Contains True/False button images
└── README.md          # Project documentation
```

---

## Example Code

### Sample Initialization

```python
from question_model import Question
from data import question_data
from quiz_brain import QuizBrain
from ui import QuizInterface

question_bank = []
for question in question_data:
    question_text = question["question"]
    question_answer = question["correct_answer"]
    new_question = Question(question_text, question_answer)
    question_bank.append(new_question)

quiz = QuizBrain(question_bank)
quiz_ui = QuizInterface(quiz)
```
