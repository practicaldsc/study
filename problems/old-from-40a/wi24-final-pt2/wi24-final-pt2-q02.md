# BEGIN PROB

<i>Source: [Winter 2024 Final Part 2](../wi24-final-pt2/index.html), Problem 2</i>

You run the $k$-means clustering algorithm on a dataset
and it converges to a certain clustering with associated inertia $I$.
You then duplicate each data point in the dataset and run $k$-means
again on this twice-as-big dataset, with the same initial centroids as
before. Which of the following is true? **Select all that apply.**

[ ] The centroids found will be the same as before.
[ ] The inertia will be the same as before, $I$.
[ ] The inertia will be twice as much as before, $2I$.
[ ] None of the above.

# BEGIN SOLUTION

Bubbles 1 and 3: "The centroids found will be the same as before" and "The inertia will be twice as much as before, $2I$."

The centroids found will be the same as before because the dataset has been duplicated, but they have not moved! This means $k$ means clustering will find the same clusters as before. You can imagine it like points overlapping each other.

The inertia will be twice as much before $2I$ because of how inertia is calculated. Recall inertia measures how well a dataset is clustered and is calculated by measuring the distance between each data point and its centroid, squaring the distance, and summing these squares across a cluster. We have doubled our points! Since they did not move otherwise the difference does not change, but we have twice as many points, which will cause the inertia to double.

# END SOLUTION

# END PROB