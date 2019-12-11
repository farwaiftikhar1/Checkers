# Checkers
Checkers Game using Alpha Beta Pruning

The program is written in python and works with any python compiler. It was initially constructed using PyCharm and python version 3.6. The project contains three files namely:
	•	Board.py
	•	Algorithm.py
	•	Main.py

When the Main.py is executed the user is asked to input the level of difficulty. After which the 6*6 board appears in which the rows and columns are labeled 0-6. The first move is the human player’s so the player is asked to enter the y-coordinate which is the row number of the piece that needs to be moved and then the x-coordinate that is the column number is added. The coordinates are added for the place to which the piece needs to be moved. The H represents human pieces while X represents computer pieces.

The Board.py file contains the code to implementation of the game. It contains class defined as board and another one named node, in it. Node is a class which represents a piece on the board. It sets the type of the piece using node and its position on the board, these types are either human or computer. It contains an array which has the current positions of the pieces.
The method in the board class get_board returns c_board which is an array with positions of all the pieces. The method set_pieces runs in the height and width of the board and sets the pieces on the board, print_board prints the board, get_move gets the position of the pieces, sees whose move it is and appends this position to an array which contains the legal moves and the method check_legal,moves takes a piece and a move which has to be made and executes the move. The check_capture checks if a capture move is possible and then executes it.

The get_utility implements the heuristic functions for all the three levels of the game. It has a human_value which is set to 1 and a com_value variable which is also set to 1.  The dist_comp and dis_human are initialized to 0. It loops through the board and adds 1 to the human_value everytime it encounters a human player piece and to the dist_human adds the current position of each piece that is discovered while looping through. It does the same for the computer type. Thus,the human_value is all the number of human player’s pieces on the board and the comp_value is the number of all the pieces for the computer player on the board. The dist_comp is the extent to which the comp player has moved towards the opponent’s side, this is value gets bigger as the pieces move along towards the opponents side. While for dist_human the value gets smaller as it moves farther towards the opponent’s side.

For level 1 the heuristic implemented was the difference of the number of pieces on the board for the human and the computer player. The player which has more pieces is likely to win the game. We assign both the comp_value and human_value an equal weightage so the computer plays a neutral game neither defensive. 

In level 2 of the game the computer’s heuristic is calculated by adding the dist_comp to the comp_value thus the computer has more likely chance to win the game it has more number of pieces on the board and the farther down it is towards the opponent’s side. The human_value is subtracted from this value to give the overall value for the heuristic. 

In level 3 of the game both the dist_comp and dist_human are added to the comp_value and human_value respectively.  The dist_comp and dist_human have much smaller weightage, so they just contribute towards a tie breaker. 
The terminal test is carried out in the Algorithm.py in the function terminal_test where the terminal state is tested to be if there are no more pieces left on the board to move and see which player has won. 

In the Algorithm.py the search function is the function equivalent to the alpha beta search algorithm which take the computer to be the max node. The max_value function calls the min_value function and vice versa is also true. The max_value function checks the beta value while it sets the alpha value. While min_value checks the alpha value and sets the Beta value. 



