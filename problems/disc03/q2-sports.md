# BEGIN PROB
You are given a DataFrame called `sports`, indexed by `'Sport'` containing one column, `'PlayersPerTeam'`. The first few rows of the DataFrame are shown below:

<center><img src='../assets/images/disc03/sports.png' width=20%></center>


# BEGIN SUBPROB
Which of the following evaluates to `'basketball'`?

( ) `sports.loc[1]`
( ) `sports.iloc[1]`
( ) `sports.index[1]`
( ) `sports['Sport'].iloc[1]`

# BEGIN SOLN

**Answer: ** `sports.index[1]`

We are told that the DataFrame is indexed by `'Sport'` and `'basketball'` is one of the elements of the index. To access an element of the index, we use `.index` to extract the index and square brackets to extract an element at a certain position. Therefore, `sports.index[1]` will evaluate to `'basketball'`.

The first two answer choices attempt to use `.loc` or `.iloc` directly on a DataFrame. Specifically, `sports.loc[1]` attempts to locate a row with the index label `1`. However, since the DataFrame is indexed by `'Sport'`, and `1` is not a valid index label, this would result in a KeyError. On the other hand, `sports.iloc[1]` accesses the second row of the DataFrame (based on zero-based indexing), but it returns the entire row as a Series, including all its columns. 

The last answer choice is incorrect because `'Sport'` is not a column in the DataFrame. Instead, `'Sport'` is the index of the DataFrame, which is never considered a column.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB
Which of the following expressions evaluate to `5`?

[ ] `sports.loc['basketball', 'PlayersPerTeam']`  
[ ] `sports['PlayersPerTeam'].loc['basketball']`  
[ ] `sports['PlayersPerTeam'].iloc[1]`  
[ ] `sports.loc['PlayersPerTeam']['basketball']`
[ ] `sports.loc['basketball']`   
[ ] `sports.iloc[1]`

# BEGIN SOLN

**Answer: ** The first three options are correct.

### Explanation:

- `sports.loc['basketball', 'PlayersPerTeam']`:  
  `.loc`  will access the value of a specific row (`'basketball'`) and column (`'PlayersPerTeam'`) by label. This will return `5`.

- `sports['PlayersPerTeam'].loc['basketball']`:  
  Selecting the column `'PlayersPerTeam'` as a Series and then using `.loc['basketball']` accesses the value for the `'basketball'` index, returning `5`.

- `sports['PlayersPerTeam'].iloc[1]`:  
  Selecting the column `'PlayersPerTeam'` as a Series and using `.iloc[1]` accesses the second value (index `1`) in the Series, which corresponds to `'basketball'`. This will also return `5`.

- `sports.loc['PlayersPerTeam']['basketball']`:  
  This throws a KeyError because `'PlayersPerTeam'` is not a valid index label in the DataFrame. The `sports` DataFrame is indexed by `'Sport'`, so attempting to locate a row labeled `'PlayersPerTeam'` is invalid. 

- `sports.loc['basketball']`: 
  While this syntax is valid, it retrieves the entire row corresponding to the index `'basketball'`. The result will be a Series, not just the single value. 

- `sports.iloc[1]`:
  In this case, `sports.iloc[1]` retrieves the entire second row of the DataFrame.


# END SOLN

# END SUBPROB

# END PROB