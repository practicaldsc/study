# BEGIN PROB

The DataFrame `games` contains information about a sample of popular games, including board games, dice games, and card games. The data comes from Board Game Geek, a popular website and vibrant online community for game enthusiasts.

The columns of games are as follows.

- `"Name"` (`str`): The name of the game.
- `"Mechanics"` (`str`): A sequence of descriptors for how the game is played. A game can have several descriptors, each of which is separated by a comma.
- `"Domains"` (`str`): A sequence of domains to which the game belongs. A game can belong to multiple domains.
- `"Play Time"` (`int`): The average play time of the game, in minutes, as suggested by the game’s creators.
- `"Complexity"` (`float`): The average complexity of the game, on a scale of 1 to 5 points, as reported by Board Game Geek community members.
- `"Rating"` (`str`): The average rating of the game, on a scale of 1 to 10 points, as rated by Board Game Geek community members. Note that while this data should be numerical, it is actually stored as a string, because some entries use a comma in place of a decimal point. For example 8,79 actually represents the number 8.79.
- `"BGG Rank"` (`int`): The rank of the game in Board Game Geek’s database. The formula for how this rank is calculated is not publicly known, but it likely includes many factors, such as `"Rating"`, number of registered owners of the game, and number of reviews.

The first few rows of `games` are shown below (though `games` has many more rows than pictured here).

<center><img src='../assets/images/disc04/preview.jpg' width=100%></center>
<br>

Assume that we have already run `import babypandas as bpd` and `import numpy as np`.

Notice that `"Strategy Games"` and `"Thematic Games"` are two of the possible domains, and that a game can belong to multiple domains.

Define the variables strategy and thematic follows.

```py
strategy = games.get("Domains").str.contains("Strategy Games")
thematic = games.get("Domains").str.contains("Thematic Games")
```

# BEGIN SUBPROB
Many of the games in the `games` DataFrame belong to more than one domain. We want to identify the number of games that belong to only one domain. Select all of the options below that would correctly calculate the number of games that belong to only one domain.
**Hint:** Don’t make any assumptions about the possible domains.

[ ] `(games["Domains"].str.split(" ").apply(len) == 2).sum()`
[ ] `(games["Domains"].apply(len) == 1).sum()`
[ ] `(games[games["Domains"].str.split(",").str.len == 1].value_counts["Name"].sum())`
[ ] `games[games["Domains"].str.split(",").str.len == 1].shape[0]`

# BEGIN SOLUTION

**Answer:** Options 3 and 4

Let’s take a closer look at why **Option 3** and **Option 4** are correct.

**Option 3**: Option 3 first queries the `games` DataFrame to only keep `games` with one `“Domains”`. `games[“Domains”].str.split(“,”).str.len == 1` gets the `“Domains”` column and splits all of them if they contain a comma. If the value does have a comma then it will create a list. For example let’s say the domain was `“Strategy Games”, “Thematic Games”` then after doing `str.split(“,”)` we would have the `list`: `[“Strategy Games”, “Thematic Games”]`. Any row with a `list` will evaluate to `False`. This means we are only keeping values where there is **one** domain. The next part `.groupby(“Domains”).count()[“Name”].sum()` makes a DataFrame with an index of the unique domains and the number of times those appear. Note that all the other columns: `“Name”`, `“Mechanics”`, `“Play Time”`, `“Complexity”`, `“Rating”`, and `“BGG Rank”` now evaluate to the same thing, the number of times a unique domain appears. That means by doing `[“Name”]sum()` we are adding up all the number of times a unique domain appears, which would get us the number of games that belong to only one domain.

**Option 4**: Option 4 starts off exactly like Option 3, but instead of doing `.groupby()` it gets the number of rows using `.shape[0]`, which will give us the number of games that belong to only one domain.

**Option 1:** Let’s step through why Option 1 is incorrect. `games[“Domains”].str.split(“ ”).apply(len) == 2.sum()` gives you a `Series` of the `“Domains”` column, then splits each domain by a space. We then get the length of that `list`, check if the length is equal to 2, which would mean there are two elements in the `list`, and finally get the sum of all elements in the list who had two elements because of the split. Remember that `True` evaluates to 1 and `False` evaluates to 0, so we are getting the number of elements that were split into two. It does not tell us the number of games that belong to only one domain.

**Option 2:** Let’s step through why Option 2 is also incorrect. `(games[“Domains”].apply(len) == 1).sum()` checks to see if each element in the column `“Domains”` has only one character. Remember when you apply `len()` to a string then we get the number of characters in that string. This is essentially counting the number of domains that have 1 letter. Thus, it does not tell us the number of games that belong to only one domain.

# END SOLUTION

# END SUBPROB

# END PROB
