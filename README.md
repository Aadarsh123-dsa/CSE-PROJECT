Brainstorm: MAT Skill Test
Brainstorm is a command-line quiz game built in Python. It tests your Mental Ability (MAT) with a series of 10 timed, multiple-choice questions. The game features a dynamic scoring system, a persistent leaderboard, and randomized questions/answers to ensure a unique experience every time.

✨ Features
Dynamic Quiz: Selects 10 random questions from a larger question bank for each session.

Randomized Options: The multiple-choice options are shuffled for every question to prevent memorization of answers by position (e.g., "A" or "1").

Timed Responses: Each question has a 60-second time limit. Failing to answer in time forfeits the question.

Bonus Scoring:

+10 points for a correct answer.

+5 bonus points for a "Fast Answer" (under 10 seconds).

Persistent Leaderboard: All scores are saved to leaderboard.txt. The game displays the Top 5 all-time scores after each session.

Performance Report: At the end of the quiz, you get a detailed, question-by-question breakdown of your performance, including your answer status (Correct, Wrong, Timeout), time taken, and points earned.

🚀 How to Run
Prerequisites: Ensure you have Python 3 installed on your system.

Save the File: Save the provided code as quiz_game.py.

Run from Terminal: Open your terminal or command prompt, navigate to the directory where you saved the file, and run the following command:

Bash

python quiz_game.py
Play: Follow the on-screen prompts. You will be asked for your name, and then the quiz will begin after you press ENTER.

⚙ How It Works
The script is divided into three main parts: helper functions, main game logic, and the question bank.

Question Bank
question_bank: A list of dictionaries. Each dictionary represents a single question and must contain:

"q": The text of the question.

"options": A list of 4 possible answer strings.

"correct_text": The string that exactly matches the correct answer from the "options" list.

Helper Functions
save_score_to_file(name, score):

Opens leaderboard.txt in append mode ("a").

Writes the player's name and score as a new line in the format name,score.

This file is created automatically if it doesn't exist.

show_leaderboard():

Reads all lines from leaderboard.txt.

Parses each line, splitting it by the comma to get the name and score.

Sorts the list of players by score in descending order.

Prints a formatted table of the Top 5 players.

Handles the FileNotFoundError if no games have been played yet.

Main Game Logic
start_game():

Prompts the user for their name.

Shuffles the entire question_bank and selects the first 10 questions.

Iterates through each of the 10 questions.

For each question, it shuffles the "options" list to randomize the answer order (1-4).

It then finds the new index (1-4) of the correct_text within the shuffled list.

It records the start_time before the user input() and the end_time after.

The duration is calculated and checked against the 60-second limit and the 10-second bonus threshold.

Scores are awarded, and a record dictionary is created for the final report.

After the loop, it prints the full performance report and the final score.

Finally, it calls save_score_to_file() and show_leaderboard().
