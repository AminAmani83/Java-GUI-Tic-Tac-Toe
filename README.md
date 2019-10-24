This is a simple game of Tic Tac Toe, written in Java, using GUI, where the Human user plays against the computer.
I have used NetBeans IDE to auto generate the GUI part. Each of the 9 playing fields is actually a Button. The button text can be X, O or Empty. The user always starts first, and after they choose a field, the event handler will save that information, check if the game is over or not, and if not, run the computer's process to make a move. Finally the program will wait for the next input from the user.


Here is the computer's strategy for winning the game:

When it is the computer's turn, it will go through the following array, to check the fields and make a decision. 
workArray: {row1 row2 row3 col1 col2 col3 crs1 crs2}
This is the strategy that the computer will use:
1. If there are 2 O's in a line somewhere, place the 3rd one and win.
2. If there are 2 X's in a line somewhere, place the O to prevent loss.
3. If none of the above happened, and the center is empty, fill it.
Next, shuffle the workArray. Because we don't want the computer moves to be predictable.
4. If there is an O and 2 Empty fields somewhere, randomly choose one of the 2 Empty fields to place O.
5. If none of the above is true, Choose Randomly.

Question:
Why do we need a workArray, when we have 9 buttons that store the X,O and E values? Why do we store that information in 2 different formats and go through the trouble of converting one format to the other?

Answer:
When it is the computer's turn, we need to check all the rows, columns and 2 crosses. For the first 3 steps, it is ok to simply check them in order. i.e, first check row1, then row2, then row3, then col1, and so on.
But for step 4 and 5, if we go in order, then we would always place an O in the first available empty space, which makes it predictable. So we need to randomize things a bit. That is where the workArray shines. It stores the order in which we check the fields, and when we shuffle it, the order will become random.
The downside is that every time the button values change, we need to update the workArray accordingly.

To be done in the future:
The computer strategy is pretty basic right now, it can be improved by a lot. For example we could predict the user's next move(s) and base our decision on that.
