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

$$
R \mathbf{v} =
\begin{bmatrix}
\cos(\theta) & -\sin(\theta) \\
\sin(\theta) & \cos(\theta)
\end{bmatrix}
\begin{bmatrix}
{d \over 2} \\
t
\end{bmatrix} =
\begin{bmatrix}
{d \over 2} \cos(\theta) - t \sin(\theta) \\
{d \over 2} \sin(\theta) + t \cos(\theta)
\end{bmatrix} =
\begin{bmatrix}
r \cos({\pi \over 2} - x) - t \sin({\pi \over 2} - x) \\
r \sin({\pi \over 2} - x) + t \cos({\pi \over 2} - x)
\end{bmatrix} =
\begin{bmatrix}
r \sin(x) - t \cos(x) \\
r \cos(x) + t \sin(x)
\end{bmatrix}
$$

If we set  $a$  is x coordinate, and  $b$  is y coordinate, we can also use *inner product* and  $L^P$-norm to get the following equations system.

$$
\begin{aligned}
& r = a \cos({\pi \over 2} - x) + b \sin({\pi \over 2} - x) \\
& \sqrt{r^2 + a^2 + b^2 - 2 a r \cos({\pi \over 2} - x) - 2 b r \sin({\pi \over 2} - x)} = t
\end{aligned}
$$

Therefore,

$$ a = r \sin(x) - t \cos(x) $$

$$ b = r \cos(x) + t \sin(x) $$

After we get the endpoint coordinates, we can perform the translation. We can separate them to diagonal / anti-diagonal,  $r > b$  or not.

top diagonal format (\\):

$$ b > r, top = the\\_height\\_from\\_top\\_offset + \lvert b - r \rvert $$

$$ b < r, top = the\\_height\\_from\\_top\\_offset - \lvert b - r \rvert $$

top anti-diagonal format (/):

$$ top = the\\_height\\_from\\_top\\_offset - \lvert b - r \rvert $$

left diagonal format (\\):

$$ left = -(a + space\\_between\\_two\\_stacks) $$

left anti-diagonal format (/):

$$ left = -(a + space\\_between\\_two\\_stacks) $$
