# BEGIN PROB

<!-- Probability / Sample Space-->

There were 70 farmers in a La Jolla farmers market last week. We know
that 52 of them farm arugula, 20 farm beets, 14 farm carrots, 8 farm
arugula and carrots, 8 farm beets and carrots, and 6 farm arugula and
beets.

We pick a farmer uniformly at random. Determine the probability of this
particular farmer farms all three crops, i.e., arugula, beets, and
carrots.

# BEGIN SOLUTION

Let 
\begin{align*}
    A:& \text{ Farmers that grow arugula}\\
    B:& \text{ Farmers that grow beet}\\
    C:& \text{ Farmers that grow carrots}
\end{align*}
One can drow the following Ven diagram (for simplicity, we represented the size of sets instead of probabilities.)
\begin{center}
 \includegraphics[scale=0.20]{Farmers.pdf} 
\end{center}
By setting the sum equal to $70$ we get:

$$
38-x+6-x+8-x+x+6+x+8-x-2+x=70 \xrightarrow[]{} x=6
$$
Therefore, the probability is equal to $\frac{6}{70}=\frac{3}{35}$.

# END SOLUTION

# END PROB