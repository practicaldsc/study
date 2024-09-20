# BEGIN PROB

In September 2020, Governor Gavin Newsom announced that by 2035, all new vehicles sold in California must be zero-emissions vehicles. Electric vehicles (EVs) are among the most popular zero-emissions vehicles (though other examples include plug-in hybrids and hydrogen
fuel cell vehicles).

<center><img src='../assets/images/disc04/data22.png' width=20%></center>
<br>

The DataFrame `evs` consists of **32** rows, each of which contains information about a different EV model.

* `"Brand"` (str): The vehicle's manufacturer.
* `"Model"` (str): The vehicle's model name.
* `"BodyStyle"` (str): The vehicle's body style.
* `"Seats"` (int): The vehicle's number of seats.
* `"TopSpeed"` (int): The vehicle's top speed, in kilometers per hour.
* `"Range"` (int): The vehicle's range, or distance it can travel on a single charge, in kilometers.

The first few rows of `evs` are shown below (though remember, `evs` has 32 rows total).

<center><img src='../assets/images/disc04/form22.png' width=60%></center>
<br>

**Throughout this problem, we will refer to `evs` repeatedly.**

Assume that:

- The only four values in the `"Brand"` column are `"Tesla"`, `"BMW"`, `"Audi"`, and `"Nissan"`.
- We have already run `import babypandas as bpd` and `import numpy as np`.

**Tip:** Open this page in another tab, so that it is easy to refer to this data description as you work through the exam.


# BEGIN SUBPROB

Which of the following types of visualizations could use to visualize the distribution of `"Range"`? Select all that apply.

[ ] Bar chart
[ ] Histogram
[ ] Scatter plot
[ ] Line plot
[ ] Box plot
[ ] None of the above

# BEGIN SOLUTION

**Answer:** Histogram or box plot

`"Range"` is a numerical (i.e. quantitative) variable, and we use histograms and box plots to visualize the distribution of numerical features.

- A bar chart couldn't work here. Bar charts can show the distribution of a categorical feature, but `"Range"` is not categorical.
- A scatter plot visualizes the relationship between two numerical features, but we are only dealing with one numerical feature here (`"Range"`).
- Similarly, a line plot visualizes the relationship between two numerical features, but we only have one here.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Teslas, on average, tend to have higher `"Range"`s than BMWs. In which of the following visualizations would we be able to see this pattern? Select all that apply.

[ ] A bar chart that shows the distribution of `"Brand"`
[ ] A bar chart that shows the average `"Range"` for each `"Brand"`
[ ] An overlaid histogram showing the distribution of `"Range"` for each `"Brand"`
[ ] A scatter plot with `"TopSpeed"` on the $x$-axis and `"Range"` on the $y$-axis

# BEGIN SOLUTION

**Answer:**

- A bar chart that shows the average `"Range"` for each `"Brand"`
- An overlaid histogram showing the distribution of `"Range"` for each `"Brand"`

Let's look at each option more closely.

- **Option 1:** A bar chart showing the distribution of `"Brand"` would only show us how many cars of each `"Brand"` there are. It would not tell us anything about the average `"Range"` of each `"Brand"`.

- **Option 2:** A bar chart showing the average range for each `"Brand"` would help us directly visualize how the average range of each `"Brand"` compares to one another.

- **Option 3:** An overlaid histogram, although perhaps a bit messy, would also give us a general idea of the average range of each `"Brand"` by giving us the distribution of the `"Range"` of each brand. In the scenario mentioned in the question, we'd expect to see that the Tesla distribution is further right than the BMW distribution.

- **Option 4:** A scatter plot of `"TopSpeed"` against `"Range"` would only illustrate the relationship between `"TopSpeed"` and `"Range"`, but would contain no information about the `"Brand"` of each EV.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Kyle thinks `"Seats"` is a categorical feature because it can be used to categorize EVs by size. For instance, EVs with 4 seats are small, EVs with 5 seats are medium, and EVs with 6 or more seats are large.

Is Kyle correct?

( ) Yes
( ) No

Justify your answer in **one sentence**. Your answer must fit in the box below.
# BEGIN SOLUTION

**Answer:** No

`"Seats"` is a numerical feature, since it makes sense to do arithmetic with the values. For instance, we can find the average number of `"Seats"` that a group of cars has. Gabriel's argument could apply to any numerical feature; just because we can place numerical features into "bins" doesn't make them categorical.


# END SOLUTION

# END SUBPROB

# END PROB
