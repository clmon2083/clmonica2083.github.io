flowchart TD

    Start([Start]) --> AskRange[Prompt: Choose a range of numbers to guess between!]  
    AskRange --> CheckRange{Is this a valid range?}
    
    CheckRange -->|Yes| GenerateNumber[Generate a random number between the range]
    CheckRange -->|No| RangeInvalid[DisplayText: "This range is invalid, please enter a valid range."] --> AskRange
    
    GenerateNumber --> AskGuess[Ask: Take your guess!]
    
    AskGuess --> CheckGuess{Is this input valid?}
    CheckGuess -->|Yes| Compare{Is this the correct generated number?}
    CheckGuess -->|No| InvalidGuess[DisplayText: "This guess is invalid, please enter a valid guess."] --> AskGuess
      
    Compare -->|No| HighOrLow{Is this guess too high or too low?}
    HighOrLow -->|Yes| TooHigh[Display: "Too high! Try again!"] --> AskGuess
    HighOrLow -->|No| TooLow[Display: "Too low! Try again!"] --> AskGuess
    
    Compare -->|Yes| CorrectAnswer[Display: "Congrats! You guessed the right number!"]

    
    CorrectAnswer --> End([End])

Description
1. First, the computer asks for a range to be decided using "AskRange".  
2. Then the range is checked for non-numerical characters. If the input is invalid  
3. The computer then generates a correct a number between said range to be used as the correct answer.  
4. The computer then asks the user to guess the number that was generated.  
5. After recieving the answer, the computer determines wether the guess inputted contains all valid characters.  
6. If the characters are valid, the computer then determines whether the answer is correct or incorrect using "Compare"  
7. If the input is detected to have invalid characters the computer will ask for a valid input.  
8. If the guess is valid but incorrect the computer will then determine whether the guess was too high or too low and display it.
9. If the guess is correct the words "Congrats! You guessed the right number!" will display and end the game.
