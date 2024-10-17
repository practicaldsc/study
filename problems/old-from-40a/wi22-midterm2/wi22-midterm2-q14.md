# BEGIN PROB

<i>Source: [Winter 2022 Midterm 2](../wi22-midterm2/index.html), Problem 14</i>

You survey 250 Stringle players and ask them several questions
about their Stringle-playing behavior, with the goal of figuring out how
much they would be willing to pay if Stringle were to switch to a paid
annual subscription. All of the questions are yes or no questions,
except for

*"What's the maximum amount you would pay for a year's subscription to Stringle?"*

which has options \$0, \$10, or \$20. Of the 250 participants,

-   100 said they would pay \$0,

-   50 said they would pay \$10, and

-   100 said they would pay \$20.

The table below shows the survey questions and gives the number of
people who answered yes to each question, broken down by how much they
would pay for a subscription.

::: center
  Question                                                     Number of yes responses from those who would pay \$0 **(among 100 people)**   Number of yes responses from those who would pay \$10 **(among 50 people)**   Number of yes responses from those who would pay \$20 **(among 100 people)**
  ------------------------------------------------------------ ----------------------------------------------------------------------------- ----------------------------------------------------------------------------- ------------------------------------------------------------------------------
  Do you play Stringle every day?                              30                                                                            10                                                                            50
  Do you share your Stringle results with friends or family?   40                                                                            20                                                                            40
  Do you record your Stringle scores anywhere?                 30                                                                            30                                                                            30
  Have you ever recommended Stringle to someone you know?      40                                                                            40                                                                            80
:::

Assume that each person answered each question on the survey. For
example, of the 100 people who said they would pay \$0 for Stringle, 30
said "Yes" to the question *Do you play Stringle every day?*, and the
other 70 said "No".

You will use the results of this survey to try to predict how much a
person is willing to pay based on their answers to the four questions
listed in the table above, using a naive Bayes classifier (without
smoothing).

What would your classifier predict for someone who answers the survey
questions as follows:

-   *Do you play Stringle every day?* "No"

-   *Do you share your Stringle results with friends or family?* "Yes"

-   *Do you record your Stringle scores anywhere?* "No"

-   *Have you ever recommended Stringle to someone you know?* "No"

**Hint**: It's not necessary to do lots of arithmetic.

( ) This person would pay \$0 for a Stringle subscription.
( ) This person would pay \$10 for a Stringle subscription.
( ) This person would pay \$20 for a Stringle subscription.

# BEGIN SOLUTION

This person would pay \$0 for a Stringle subscription.\

TODO

# END SOLUTION

# END PROB