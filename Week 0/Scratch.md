### Logic for a Scratch game

--- Yahtzeeee

#### Elements needed

1. 5 dices
2. Scorecard sheet
3. Roll Button
4. Hold function
5. Theme Button

#### Pseduocode for Yahtzee game logic

1. START game
2. Initilize scorecard with all Categories set to "unscored"
3. Initialize upper_section_total = 0
4. Initialize total_score = 0
5. Set YAHTZEE_BONUS = 0
6. Set Theme_value = 0
7. BUTTON theme:
   1. IF Theme_value == 0:
      1. Change theme to Dark
   2. ELSE
      1. Change theme to Light
         1. Update Theme_value = 1
8. FOR each of the 13 rounds:
9. Initialize roll_count = 0
10. WHILE roll_count < 3:
    1. If roll_count == 0:
       1. Roll all 5 dices
    2. ELSE:
       1. Ask Player which dice to hold
       2. Re-Roll the rest of the dices
    3. Display current Dice values
    4. roll_count += 1
11. If player decides to hold all the dice:
    1. BREAK out of WHILE Loop
12. Display final Dice
13. Show unscored Categories
14. Ask player to select an scoring Category
15. WHILE Player selects already filled category:
    1. Ask player to select unscored/different category
16. score = Function calculate_score(dice, selected_category):
    1. counts = count occurrences of each die value
    2. SWITCH category:
       1. CASE "Ones" to "Sixes":
          1. return sum of dice matching the category number
       2. CASE "Three of a kind":
          1. IF any dice value appears >= 3 times:
             1. return sum of all dices
          2. ELSE
             1. return 0
       3. CASE "Four of a kind":
          1. IF any dice value appears >= 4 times:
             1. return sum of all dices
          2. ELSE
             1. return 0
       4. CASE "Full House":
          1. IF 3 dice have same number and 2 dice have a different same number:
             1. return 25
          2. ELSE
             1. return 0
       5. CASE "Small Straight":
          1. IF 4 dice have consecutive numbers:
             1. return 30
          2. ELSE
             1. return 0
       6. CASE "Large Straight":
          1. IF 5 dice have consecutive numbers:
             1. return 40
          2. ELSE
             1. return 0
       7. CASE "Yahtzee":
          1. IF all dice have same number:
             1. return 50
          2. ELSE
             1. return 0
       8. CASE "Chance":
          1. return sum of all dices
    3. END SWITCH
17. IF selected_category is in Upper Section:
    1. upper_section_total += score
18. IF selected_category == "Yahtzee" AND score ==50:
    1. IF Yahtzee already scored:
       1. YAHTZEE_BONUS +=100
19. Mark selected_category as scored in scorecard
20. Store score in scorecard[selected_category]
21. Display updated scorecard
22. IF upper_section_total >= 63:
23. total_score += 35
24. total_score = sum of all category scores + YAHTZEE_BONUS
25. Display final scorecard
26. Display total_score
27. END game
