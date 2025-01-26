# BEGIN PROB

The DataFrame `tv_excl` contains all of the information we have for TV
shows that are available to stream *exclusively* on a single streaming service. 
The `"Service"` column contains the name of the one streaming service
that the TV show is available for streaming on.

The first few rows of `tv_excl` are shown below (though, of course,
`tv_excl` has many more rows than are pictured here). Note that *Being
Erica* is not in `tv_excl`, since it is available to stream on multiple
services.

<center><img src='../assets/images/disc04_new/tv-excl.png' width=65%></center>

The DataFrame `counts`, shown in full below, contains the number of TV
shows for every combination of `"Age"` and `"Service"`.

<center><img src='../assets/images/disc04_new/pivot.png' width=40%></center>

Given the above information, what does the following expression evaluate
to?

```py
tv_excl.groupby(["Age", "Service"]).sum().shape[0]
```

( ) 4 
( ) 5 
( ) 12
( ) 16
( ) 18
( ) 20
( ) 25

# BEGIN SOLN

**Answer**: 18

Note that the DataFrame `counts` is a pivot table, created using `tv_excl.pivot_table(index="Age", columns="Service", aggfunc="size")`. As we saw in lecture, pivot tables contain the same information as the result of grouping on two columns.

The DataFrame `tv_excl.groupby(["Age", "Service"]).sum()` will have one row for every unique combination of `"Age"` and `"Service"` in `tv_excl`. (The same is true even if we used a different aggregation method, like `.mean()` or `.max()`.) As `counts` shows us, `tv_excl` contains every possible combination of a single element in {`"13+"`, `"16+"`, `"18+"`, `"7+"`, `"all"`} with a single element in {`"Disney+"`, `"Hulu"`, `"Netflix"`, `"Prime Video"`}, except for (`"13+"`, `"Disney+"`) and (`"18+"`, `"Disney+"`), which were not present in `tv_excl`; if they were, they would have non-null values in `counts`. 

As such, `tv_excl.groupby(["Age", "Service"]).sum()` will have $20 - 2 = 18$ rows, and `tv_excl.groupby(["Age", "Service"]).sum().shape[0]` evaluates to 18.

# END SOLN

# END PROB