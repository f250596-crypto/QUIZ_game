# QUIZ_game
A beginner-friendly C++ quiz game you can run in the console. Uses arrays to store questions, functions to organize code, and saves high scores to a file. Great for learning basic programming concepts with a bit of game fun!

## Features

- Multiple Categories: Choose from Computer Science, Science, Sports, or History
- Adjustable Difficulty: Play on Easy, Medium, or Hard modes with different scoring
- Helpful Lifelines: Use special abilities to help you during the quiz
- Score Tracking: Earn points for correct answers with bonus streaks
- Leaderboard: Compete for top scores that are saved between sessions
- Review Mode: See what questions you got wrong after finishing
- Game Logs: Your quiz attempts are recorded for review

## How to Play

1. Start the Game: Run the executable and enter your name
2. Choose Category: Select from four different topic areas
3. Select Difficulty: Pick how challenging you want the quiz to be
4. Answer Questions: You'll get 10 questions with a timer for each
5. Use Lifelines: When stuck, use one of your four available helpers
6. See Results: After the quiz, view your score and review mistakes
7. Check Leaderboard: See how you compare to other players

## Scoring System

### Base Points:
- Easy: 10 points for correct answers, -2 for wrong answers
- Medium: 15 points for correct answers, -3 for wrong answers  
- Hard: 20 points for correct answers, -5 for wrong answers

### Streak Bonuses:
- Answer 3 questions in a row correctly: +5 bonus points
- Answer 5 questions in a row correctly: +15 bonus points

## Lifelines

You get four lifelines per game, each usable once:

1. 50:50: Removes two incorrect options
2. Skip: Skip the current question without penalty
3. Swap: Replace the current question with a new one
4. Time+10: Add 10 extra seconds to the timer

## Setting Up the Game

### Compilation:

Windows (using MinGW):
```
g++ main.cpp -o quiz_game.exe -std=c++11
```

Linux/Mac:
```
g++ main.cpp -o quiz_game -std=c++11
```

### Required Files:

Before running the game, create these text files in the same folder as your executable:

1. computer.txt - For Computer Science questions
2. science.txt- For Science questions  
3. sports.txt - For Sports questions
4. history.txt - For History questions

### Question File Format:

Each question needs exactly 7 lines in your text files:

```
Difficulty level (1=Easy, 2=Medium, 3=Hard)
Question text
Option A
Option B
Option C
Option D
Correct answer letter (A, B, C, or D)
```

Example:
```
2
What is the capital of France?
Paris
London
Berlin
Madrid
A
```

## Game Structure

### Main Components:

- **Main Menu**: Start new quiz, view leaderboard, or exit
- **Quiz Session**: 10 timed questions with scoring
- **Question Display**: Shows question, options, timer, and score
- **Lifeline System**: Special help features during questions
- **Scoring Engine**: Calculates points and streaks
- **Leaderboard**: Tracks and displays top scores
- **Review Mode**: Shows incorrect answers after quiz

### Files Generated:

When you play the game, it creates:
- **high_scores.txt**: Stores the top 5 scores with player names and dates
- **quiz_logs.txt**: Records all quiz attempts with results

## Leaderboard

The leaderboard automatically saves your score if it's in the top 5. Each entry shows:
- Player name
- Date and time of the quiz
- Final score
- Difficulty level played

## Review Mode

After finishing a quiz, you can review:
- All questions you answered incorrectly
- What you chose vs the correct answer
- Learn from your mistakes for next time

## Technical Details

The game is written in C++11 and uses:
- File I/O for question loading and score saving
- Time functions for the quiz timer
- Random number generation for question selection
- Input validation to handle user mistakes

## Customization

You can modify the game by changing these values in the code:

```cpp
const int MAX_Q = 10;           // Maximum questions that can be loaded
const int Q_PER_GAME = 10;      // Number of questions per quiz
const int MAX_LIFELINES = 4;    // Number of lifelines available
```

To add new categories:
1. Create a new question file
2. Update the category selection in the startNewQuiz() function
3. Add the file loading logic

## Common Issues and Solutions

1. **"Question file not found" error**
   - Make sure all question files are in the same folder as the executable
   - Check that filenames match exactly: computer.txt, science.txt, etc.

2. **Compilation errors**
   - Use the -std=c++11 flag when compiling
   - Ensure you have a C++11 compatible compiler

3. **Leaderboard not saving**
   - Check file permissions in your folder
   - Make sure high_scores.txt can be created/modified

4. **Question format problems**
   - Verify each question has exactly 7 lines
   - Check that difficulty levels are 1, 2, or 3
   - Ensure correct answers are A, B, C, or D

## Educational Value

This project demonstrates several programming concepts:
- Game development logic
- File handling and data persistence
- User interface design for console applications
- Input validation and error handling
- Score tracking and ranking systems
- Timer implementation

## Future Improvements

Potential enhancements for this game could include:
- Graphical user interface
- More question categories
- Sound effects and visuals
- Multiplayer mode
- Question editor for creating custom quizzes
- Online leaderboards
- Mobile app version

## License

This project is available for educational use. You can modify, distribute, and build upon it for learning purposes.

## Getting Help

If you encounter problems:
1. Check that all required files are present
2. Verify question file formatting
3. Ensure proper compilation with C++11
4. Check file permissions for score saving

Enjoy testing your knowledge and competing for the top spot on the leaderboard!
