# BEGIN PROB

We have a pool of 50 colleges, and would like to randomly select 4 of those colleges to form a bracket for our Mario Kart Tournament. Selection is performed uniformly at random, so that each team has the same chance of being selected. Please leave your answers in **unsimplified** form: answers of the form $(\frac{3}{4}) \cdot (\frac{2}{3})$ or $\left[1 - (\frac{1}{2})^4\right]$ are *preferred*.

# BEGIN SUBPROB

Assume we populate our tournament by randomly selecting four teams **with replacement**. What is the probability there are no duplicates among the four teams selected for the tournament? Do not simplify your answer.

# BEGIN SOLUTION

**Answer:** $\frac{1}{1} \cdot \frac{49}{50} \cdot \frac{48}{50} \cdot \frac{47}{50}$

We need to find the probability that there are no duplicates among the four teams selected for the tournament from our pool of 50 **with replacement**. Since we are selecting four times, we want each selected team to be unique.

1. **First Selection:**  
   - We can select any of the 50 teams, so the probability is $\frac{50}{50}$ = 1.

2. **Second Selection:**  
   - To avoid duplicates, we must pick a team different from the first one.
   - The probability is $\frac{49}{50}$.
   

3. **Third Selection:**  
   - We must pick a team different from the first two selections.
   - The probability is $\frac{48}{50}$.
   

4. **Fourth Selection:**  
   - We must pick a team different from the first three selections.
   - The probability is $\frac{47}{50}$.

The total probability that there are **no duplicates among the four teams selected** is the product of these probabilities: **$\frac{1}{1} \cdot \frac{49}{50} \cdot \frac{48}{50} \cdot \frac{47}{50}$**

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Now, assume we populate our tournament by randomly selecting four teams from our pool of 50 **without replacement**. Additionally, assume 30 are from Division 1 and 20 teams are from Division 2. What is the probability that there is at least one Division 2 team among the four teams selected for the tournament? Do not simplify your answer.

# BEGIN SOLUTION

**Answer:** $1 - \frac{30}{50} \cdot \frac{29}{49} \cdot \frac{28}{48} \cdot \frac{27}{47}$

We are selecting four teams from our pool of 50 **without replacement**, and we want to calculate the probability that **at least one Division 2 team** is selected, which represented as P(A). We know that there are 30 Division 1 teams and 20 Division 2 teams.

It’s much simpler to calculate the **complement probability**, P(Ac) which is the probability that **all four teams are from Division 1**, and then subtract from 1. Otherwise, we would have to calculate and add the probabilities of choosing 1, 2, 3, or 4 Division 2 teams - much more time consuming. 

1. **First Selection:**  
   - Probability of picking a Division 1 team is $\frac{30}{50}$.

2. **Second Selection:**  
   - After one Division 1 team is selected, there are 29 Division 1 teams left and 49 teams remaining in total.
   - The probability is $\frac{29}{49}$.


3. **Third Selection:**  
   - After two Division 1 teams are selected, there are 28 Division 1 teams left and 48 teams remaining in total.
   - The probability is $\frac{28}{48}$.
   

4. **Fourth Selection:**  
   - After three Division 1 teams are selected, there are 27 Division 1 teams left and 47 teams remaining in total.
   - The probability is $\frac{27}{47}$.

The probability that **all four teams are from Division 1** is:
$\frac{30}{50} \cdot \frac{29}{49} \cdot \frac{28}{48} \cdot \frac{27}{47}$

To find the probability of **at least one Division 2 team** being selected, we use P(A) = 1 - P(Ac): **$1 - \frac{30}{50} \cdot \frac{29}{49} \cdot \frac{28}{48} \cdot \frac{27}{47}$**

# END SOLUTION

# END SUBPROB

# END PROB
