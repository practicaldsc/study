As it gets colder outside, it’s important to make sure we’re taking care of our skin! In this exam, we’ll work with the DataFrame `skin`, which contains information about various skincare products for sale at Sephora, a popular retailer that sells skincare products. The first few rows of `skin` are shown below, but `skin` has many more rows than are shown.

<center><img src="../assets/images/fa24-final/df.png" width=800></center>

The columns in `skin` are as follows: 

- `"Type" (str)`: The type of product. There are six different possible types, three of which are shown above.

- `"Brand" (str)`: The brand of the product. As shown above, brands can have multiple products. 

- `"Name" (str)`: The name of product. Assume that product names are unique. 

- `"Price" (int)`: The price of the product, in a whole number of dollars. 

- `"Rating" (float)`: The rating of the product on sephora.com; ranges from 0.0 to 5.0. 

- `"Num Ingredients" (int)`: The number of ingredients in the product.
 
- `"Sensitive" (int)`: 1 if the product is made for individuals with sensitive skin, and 0 otherwise. 

**Throughout the exam**, assume we have already run all necessary import statements.