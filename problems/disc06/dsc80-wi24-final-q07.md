# BEGIN PROB

Tahseen decides to look at reviews for the same hotel, but he modifies them so that the only terms they contain are `"taco"` and `"sand"`. The bag-of-words representations of three reviews are shown as vectors below.

<center><img src="../../assets/images/disc06/sand_taco.png" width=350></center>

Using cosine similarity to measure similarity, which pair of reviews are the most similar? If there are multiple pairs of reviews that are most similar, select them all.

[ ] $\vec{r}_1$ and $\vec{r}_2$
[ ] $\vec{r}_1$ and $\vec{r}_3$
[ ] $\vec{r}_2$ and $\vec{r}_3$

# BEGIN SOLUTION

**Answer:** $\vec{r}_1$ and $\vec{r}_2$, **and** $\vec{r}_2$ and $\vec{r}_3$

The cosine similarity of two vectors $\vec{a}$ and $\vec{b}$ is $\frac{\vec{a} \cdot \vec{b}}{||\vec{a}|| \cdot ||\vec{b}||}$. 

- The cosine similarity of $\vec{r}_1$ and $\vec{r}_2$ is: $$\frac{2 \cdot 4 + 3 \cdot 4}{\sqrt{13} \cdot \sqrt{32}} = \frac{20}{4 \cdot \sqrt{26}} = \frac{5}{\sqrt{26}}$$
- The cosine similarity of $\vec{r}_1$ and $\vec{r}_3$ is: $$\frac{2 \cdot 6 + 3 \cdot 4}{\sqrt{13} \cdot \sqrt{52}} = \frac{24}{26} = \frac{12}{13}$$
- The cosine similarity of $\vec{r}_2$ and $\vec{r}_3$ is: $$\frac{4 \cdot 6 + 4 \cdot 4}{\sqrt{32} \cdot \sqrt{52}} = \frac{40}{8 \cdot \sqrt{26}} = \frac{5}{\sqrt{26}}$$

$\frac{12}{13} \approx 0.9231$ and $\frac{5}{\sqrt{26}} \approx 0.9806$. Since **larger** cosine similarities mean more similar vectors, our answer is vector pairs $\vec{r}_1$, $\vec{r}_2$ AND $\vec{r}_2$, $\vec{r}_3$.

Note that we could've answered the question without finding the cosine similarity between $\vec{r}_1$ and $\vec{r}_3$. Remember, the cosine similarity between two vectors is the cosine of the **angle** between the two vectors.

- The angle between $\vec{r}_1$ and $\vec{r}_3$ is clearly bigger than the angle between $\vec{r}_1$ and $\vec{r}_2$, because $\vec{r}_2$ is in between $\vec{r}_1$ and $\vec{r}_3$, so we can rule out $\vec{r}_1$ and $\vec{r}_3$.
- The question then boils down to comparing the angle between $\vec{r}_1, \vec{r}_2$ and the angle between $\vec{r}_2$, $\vec{r}_3$. We can compute the cosine similarities of both pairs, as we did above. But, there's a slightly easier way!
- Specifically, note that $\vec{r}_3 = \begin{bmatrix} 6 \\ 4 \end{bmatrix} = 2 \begin{bmatrix} 3 \\ 2 \end{bmatrix}$, i.e. it is a scalar multiple of $\begin{bmatrix} 3 \\ 2 \end{bmatrix}$, meaning $\vec{r}_3$ points in the same direction as $\begin{bmatrix} 3 \\ 2 \end{bmatrix}$, just is twice the length. This means that the angle between $\vec{r}_2$ and $\vec{r}_3$ is the same as the angle between $\vec{r}_2$ and $\begin{bmatrix} 3 \\ 2 \end{bmatrix}$ (and remember, if two pairs of vectors have the same angle between them, they have the same cosine similarity).
- Why does that matter? Because, now we're comparing the cosine similarity between: $$\vec{r}_1 = \begin{bmatrix} 2 \\ 3 \end{bmatrix}, \vec{r}_2 = \begin{bmatrix} 4 \\  4 \end{bmatrix} \\ \\ \text{ and } \\ \\ \vec{r_2} = \begin{bmatrix} 4 \\ 4 \end{bmatrix}, \frac{1}{2}\vec{r}_3 = \begin{bmatrix} 3 \\ 2 \end{bmatrix}$$
- Because of symmetry (work this out yourself!), the two pairs of vectors have the same cosine similarity, and thus the same angle!


# END SOLUTION

# END PROB