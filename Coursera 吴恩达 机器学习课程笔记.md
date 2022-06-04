# Coursera 吴恩达 机器学习课程笔记

## Supervised Learning

*   “right answer” given
*   Regression problem or Classfication problem
    *   Regression : predict continuous valued output (e.g. price)
    *   Classfication: discrete value output (e.g. 0 or 1)

## Unsupervised Learning

*   No “right answer” given
*   Cluster problem 
    *   Group samples into groups based on relationships among the variables
    *   no feedback based on the prediction results



## Linear regression

 $\large\boxed{h_\theta(x) = \theta_0 + \theta_1x}$

*   straight line

*   h: hypothesis, which maps from x’s to y’s
*   Linear regression with one variable

## Cost Function

idea: choose $\theta_0$, $\theta_1$ so that $h_{\theta}(x)$ is close to y for (x, y)									$\large\boxed{J(\theta_0, \theta_1) = \frac{1}{2m}\sum_{i=1}^m(h_\theta(x^{(i)})-y^{(i)})^2}$

*   find the  $\theta_0, \theta_1$ That  minimise $J(\theta_0, \theta_1)$.

*   also called **squared error function** 

*   Objective function

     $\large\boxed{\underset{\theta_0, \theta_1}{minimize} \ J(\theta_0, \theta_1)}$

*   Simplified example: set $\theta_0 = 0$

    *   ![截屏2022-05-24 00.19.26](https://tva1.sinaimg.cn/large/e6c9d24ely1h2isqcjzrij215m0oa77e.jpg)
        *    Simplified: set $\theta_0 = 0$
        *   minimum point ont the right gives the best fit stright line on the left.

## Gradeint Descent

$$
\large\boxed{\begin{align*}
\quad Repeat\ until\ convergence:\\
&\theta_j:=\theta_j-\alpha\frac{\partial}{\partial\theta_j}J(\theta_0,\theta_1)\quad(for\ j=0\ and\ j=1)\quad

\end{align*}}
$$

*   $\alpha$ is the **learning rate**: which controls the step size of the gradient descent.

*   the derivative term will approach to zero as we reach the minimum point, so the moving step will autimatically decrease over time. 

*   could suffer from local minimum

*   **Simultaneously** update $\theta_0$ and $\theta_1$.

    $temp0\ := \theta_0 - \alpha\frac{\partial}{\partial\theta_0}J(\theta_0,\theta_1)$

    $temp1\ := \theta_1 - \alpha\frac{\partial}{\partial\theta_1}J(\theta_0,\theta_1)$

    $\theta_0\ := temp0$

    $\theta_1\ := temp1$ 



## Gradient Descent for Linear Regression

$$
\begin{align*}
\theta_j&=\theta_j-\alpha\frac{\partial}{\partial\theta_j}J(\theta_0,\theta_1)\quad(for\ j=0\ and\ j=1)\\
\frac{\partial}{\partial\theta_j}J(\theta_0,\theta_1)&=\frac{\partial}{\partial\theta_j}\frac{1}{2m}\sum_{i=1}^m(h_\theta(x^{(i)})-y^{(i)})^2\\
&=\frac{\partial}{\partial\theta_j}\frac{1}{2m}\sum_{i=1}^m(\theta_0+\theta_1x^{(i)}-y^{(i)})^2\
\end{align*}
$$

$$
\begin{align*}
\quad Repeat\ &until\ convergence:\{\\
&\theta_0\:=\theta_0-\alpha\frac{1}{m}\sum^m_{i=1}(h_\theta(x^{(i)})-y^{(i)})\\
&\theta_1\:=\theta_1-\alpha\frac{1}{m}\sum^m_{i=1}(h_\theta(x^{(i)})-y^{(i)}).x^{i}\\
\}
\end{align*}
$$

*   cost function for linear regression is a convex (bowl shape) function, which always has a global minimum –> always converge to global minimum.
*   this gradient descent process is often called **Batch greadient descent**
    *   each step of gradient descent using all training samples.





## Matrix and Vectors

**Matrix**: array of numbers

**Dimension of matrix**: no. row x  no. columns

**Vector**: n x 1 matrix



### Matrix addition

*   2 mateix have to have the same dimension
*   do addition for each element in the matrices accordingly



### Matrix multiplication

*   scalar multiplication: multiply each element by the scalar

*   Matrix matrix multiplication: 

    *   the no. of columns of the first matrix has to be the same as the no. of rows of the second matrix

    *   ###### exmaple

    *   Properties:

        *   A x B != B x A where B is not an identity matrix.
        *   Identity Matrix: if A . I = I x A = A, denoted $I$ or $I_{n\times n}$, which has 1’s at the diagonals from upper left to lower right, and 0’s elsewhere.

### Inverse

*   Matrix inverse: If A is an m x m (square) matrix, and if it has an inverse, $AA^{-1}=A^{-1}A=I)$ 
*   matrix that does’s hava inverse is called “singular” or “degenerate”



### Transpose

*   Let A be an m x n matrix, and let $B = A^T$, then B is an n x m matrix, and 

    $B_{ij}=A_{ji}$



 