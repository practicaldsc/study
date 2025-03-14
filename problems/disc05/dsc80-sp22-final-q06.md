# BEGIN PROB

[🎥 Walkthrough Available](https://youtu.be/aHtlISTIvL8)

Consider the following HTML document, which represents a webpage
containing the top few songs with the most streams on Spotify today in
Canada.

```html
<head>
    <title>3*Canada-2022-06-04</title>
<head>
<body>
    <h1>Spotify Top 3 - Canada</h1>
    <table>
        <tr class='heading'>
            <th>Rank</th>
            <th>Artist(s)</th> 
            <th>Song</th>
        </tr>
        <tr class=1>
            <td>1</td>
            <td>Harry Styles</td> 
            <td>As It Was</td>
        </tr>
        <tr class=2>
            <td>2</td>
            <td>Jack Harlow</td> 
            <td>First Class</td>
        </tr>
        <tr class=3>
            <td>3</td>
            <td>Kendrick Lamar</td> 
            <td>N95</td>
        </tr>
    </table>
</body>
```

Suppose we define `soup` to be a `BeautifulSoup` object that is
instantiated using the document above.

# BEGIN SUBPROB

How many leaf nodes are there in the DOM tree of the previous
document --- that is, how many nodes have no children?

# BEGIN SOLN

**Answer: ** 14

There's 1 `<title>`, 1 `<h1>`, 3 `<th>`s, and 9 `<td>`s, adding up to
14.

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/aHtlISTIvL8?si=7FeCZZ-vT8dYCwBm" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></center>

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

What does the following line of code evaluate to?

```py
len(soup.find_all("td"))
```

# BEGIN SOLN

**Answer: ** 9

As mentioned in the solution to the part above, there are 9 `<td>`
nodes, and `soup.find_all` finds them all.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

What does the following line of code evaluate to?

```py
soup.find("tr").get("class")
```

# BEGIN SOLN

**Answer: ** `["heading"]` or `"heading"`

`soup.find("tr")` finds the first occurrence of a `<tr>` node, and
`get("class")` accesses the value of its `"class"` attribute.

Note that technically the answer is `["heading"]`, but `"heading"`
received full credit too.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Complete the implementation of the function `top_nth`, which takes in a
positive integer `n` and returns the **name of the $n$-th ranked song**
in the HTML document. For instance, `top_nth(2)` should
evaluate to `"First Class"` (`n=1` corresponds to the top song).

**Note:** Your implementation should work in the case that the page
contains more than 3 songs.

```py
def top_nth(n):
    return soup.find("tr", attrs=__(a)__).find_all("td")__(b)__
```

What goes in blank (a)?

What goes in blank (b)?

# BEGIN SOLN

**Answer: ** a) `{'class' : n}` b) `[2].text` or `[-1].text`

The logic is to find the `<tr>` node with the correct class attribute (which we do by setting attr to `{'class' : 2}`), then access the text of the node's last `<td>` child (since that's where the song titles are stored).

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Suppose we run the line of code `r = requests.get(url)`, where `url` is
a string containing a URL to some online data source.

**True or False:** If `r.status_code` is `200`, then `r.text` must be a
string containing the HTML source code of the site at `url`.

( ) True
( ) False

# BEGIN SOLN

**Answer: ** Option B: False

A status code of 200 means that the request has succeeded. Hence, the response could be JSON, it is not necessarily HTML.

# END SOLN

# END SUBPROB

# END PROB