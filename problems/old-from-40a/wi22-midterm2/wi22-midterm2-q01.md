# BEGIN PROB

<i>Source: [Winter 2022 Midterm 2](../wi22-midterm2/index.html), Problem 1</i>

In the game Stringle, players try to guess a randomly generated string. There is a new Stringle string available each day.

Each day's Stringle string is a **six-letter string**, where each letter is chosen uniformly at random, **with replacement**, from among the 26 letters of the English alphabet. This means Stringle strings can have repeated letters, and they do not need to have any meaning as an English word.

Players input a guess, which can be any six-letter string, and get feedback on their guess, which is given by coloring the letters of the guessed string as follows:

- **green** for letters in the correct position,
- **yellow** for letters in the Stringle string, but in the incorrect position,
- **gray** for letters not in the Stringle string.

Based on this feedback, they can guess again, an **unlimited** number of times, until they guess the string correctly, at which point the game is over. Here's an example of what happens when someone plays Stringle and guesses the string on their fifth guess:

<center><img src="../assets/images/wi22-midterm2/stringlewin.png" width="330" height="330"></center>

A player's Stringle **score** is the number of guesses it took them to guess the word correctly. In the example above, the player's score is 5.

(1 point) Stringle uses the following color scheme, or assignment of
colors to meanings:

-   **green** for letters in the correct position,

-   **yellow** for letters in the Stringle string, but in the incorrect
    position,

-   **gray** for letters not in the Stringle string.

Suppose the game developers could have instead used any three colors
from the set of seven colors $\{$red, orange, yellow, green, blue,
purple, gray$\}$, so long as no color has multiple meanings. How many
color schemes include the color purple?

( ) $15$
( ) $30$
( ) $90$
( ) $120$
( ) None of the above.

# BEGIN SOLUTION

$90$

To solve this problem we need to figure out two thigs. First, we need to get the number of groups of three colors that include purple, and then we need to calculate how many different color schemes can we make with three given colors.

For the first part since we know we are using purple the only thing we need to do then is choose two colors from the remaining 6, and we know there's ${6 \choose 2}$ way's to do that. Then given any set of three colors, How many color schemes can we create? To answer this question you can think of the three possible meanings for a color as placesments on a line, thus if you have your three colors on a line, the first one means correct, the second one means incorrect placement for the letter, and the last one means the letter is not on the string, then the question becomes how many lines can you make with three elements, and it should be clear to you thet this is $3!$. Therefore the total number of schemes that include purple would be 

${6 \choose 2} \cdot 3! = 90$ 

# END SOLUTION

# END PROB