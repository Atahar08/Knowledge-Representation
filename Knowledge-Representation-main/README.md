# Knowledge-Representation

## Clue-Style Logical Reasoning Game in Python

This project uses propositional logic to illustrate a logical deduction game in the vein of *Clue*. It models and solves the game using ideas from logical reasoning and AI knowledge representation. To represent symbols and words, the program uses a bespoke `logic.py` module. It then makes logical deductions to ascertain the game's potential outcomes.

## Table of Contents
- [Overview](#overview)
- [Installation](#installation)
- [How It Works](#how-it-works)
- [Code Structure](#code-structure)
- [Examples](#examples)
- [Future Work](#future-work)
- [License](#license)

---

## Overview
The AI must determine which character committed the act, where the crime occurred, and what weapon was used in this project's model of a straightforward *Clue*-style game.


Propositional logic is used to represent the facts and game rules, enabling the AI to draw conclusions and solve the challenge. Beyond this example, the project can be expanded to tackle other logic-based challenges.


---

## Installation
1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Install required packages**:
   ```bash
   pip install termcolor
   ```

3. **Run the game**:
   ```bash
   python main.py
   ```

---

## How It Works
1. **Knowledge Representation**: Characters, rooms, and weapons are all defined as symbols in the game using propositional logic. Facts and game rules are represented by logical statements.
2. **Logical Reasoning**: The `model_check` function determines if certain queries are present in the knowledge base. It checks for logical entailment in every potential model using a brute-force method.
3. **Constraints and Inference**:In order to solve the problem, the program makes deductions and makes sure that all game rules are followed.

### Key Concepts
- **Symbols**: Represent game elements (e.g., Colonel Mustard, Kitchen, Knife).
- **Sentences**: Logical expressions formed using symbols and logical operators (`And`, `Or`, `Not`, etc.).
- **Model Checking**: A method to verify if the knowledge base implies the query, used to make logical inferences.

---

## Code Structure
- `main.py`: The main script that sets up the game and performs logical reasoning.
- `logic.py`: Contains classes for representing logical symbols and sentences, including operations like `And`, `Or`, `Not`, `Implication`, and `Biconditional`.
- `README.md`: Documentation for the project.

---

## Examples
Here are some examples of how the game logic is set up:
1. **Defining Symbols**:
   ```python
   mustard = Symbol("ColMustard")
   kitchen = Symbol("kitchen")
   knife = Symbol("knife")
   ```

2. **Constructing the Knowledge Base**:
   ```python
   knowledge = And(
       Or(mustard, plum, scarlet),  # At least one character is involved
       Or(ballroom, kitchen, library),  # At least one room is involved
       Or(knife, revolver, wrench)  # At least one weapon is involved
   )
   ```

3. **Adding Constraints**:
   ```python
   knowledge.add(Not(mustard))
   knowledge.add(Not(kitchen))
   knowledge.add(Not(revolver))
   ```

4. **Checking Knowledge**:
   ```python
   check_knowledge(knowledge)
   ```

---

## Future Work
- Expand the game to include more characters, rooms, and weapons.
- Implement optimization techniques for the model checking process.
- Create a graphical user interface (GUI) for an improved user experience.
- Integrate more complex logical puzzles and scenarios.
