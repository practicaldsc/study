# BEGIN PROB

The two plots below show the total number of boots (top) and sandals (bottom) purchased per month in the `df` table. Assume that there is one data point per month.

<center><img src="../../assets/images/disc09/boot.png" style="width: 100%; height: auto;"></center>

<center><img src="../../assets/images/disc09/sandal.png" style="width: 100%; height: auto;"></center>


For each of the following regression models, use the visualizations shown above to select the value that is **closest** to the fitted model weights. If it is not possible to determine the model weight, select "Not enough info". For the models below:

- The notation $\text{boot}$ refers to the number of boots sold.
- The notation $\text{sandal}$ refers to the number of sandals sold.
- $\text{summer}=1$ is a column with value 1 if the month is between March (03) and August (08), inclusive.
- $\text{winter}=1$ is a column with value 1 if the month is between September (09) and February (02), inclusive.


# BEGIN SUBPROB

$\text{predicted boot}_i = w_0$

$w_0$:

( ) 0  
( ) 50  
( ) 100  
( ) Not enough info

# BEGIN SOLN

**Answer:** $w_0 = 50$

The model predicts a constant value for boots. The intercept $w_0$ represents the average boots sold across all months. Since the boot count plot shows data points centered around 50, this is the best estimate.


# END SOLN

# END SUBPROB



# BEGIN SUBPROB

$\text{predicted boot}_i = w_0 + w_1 \cdot \text{sandals}_i$

$w_0$:

( ) -100  
( ) -1  
( ) 0  
( ) 1  
( ) 100  
( ) Not enough info

$w_1$:

( ) -100  
( ) -1  
( ) 1  
( ) 100  
( ) Not enough info

# BEGIN SOLN

**Answer:** 

$w_0$: 100

The intercept $w_0$ represents the predicted boot sales when sandal sales are zero. Since the boot plot shows a baseline of ~100 units during months with minimal sandal sales (e.g., winter), this justifies $w_0 = 100$

$w_1$: -1

The coefficient 
$w_1 = −1$ indicates an inverse relationship: for every additional sandal sold, boot sales decrease by 1 unit. This aligns with seasonal trends (e.g., sandals dominate in summer, boots in winter), and the plots show a consistent negative slope of -1 between the variables.



# END SOLN

# END SUBPROB



# BEGIN SUBPROB

$\text{predicted boot}_i  = w_0 + w_1 \cdot (\text{summer=1})_i$

$w_0$:

( ) -100  
( ) -1  
( ) 0  
( ) 1  
( ) 100  
( ) Not enough info

$w_1$:

( ) -80  
( ) -1  
( ) 0  
( ) 1  
( ) 80  
( ) Not enough info

# BEGIN SOLN

**Answer:**

$w_0$: 100

The intercept represents the average boot sales when $\text{summer}=0$ (winter months). Since the boot plot shows consistent sales of ~100 units during winter, this value is justified.

$w_1$: -80

The coefficient for $\text{summer}=1$ reflects the change in boot sales during summer. If boot sales drop sharply by ~80 units in summer (e.g., from 100 in winter to 20 in the summer), this negative offset matches the seasonal trend.

# END SOLN

# END SUBPROB



# BEGIN SUBPROB

$\text{predicted sandal}_i  = w_0 + w_1 \cdot (\text{summer=1})_i$

$w_0$:

( ) -20  
( ) -1  
( ) 0  
( ) 1  
( ) 20  
( ) Not enough info

$w_1$:

( ) -80  
( ) -1  
( ) 0  
( ) 1  
( ) 80  
( ) Not enough info

# BEGIN SOLN

**Answer:**

$w_0$: 20

The intercept represents baseline sandal sales when $\text{summer}=0$ (winter months). Since the sandal plot shows consistent sales of ~20 units during winter, this value aligns with the seasonal low.

$w_1$: 80

The coefficient reflects the increase in sandal sales during summer. If sales rise sharply by ~80 units in summer (e.g., from 20 in winter to 100 in summer), this positive seasonal effect matches the trend shown in the visualization.

# END SOLN

# END SUBPROB



# BEGIN SUBPROB

$\text{predicted sandal}_i  = w_0 + w_1 \cdot (\text{summer=1})_i + w_2 \cdot (\text{winter=1})_i$

$w_0$:

( ) -20  
( ) -1  
( ) 0  
( ) 1  
( ) 20  
( ) Not enough info

$w_1$:

( ) -80  
( ) -1  
( ) 0  
( ) 1  
( ) 80  
( ) Not enough info

$w_2$:

( ) -80  
( ) -1  
( ) 0  
( ) 1  
( ) 80  
( ) Not enough info

# BEGIN SOLN

**Answer:**

$w_0$: Not enough info

$w_1$: Not enough info

$w_2$: Not enough info

The model includes both (\text{summer}) and (\text{winter}) variables, which  cover all months. This creates multicollinearity. The intercept and coefficients cannot be uniquely determined without a reference category or additional constraints. For example, increasing the intercept and decreasing both seasonal coefficients equally would yield the same predictions. The visualizations do not provide enough information to resolve this ambiguity.

# END SOLN

# END SUBPROB

# END PROB