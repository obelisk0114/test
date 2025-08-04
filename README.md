# test
Since GitHub supports [MathJax](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions) recently, we can write mathematical expressions in LaTeX format. 

First, we need to determine the length and the rotation angle. We can use *Pythagorean theorem* and *inverse trigonometric functions* to get these two results. Therefore, the length,  $t$ , and the rotation angle,  $x$ , are

$$ x = \arctan ({\Delta the\\_height \over space\\_between\\_two\\_stacks}) $$

$$ t = \sqrt {(\Delta the\\_height)^2 + (space\\_between\\_two\\_stacks)^2} $$

Second, we want to translate the arrow. Before we perform the translation, we need to know the endpoint coordinates of the vector. They are the endpoint coordinates just after rotation. In linear algebra, a *rotation matrix* is a transformation matrix that is used to perform a rotation in Euclidean space.

$$
R =
\begin{bmatrix}
\cos(\theta) & -\sin(\theta) \\
\sin(\theta) & \cos(\theta)
\end{bmatrix}
$$

The vector  $\mathbf{v} = [{d \over 2}, t]^T$, $d$ is the height of the stacks, and $t$ is the length of the vector. We can use

$$ r = {d \over 2} , \theta = {\pi \over 2} - x $$

So we can get
