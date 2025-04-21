### Logic for a Scratch game

--- Yahtzeeee

#### Elements needed

1. 5 dices
2. Scorecard sheet
3. Roll Button
4. Hold function
5. Theme Button

#### Pseduocode

1. Start the game
2. Initilize scorecard with all Categories set to "unscored"
3. FOR each of the 13 rounds:
   1. Initialize roll_count = 0
   2. WHILE roll_count < 3:
      1. If roll_count == 0:
         1. Roll all 5 dices
      2. ELSE:
         1. Ask Player which dice to hold
         2. Re-Roll the rest of the dices
      3. Display current Dice values
      4. roll_count += 1
   3. If player decides to hold all the dice:
      1. BREAK out of WHILE Loop
