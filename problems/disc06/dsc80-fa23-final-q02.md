# BEGIN PROB

[🎥 Walkthrough Available](https://www.loom.com/share/037504d266e7409bbd0151bbbc2d4774?sid=1119064d-59f8-4440-a572-1d0f2e21c920)

Neeru wants to work with the `'time'` column in `bus`, but the times aren't consistently formatted. He writes the following code:
```py
import re

def convert(y1, y2, y3):
	return int(y1), int(y2) if y2 else 0, y3

def parse(x):
	# Fill me in

bus['time'].apply(parse)
```

Neeru wants the last line of his code to output a Series containing tuples with parsed information from the `'time'` column. Each tuple should have three elements: the hour, minute, and either `'am'` or `'pm'` for each time. For example, the first two values in the `'time'` column are `'12pm'` and `'1:15pm'`, so the first two tuples in the Series should be: `(12, 0, 'pm')` and `(1, 15, 'pm')`.

Select **all** the correct implementations of the function `parse`. Assume that each value in the `'time'` column starts with one or two digits for the hour, followed by an optional colon and an optional two digits for the minute, followed by either "am" or "pm".

*Hint:* Calling `.groups()` on a regular expression match object returns the groups of the match as a tuple. For nested groups, the outermost group is returned first. For example:
```py
>>> re.match(r'(..(...))', 'hello').groups()
('hello', 'llo')
```
Option A:
```py
def parse(x):
	res = x[:-2].split(':')
	return convert(res[0], res[1] if len(res) == 2 else 0, x[-2:])
```
Option B:
```py
def parse(x):
	res = re.match(r'(\d+):(\d+)([apm]{2})', x).groups()
	return convert(res[0], res[1], res[2])
```
Option C:
```py
def parse(x):
	res = re.match(r'(\d+)(:(\d+))?(am|pm)', x).groups()
	return convert(res[0], res[2], res[3])
```
Option D:
```py
def parse(x):
	res = re.match(r'(.+(.{3})?)(..)', x).groups()
	return convert(res[0], res[1], res[2])
```
# BEGIN SOLN
**Answer**: Options A and C

<center><iframe width="800" height="450" src="https://www.loom.com/embed/037504d266e7409bbd0151bbbc2d4774?sid=c36c4875-7f21-4dd7-8004-d3113c35dfbc" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></center>

- Option A: First, we grab everything but `'am'` / `'pm'` with `x[:-2]`. Then splitting on `':'` means that values such as `'1:15'` become a list like `['1', '15']`, while single numbers such as `'12'` become a list like `['12']`. We then pass in the hour value, the minute value or `0` if there is none, and then the `'am'` / `'pm'` value by grabbing just the last two indices of `x`.
- Option B: We use regex to define groups from `x` and return a list of those groups using `.groups()`. The regex matches to any number of integers `'(\d+)'` as the first group, then a colon `':'`, another group of any number of integers `'(\d+)'`, then a final group that matches exactly twice to characters from "apm", which can be "am" or "pm" with `'([apm]{2})'`. The problem with this solution is that while it does correctly match to input such as `'1:15pm'`, it would not match to `'12pm'` because there is no `':'` character.
- Option C: We use regex to define groups from `x` and return a list of those groups using `.groups()`. The regex matches to any number of integers `'(\d+)'` as the first group, then looks for a colon `':'` as the second group, and matches another group to any number of integers following it with `'(\d+)'`. The `'?'` character makes the previous matches optional, so if there is no `':'` followed by integers then it will return `None` for groups 2 and 3 and still match the rest of the string. Finally, it matches one last group that is any two characters after the previous groups. This solution works because the full regex matches the format `'1:15pm'`, while the `'?'` checks so if there is no `':'` it can still match something formatted like `'12pm'`. It also passes in the group indices 0, 2, and 3 because group 1 will just be `':digits'` or `None`, so we want to skip it. (By `digits`, we mean the digits that are after the colon, if any, like `:45`.)
- Option D: We use regex to define groups from `x` and return a list of those groups using `.groups()`. The regex matches any character unlimited times with `'.+'` as the first group, then has another group that takes 3 of any character after the first group from `'(.{3})?`, and this group is optional because of the ending `'?'`. Finally, the last two characters are the last group `'(..)'`. This solution does not work because while the intention is that `'.+'` grabs the hour and `'(.{3})?'` grabs the colon and minutes if present, the `'.+'` just grabs everything because the `'+'` matches unlimited times. Therefore, `'1:15pm'` returns the groups `['1:15', None, 'pm']`, which doesn't work with our `convert` function.

# END SOLN
# END PROB