::: center
**Data Overview: Food Deliveries**
:::

In this exam, we'll work with the DataFrame `orders`, which contains
information about deliveries made using various food delivery services
in India.

The first few rows of `orders` are shown below, but `orders` has many
more rows than are shown.

<center><img src="../assets/images/wn25-midterm/df.png" width=800></center>


Each row in `orders` contains information about a single delivery. The
columns in `orders` are as follows:

-   `"driver" (str)`: The delivery driver's ID. Note that there are
    duplicate values in this column, because some drivers have made
    multiple deliveries.

-   `"type" (str)`: The type of food ordered; either `"Buffet"`,
    `"Drinks"`, `"Meal"`, or `"Snack"`.

-   `"rating" (float)`: The average rating of the driver out of 5,
    **after** making the given delivery.

-   `"dist" (float)`: The distance from the restaurant to the delivery
    address, in kilometers.

-   `"traffic" (str)`: The level of traffic; either `"High"`, `"Low"`,
    `"Moderate"`, or `"Very High"`.

-   `"minutes" (float)`: The time in minutes between when a customer
    places their order and when they receive it.

**Throughout the exam**, assume we have already run all necessary import
statements.

**Make sure you have read the Data Overview before beginning!**
