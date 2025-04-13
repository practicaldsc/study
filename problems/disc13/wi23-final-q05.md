# BEGIN PROB

<!-- **k-means Clustering** -->

Look at the following picture representing where the data are in a 2
dimensional space. We want to use k-means to cluster them into 3 groups.
The cross shapes represent positions of the initial centroids (that are
not data points).

# BEGIN SUBPROB

Which of the following facts are true about the cluster
assignment during the first iteration, as determined by these initial
centroids (circle all answers that are correct)? All 35 circles are data points. All 3 plus-sign shapes are the initial centroids. Explain your selected answer(s).

<center><img src="../assets/images/disc13/image.png" width="500"></center>

1.  Exactly one cluster contains 11 data points.

2.  Exactly two clusters contain 11 data points.

3.  Exactly one cluster contains at least 12 data points.

4.  Exactly two clusters contain at least 12 data points.

5.  None of the above.

# BEGIN SOLUTION

Option 4 is correct.

The top cluster will contain 13 points. The left cluster will
contain 10 points. The bottom right cluster will contain 12 points
(including the outlier since it is closer to the bottom cross than to
the left one). Therefore option 4 is correct.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

The cross shapes represent positions of the initial
centroids (that are not data points) before the first iteration. Now the
algorithm is run for one iteration, where the centroids have been
adjusted.

We are now starting the second iteration. Which of the following facts
are true about the cluster assignment during the *second* iteration
(circle all answers that are correct)? Explain your answer.

1.  Exactly one cluster contains 11 data points.

2.  Exactly two clusters contain 11 data points.

3.  Exactly one cluster contains at least 12 data points.

4.  Exactly two clusters contain at least 12 data points.

5.  None of the above.

# BEGIN SOLUTION

Options 2 and 3 are correct.

The top cluster will contain 13 points. The left cluster will
contain 11 points (the outlier has now moved to this cluster since it
will be closer to its centroid). The bottom right cluster will contain
11 points. Therefore options 2 and 3 are correct.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Compare the loss after the end of the second iteration to
the loss at the end of the firs iteration. Which of the following facts
are true (circle all answers that are correct)?

1.  The loss at the end of the second iteration is lower.

2.  The loss doesn't decrease since there are actually 4 clusters in the
    data but we are using k-means with $k=3$.

3.  The loss doesn't decrease since there are actually 5 clusters in the
    data but we are using k-means with $k=3$.

4.  The loss doesn't decrease since there is an outlier that does not
    belong to any cluster.

5.  The loss at the end of the second iteration is the same as at the
    end of the first iteration.

# BEGIN SOLUTION

The loss at each iteration of k-means is non-increasing.
Specifically, at the end of the second iteration the outlier having
moved from the bottom right cluster to the left cluster will have
decreased the loss.

# END SOLUTION

# END SUBPROB

# END PROB