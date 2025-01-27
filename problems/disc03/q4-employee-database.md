# BEGIN PROB

Suppose you are given a DataFrame of employees for a given company. The DataFrame, called `employees`, is indexed by `'employee_id'` (string) with a column called `'years'` (int) that contains the number of years each employee has worked for the company. Suppose that the code

```py
employees.sort_values(by='years', ascending=False).index[0]
```

outputs `'2476'`. 

True or False: The number of years that employee 2476 has worked for the company is greater than the number of years that any other employee has worked for the company.

( ) True
( ) False
# BEGIN SOLUTION

**Answer: ** False

This is false because there could be other employees who worked at the company equally long as employee 2476.

The code says that when the `employees` DataFrame is sorted in descending order of `'years'`, employee 2476 is in the first row. There might, however, be a tie among several employees for their value of `'years'`. In that case, employee 2476 may wind up in the first row of the sorted DataFrame, but we cannot say that the number of years employee 2476 has worked for the company is greater than the number of years that any other employee has worked for the company.

If the statement had said *greater than or equal to* instead of *greater than*, the statement would have been true.

# END SOLUTION

# END PROB