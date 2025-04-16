# BEGIN PROB


You run the $k$-means clustering algorithm on a dataset
and it converges to a certain clustering with associated inertia $I$.
You then duplicate each data point in the dataset and run $k$-means
again on this twice-as-big dataset, with the same initial centroids as
before. Which of the following is true? **Select all that apply.**

[ ] The inertia will be the same as before, $I$.
[ ] The inertia will be twice as much as before, $2I$.
[ ] The centroids found will be the same as before.
[ ] None of the above.

# BEGIN SOLUTION

**Answers**:

- The centroids found will be the same as before.
- The inertia will be twice as much as before, $2I$.

The centroids found will be the same as before because the dataset has been duplicated, but they have not moved! This means $k$ means clustering will find the same clusters as before. You can imagine it like points overlapping each other.

The inertia will be twice as much before $2I$ because of how inertia is calculated. Recall inertia measures how well a dataset is clustered and is calculated by measuring the **total squared distance** from each point to its closest centroid. Since the total number of points has doubled, even though each (unique) point is still assigned to the same centroid, the total squared distance has doubled.

# END SOLUTION

# END PROB