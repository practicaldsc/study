# BEGIN PROB

<i>Source: [Spring 2023 Final Part 2](../sp23-final-pt2/index.html), Problem 4</i>

At Panda Express, there are $18$ items available on the menu. Food is served on plates that are divided into three equal sections, and all sections of the plate must contain exactly one menu
item.

# BEGIN SUBPROB

Suppose each section of the plate is a different color (in a clockwise order around the plate, the sections are red, yellow, blue). How many different-looking plates of food can be created, if we must have three different menu items on the plate?

One example plate of food has Honey Walnut Shrimp in the red section, Kung Pao Chicken in the yellow section, and brown rice in the blue section.


# BEGIN SOLUTION
${18 \choose 3} \cdot 3!$

This problem is exactly asking for the number of permutations of three elements from a pool of 18 elements, which is 
\begin{align*}
18\cdot17\cdot16 = \frac{18!}{15!} = {18 \choose 3} \cdot 3!
\end{align*}

You should remember that whenever you draw items **without replacement** and the **order matters** then you are calculating a permutation.  Alternatively, you can reason that in the red segment of the plate, you can have any of the 18 different menu items, then for the yellow segment you only have 17 menu items available, since the red already has one, lastly you have 16 items left for the blue part of the plate. Then just multiply all the ways you can choose menu items for each segment getting a total of
\begin{align*}
18\cdot17\cdot16 = {18 \choose 3} \cdot 3!
\end{align*}

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose each section of the plate is a different color (in a clockwise order around the plate, the sections are red, yellow, blue). How many different-looking plates of food can be created, if we are allowed to have the same food in multiple sections?

# BEGIN SOLUTION

$18^3$

In this question, since we are allowed to repeat menu items, we have 18 options for each of the sections of the plate. Then when you multiply all the ways you can choose items for a secyion of the plate you get $18\cdot18\cdot18 = 18^3$. 
Similarly to how we explained the question before this one, aske your self if the drawing process has replacement and if the order matters. In this case you'll find that  **we have replacement** and **we also have ordeirng**, so this is a sequence, and the number of sequence's of lenght k from a pool of n elements is $n^k$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose each section of the plate is the same color (white). How many different-looking plates of food can be created, if we must have three different menu items on the plate?

One example plate of food has, in a clockwise order around the plate, Eggplant Tofu, Broccoli Beef, and fried rice. This is the same plate as the one that has, in a clockwise order, Broccoli Beef, fried rice, and Eggplant Tofu, because one plate can be rotated to look like the other (this counts as the same.)


# BEGIN SOLUTION

$2 \cdot {18 \choose 3}$

Similarly to how we solved the previous problems, we are going to deconstruct the process of building a plate with the given characteristics. First, we know that any plate must have three items, so let's start by choosing three items from the 18 menu items we have available (we have ${18 \choose 3}$ ways to do that). 

Now once you chose the menu items that go on your plate, you need to arange them on your plate, normally if we are aranging three distinct elements on a line we know that there's $3!$ ways to do that, unfortunately like we saw in the prompt of this problem we need to account for when we rotate the plate. In the prompt it was signaled that the plate with Eggplant Tofu, Broccoli Beef, and fried rice in clockwise order around the plate, is the same as the plate with Broccoli Beef, fried rice, and Eggplant Tofu (also in clockwise order), this happens because if you rotate your fisrt plate in counter clockwise direction then you would get the second plate, and in fact we could do this again to show those two plates are the same as the plate with fried rice, Eggplant Tofu, and Broccoli Beef. If you were to do the rotation again you would get the original plate, so for any specific plate we can find three different lines that describe the same plate, thus if we divide the number of ways to order our 3 menu items on a line($3!$) by 3, we should get the number of different plates we can build with any three items, so $\frac{3!}{3} = 2$ 

Finally we only need to mutiply the number of ways we can choose three menu items by the number of plates we can build with those three items getting $2 \cdot {18 \choose 3}$.

# END SOLUTION

# END SUBPROB

# BEGIN SUBPROB

Suppose each section of the plate is the same color (white). Now we'd like to consider what happens if we can have the same food in multiple sections. What do we need to **add to 4.3's answer** to get the number of different-looking plates of food that can be created, if we are allowed to have the same food in multiple sections?

As before, two plates that can be rotated to look like one another count as the same.

# BEGIN SOLUTION

$2 \cdot {18 \choose 2} + {18 \choose 1}$

Now that we are allowed to repeat menu items we need to consider the 2 new types of plates, type 1 a plate with the same menu item 3 times, type 2 a plate with a repeated menu item and an additional menu item. Then the total number of plates should be our answer from 4.3 plus the number of plates with type 1 and number of plates with type 2. 

**Type 1**
Counting the number of type 1 plates should be fairly simple, if your plate only contains one menu item then there should be one plate of this type for each of the menu items, therefore there's $18$ plates like this.

**Type 2**
Now for type 2, we can start by chossing two items from the menu (there's $18 \choose 2$ ways to do that) then from here note that you need to choose which item you are going to repeat because depending on which one you choose to double you get a different plate (there's $2$ options to double), then  you should also consider the order but you should realize that no matter how you arange the item on your plate you are just getting rotations of the same plate, therefore your total number of plates of type 2 is $2 \cdot {18 \choose 2}$

Lastly, just add both the plates of type 1 and type 2, and that's the number you need to add to your answer from 4.3. 
**Answer**: $2 \cdot {18 \choose 2} + {18 \choose 1}$

# END SOLUTION

# END SUBPROB

# END PROB