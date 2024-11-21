# BEGIN PROB

You and a friend independently perform gradient descent on the same function, but after $200$ iterations, you have different results. Which of the following is sufficient **on its own** to explain the difference in your results? **Note:** When we say "same function" we assume the learning rate and initial predictions are the same too until said otherwise.

**Select all that apply.**

[ ] The function is nonconvex.
[ ] The function is not differentiable.
[ ] You and your friend chose different learning rates.
[ ] You and your friend chose the same initial predictions.
[ ] None of the above.

# BEGIN SOLUTION

Bubbles 3: "You and your friend chose different learning rates."

If the function is nonconvex and you and your friend have the same initial prediction and learning rate you should end up in the same location local or global minimum.

If the function is not differentiable then you cannot perform gradient descent, so this cannot be an answer.

If you and your friend chose different learning rates it is possible to have different results because if you have a really large learning rate you might be hopping over the global minimum without properly converging. Your friend could choose a smaller learning rate, which will allow you to converge to the global minimum.

If you and your friend chose the same initial predictions you are guaranteed to end up in the same spot.

Because two of the option choices are possible the answer cannot be "None of the above."

# END SOLUTION

# END PROB
