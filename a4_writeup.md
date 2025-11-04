# Assignment 4 - Writeup

In assignment 4 we created a basic tic tac toe game so that we could learn object oriented programming. Respond to the following questions.

## Reflection Questions

1. What was the most difficult part to tic-tac-toe?
The has_won function. I had trouble buiding the list of configurations. I noticed that if something is too difficult a good thing to do is break it down.
2. Explain how you would add a computer player to the game.
I would do something like this:


make move as computer(board): // assumes the computer is X
{
    if (two X's in a row next to each other)
    {
        place third X and win
    }
    else if (two O's in a row next to each other)
    {
        place X to block that spot
    }
    else if (board is empty)
    {
        place X in a corner
    }
    else if (a corner opposite any X is *, and the center is *)
    {
        place X in said corner
    }
    else:
    {
        make a random move
    }
}


3. If you add a computer player, explain (doesn't have to be super technical) how you might get the computer player to play the best move every time. *Note - I am not grading this for a correct answer, I just want to know your thoughts on how you might accomplish it.

I would use a search tree to explore the entire state space of Tic-Tac-Toe, and then have it spit out the move that leads to the most winstates eventually. For example, if the board is in state N, and the computer can make moves 1, 2, 3, or 4, (which will make the new board state into N1, N2, N3, and N4 respectively), it will pick move 1, if, from N1, there are the most possible ways to win.