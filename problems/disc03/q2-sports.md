# BEGIN PROB
You are given a DataFrame called `sports`, indexed by `'Sport'` containing one column, `'PlayersPerTeam'`. The first few rows of the DataFrame are shown below:

<center><img src='../assets/images/disc03/sports.png' width=40%></center>


<br />

# BEGIN SUBPROB
Which of the following evaluates to `'basketball'`?

( ) `sports.loc[1]`
( ) `sports.iloc[1]`
( ) `sports.index[1]`
( ) `sports['Sport'].iloc[1]`

# BEGIN SOLN

**Answer: ** `sports.index[1]`

We are told that the DataFrame is indexed by `'Sport'` and `'basketball'` is one of the elements of the index. To access an element of the index, we use `.index` to extract the index and square brackets to extract an element at a certain position. Therefore, `sports.index[1]` will evaluate to `'basketball'`.

The first two answer choices attempt to use `.loc` or `.iloc` directly on a DataFrame. We typically use `.loc` or `.iloc` on a Series that results from using `.get` on some column. Although we don't typically do it this way, it is possible to use `.loc` or `.iloc` directly on a DataFrame, but doing so would produce an entire row of the DataFrame. Since we want just one word, `'basketball'`, the first two answer choices must be incorrect. 

The last answer choice is incorrect because we can't use `.get` with the index, only with a column. The index is never considered a column.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB
Which of the following evaluates to `5`?

( ) `sports.loc["basketball", "PlayersPerTeam"]`  
( ) `sports["PlayersPerTeam"].loc["basketball"]`  
( ) `sports["PlayersPerTeam"].iloc[1]`  
( ) All of the above  

# BEGIN SOLN

**Answer: ** `All of the above`

- `sports.loc["basketball", "PlayersPerTeam"]`: The `.loc` method accesses the value of a specific row (`"basketball"`) and column (`"PlayersPerTeam"`) by label. This will return `5`.

- `sports["PlayersPerTeam"].loc["basketball"]`: Selecting the column `'PlayersPerTeam'` as a Series and then using `.loc["basketball"]` accesses the value for the `"basketball"` index, returning `5`.

- `sports["PlayersPerTeam"].iloc[1]`: Selecting the column `'PlayersPerTeam'` as a Series and using `.iloc[1]` accesses the second value (index `1`) in the Series, which corresponds to `"basketball"`. This will also return `5`.

Since all three options evaluate to `5`, the correct answer is `All of the above`.

# END SOLN

# END SUBPROB

# END PROB