# BEGIN PROB

Consider the following plot of data in $d=2$ dimensions. We'd like to use $k$-means clustering to cluster the data into $k=3$ clusters.

Suppose the crosses represent initial centroids, which are not themselves data points.

<center><img src="../assets/images/disc13/image.png" width="500"></center>

# BEGIN SUBPROB

Which of the following facts are true about the cluster
assignment during the first iteration, as determined by these initial centroids? Select all that apply.

[ ] Exactly one cluster contains 11 data points.
[ ] Exactly two clusters contain 11 data points.
[ ] Exactly one cluster contains at least 12 data points.
[ ] Exactly two clusters contain at least 12 data points.
[ ] None of the above.

# BEGIN SOLUTION

**Answer**: Exactly two clusters contain at least 12 data points.

- The top cluster will contain 13 data points.
- The left cluster will contain 10 data points.
- The bottom right cluster will contain 12 data points, including the outlier since it is closer to the bottom cross than to the left one.

Thus, the top cluster and bottom right clusters will contain at least 12 data points in Step 1 of the first iteration.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The cross shapes in the plot above represent positions of the initial centroids before the first iteration. Now the
algorithm is run for one iteration, after which the centroids have been adjusted.

We are now starting the second iteration. Which of the following facts are true about the cluster assignment during the **second** iteration? Select all that apply.

[ ] Exactly one cluster contains 11 data points.
[ ] Exactly two clusters contain 11 data points.
[ ] Exactly one cluster contains at least 12 data points.
[ ] Exactly two clusters contain at least 12 data points.
[ ] None of the above.

# BEGIN SOLUTION

**Answers**: Both of:

- Exactly two clusters contain 11 data points.
- Exactly one cluster contains at least 12 data points.

Let's look at each cluster once again.

- The top cluster will contain the same 13 data points as it did before the centroids were ever adjusted. All that happened in Step 2 of the first iteration was that the top centroid was moved down slightly, to the average $x^{(2)}$ position of the 13 points up top.
- The left cluster will contain 11 data points, including the  one outlier. This is because, in Step 2 of the first iteration, the bottom right centroid moved to the right since it was pulled closer by the 11 non-outliers in the bottom right that were assigned to it in Step 1 of the first iteration. At the same time, the left centroid moved to the center of the group of 10 points in the left, since remember, the outlier belonged to the bottom right cluster in Step 1 of the first iteration.
    - As a result, the outlier is now closer to the left centroid than the bottom right centroid, so it will be assigned to the left cluster in Step 1 of the second iteration.
- The right cluster no longer possesses the outlier for the reasons described above, so the right cluster now just contains the bottom-right group of 11 data points.

So, the cluster sizes are 13, 11, and 11, which means that two of the clusters contain 11 data points and one of the clusters contains at least 12 data points.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Compare the value of inertia after the end of the second iteration to
the value of inertia at the end of the first iteration. Which of the following facts
are true? Select all that apply.

[ ] The inertia at the end of the second iteration is lower.
[ ] The inertia doesn't decrease since there are actually 4 clusters in the
    data but we are using k-means with $k=3$.
[ ] The inertia doesn't decrease since there are actually 5 clusters in the
    data but we are using k-means with $k=3$.
[ ] The inertia doesn't decrease since there is an outlier that does not
    belong to any cluster.
[ ] The inertia at the end of the second iteration is the same as at the
    end of the first iteration.

# BEGIN SOLUTION

**Answer**: The inertia at the end of the second iteration is lower.

The inertia after each iteration of $k$-means clustering is non-increasing.
Specifically, at the end of the second iteration the outlier having
moved from the bottom right cluster to the left cluster will have
decreased the inertia, as this movement reduced the total sum of the squared distances of points to their closest centroids.

# END SOLUTION

# END SUBPROB

# END PROB