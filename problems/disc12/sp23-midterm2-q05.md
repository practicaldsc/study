# BEGIN PROB


You have a large historical dataset of all competitors in
past years of the Avocado Cup chess tournament. Each year, hundreds of
chess players compete in the tournament, and one person is crowned the
winner. For each competitor in each year of the competition's history,
you have information on their

-   experience level (beginner, intermediate, advanced),

-   birth month (January through December), and

-   whether or not they won the tournament that year (yes or no).

Assume that birthdays of competitors are evenly distributed throughout
the months.

You want to predict who will win this year's Avocado Cup. To do so, you
use this historical data to train a Naive Bayes classifier and classify
each competitor as a winner or non-winner, given their experience level
and birth month. Which of the following reasons best explains **why your
classifier is ineffective** in identifying the winner?

( ) Because it uses a variable (birth month) that likely has nothing to do with a person's chances of winning the tournament.
( ) Because it uses a variable (experience level) that likely has a strong connection with a person's chances of winning the tournament.
( ) Because it uses a dataset where there are many more non-winners than winners.
( ) Because it uses a categorical response variable.

# BEGIN SOLUTION

Bubble 3: Because it uses a dataset where there are many more non-winners than winners.

Each year there is only one winner, but then hundreds of non-winners! This skews the data and makes it harder to figure out if someone won or lost because of their birthday and level.

# END SOLUTION

# END PROB