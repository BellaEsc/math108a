# Final Practice Problems

## Problem 1

Let $U, W$ be subspaces of a vector space $V$ such that dim($U$) $\ge$ dim($W$). Prove that there exists a $\tau \in \text{End}(V)$ such that $\tau(U) = W$.

**Solution.** Let $n = \text{dim}(V), k = \text{dim}(U), l = \text{dim}(W)$. Then, let $v_1,\dots,v_k$ be a basis for $U$. Using the Steinitz Replacement theorem, we can extend this to a basis of $V$, $v_1,\dots,v_n$. Now, let $w_1,\dots,w_l$ be a basis for $W$. We can then define a linear map $\tau$ so that
$$
\tau(v_i) = w_i, \quad i \in 1,\dots,l \\
\tau(v_i) = 0, \quad i \in l+1,\dots,n.
$$
Now, if we have any element $v \in \tau(U)$, then we know that there exists some $u \in U$ so that $\tau(u) = v$. Then we also know that
$$
u = \lambda_1 v_1 + \dots \lambda_k v_k
$$
for $\lambda_1,\dots,\lambda_k \in F$. So, by the linearity of $\tau$,
$$
\begin{align}
\tau(u) &= \tau(\lambda_1 v_1 + \dots \lambda_k v_k) \\
&= \lambda_1 \tau(v_1) + \dots + \lambda_k \tau(v_n) \\
&= \lambda_1 w_1 + \dots + \lambda_l w_l + 0 + \dots + 0 \in W.
\end{align}
$$
Since $v$ is arbitrary, then $\tau(U) \subseteq W$.

Now, suppose we have any $w \in W$. Then $w = \lambda_1w_1+\dots+ \lambda_l w_l$ for some $\lambda_1,\dots,\lambda_l \in F$. By the definition of $\tau$, 
$$
\begin{align}
\lambda_1w_1+\dots+ \lambda_l w_l &= \lambda_1 \tau(v_1) + \dots + \lambda_l \tau(v_l) \\
&= \tau(\lambda_1v_1 + \dots + \lambda_l v_l) \quad \text{(linearity of $\tau$)}
\end{align}
$$
Since $v_1,\dots,v_l \in U$, Then $w = \tau(u)$ for some $u \in U$ and $w \in \tau(U)$. Since $w$ is arbitrary, then $W \subseteq \tau(U)$. 

So $W = \tau(U)$.

## Problem 2

Suppose $\tau: U \rightarrow V$ is a surjective linear map. Prove that there exists a subspace $W$ of $U$ such that the restriction $\tau_{|w}: W\rightarrow V$ is an isomorphism.

**Solution.** Let $v_1,\dots,v_n$ be a basis for $V$. Since $\tau$ is surjective, then we know that for any $v \in V$, there exists some $u \in U$ so that $\tau(u) = v$. So let $w_1,\dots,w_n \in U$ be the elements in $U$ where $\tau(w_1) = v_1,\dots,\tau(w_n)=v_n$. Then $W = \text{Span}(w_1,\dots,w_n)$ is a subspace of $U$, and the restriction $\tau_{|W}$ is an isomorphism.

(Surjective) Let $v \in V$. Then $v = \lambda_1 v_1 + \dots + \lambda_n v_n$ for some $\lambda_1,\dots,\lambda_n \in F$. As defined above,
$$
\begin{align}
v &= \lambda_1 v_1 + \dots \lambda_n v_n \\
&= \lambda_1 \tau(w_1) + \dots + \lambda_n \tau(w_n) \\
&= \tau(\lambda_1 w_1 + \dots + \lambda_n w_n) \\
&= \tau(w) \quad \text{for some $w \in W$}.
\end{align}
$$
Since $v$ is arbitrary, then $\tau_{|W}$ is surjective.

(Injective) Let $w \in W$ where $\tau(w) = 0$. Since $w \in W$, then $w = \lambda_1 w_1 + \dots + \lambda_n w_n$ for some $\lambda_1,\dots,\lambda_n \in F$. Then,
$$
\tau(w) = \tau(\lambda_1 w_1 + \dots + \lambda_n w_n) = 0 \\
\lambda_1 \tau(w_1) + \dots + \lambda_n \tau(w_n) = 0 \\
\lambda_1 v_1 + \dots + \lambda_n v_n = 0.
$$
Since $v_1,\dots,v_n$ are linearly independent, then for this to be true, $\lambda_1 = \dots = \lambda_n = 0$. Then this means $w$ must be 0, so $\text{Ker}(\tau_{|W}) = \{0\}$, and $\tau_{|W}$ is injective.

So $\tau_{|W}$ is an isomorphism. 

## Problem 3

Let $\tau \in \mathcal{L}(U,V)$ and $\sigma \in \mathcal{L}(V,W)$. Prove that if null($\sigma \tau$) $\gt$ null($\tau$), then $\text{Ker}(\sigma) \cap \text{Im}(\tau) \ne \{0\}$.

**Solution.** We know that $\text{Ker}(\tau) \subseteq \text{Ker}(\sigma\tau)$, so if null($\sigma \tau$) $\gt$ null($\tau$), then that means there exists some $x \in U$ so that $x \notin \text{Ker}(\tau)$ and $\sigma \tau(x) = \sigma (\tau(x)) = 0$. Letting $y \in V$ so that $y = \tau(x)$, we know $y \ne 0$ and $y \in \text{Ker}(\sigma)$ and $y \in \text{Im}(\tau)$. So $y \in \text{Ker}(\sigma) \cap \text{Im}(\tau)$, and $\text{Ker}(\sigma) \cap \text{Im}(\tau) \ne \{0\}$.

## Problem 4

Let $\tau \in \mathcal{L}(\mathbb{R}^3, \mathbb{R}^2)$ and $\sigma \in \mathcal{L}(\mathbb{R}^2, \mathbb{R}^3)$ be respectively given by
$$
\tau(x,y,z) = (x - 2y + z, 2x + 3y - 5z) \\
\sigma(u,v) = (2u + 3v, u - v, u + 3v)
$$
(a) Let $A$ be the matrix of $\tau$ in the standard bases. what is $A$?
$$
\tau(1,0,0) = (1,2), \quad 
\tau(0,1,0) = (-2, 3), \quad 
\tau(0,0,1) = (1, -5).
$$

$$
A = 
\begin{bmatrix}
	1 & -2 & 1 \\
	2 & 3 & -5
\end{bmatrix}
$$

(b) Let $B$ be the matrix of $\sigma$ in the standard bases. What is $B$?
$$
\sigma(1,0) = (2, 1, 1), \quad \sigma(0,1) = (3, -1, 3)
$$

$$
B = 
\begin{bmatrix}
	2 & 3 \\
	1 & -1 \\
	1 & 3
\end{bmatrix}
$$

(c) Find the matrix of $\sigma \tau$ in the standard bases.
$$
[\sigma \tau] = 
\begin{bmatrix}
	2 & 3 \\
	1 & -1 \\
	1 & 3
\end{bmatrix}
\begin{bmatrix}
	1 & -2 & 1 \\
	2 & 3 & -5
\end{bmatrix} = 
\begin{bmatrix}
8 & 5 & -13 \\
-1 & -5 & 7 \\
7 & 7 & -14
\end{bmatrix}
$$
(d) Find the matrix of $\tau \sigma$ in the standard bases.
$$
[\sigma \tau] = 
\begin{bmatrix}
	1 & -2 & 1 \\
	2 & 3 & -5
\end{bmatrix}
\begin{bmatrix}
	2 & 3 \\
	1 & -1 \\
	1 & 3
\end{bmatrix} = 
\begin{bmatrix}
1 & 8 \\
2 & -12
\end{bmatrix}
$$

## Problem 5

Let $U = \mathbb{R}^3$, $V = \mathbb{R}^2$, $W = \mathbb{R}^4$, and let $\alpha = (e_1, e_2, e_3)$, $\beta = (f_1, f_2)$, and $\gamma = (g_1, g_2, g_3, g_4)$ be the standard basis for $U, V, W$ respectively. Suppose $\sigma \in \mathcal{L}(V,U)$ and $\tau\in \mathcal{L}(W, V)$ are such that
$$
{}_\alpha[\sigma]_\beta =
\begin{bmatrix}
1 & 1 \\
3 & 0 \\
0 & 1
\end{bmatrix} \quad \text {and} \quad
{}_\beta[\tau]_\gamma =
\begin{bmatrix}
0 & 2 & -1 & 1 \\
1 & 0 & 1 & 1
\end{bmatrix}
$$
Let $\alpha' = (e_1, e_1 + e_2, e_3)$ and $\gamma' = (g_1, g_1 + g_2, g_3, g_3 + g_4)$. Compute ${}_{\alpha'}[\sigma \tau]_{\gamma'}$.

**Solution.** 
$$
\tau(g_1) = f_2, \quad 
\tau(g_2) = 2f_1, \\
\tau(g_3) = -f_1 + f_2 \quad
\tau(g_4) = f_1 + f_2. \\[4mm]

\tau(g_1) = f_2, \quad
\tau(g_1 + g_2) = 2f_1 + f_2, \\
\tau(g_3) = -f_1 + f_2, \quad 
\tau(g_3 + g_4) = 2 f_2. \\[4mm]

{}_\beta[\tau]_{\gamma'} = 
\begin{bmatrix}
0 & 2 & -1 & 0 \\
1 & 1 & 1 & 2
\end{bmatrix}.
$$

$$
\sigma(f_1) = e_1 + 3e_2, \quad \sigma(f_2) = e_1 + e_3. \\[4mm]

\sigma(f_1) = -2(e_1) + 3(e_1 + e_2), \quad \sigma(f_2) = e_1 + e_3. \\[4mm]

{}_{\alpha'}[\sigma]_\beta =
\begin{bmatrix}
-2 & 1 \\
3 & 0 \\
0 & 1
\end{bmatrix}.
$$

$$
\begin{align}
_{\alpha'}[\sigma \tau]_{\gamma'} &=
\begin{bmatrix}
-2 & 1 \\
3 & 0 \\
0 & 1
\end{bmatrix}
\begin{bmatrix}
0 & 2 & -1 & 0 \\
1 & 1 & 1 & 2
\end{bmatrix} \\
&=
\begin{bmatrix}
1 & -3 & 3 & 2 \\
0 & 6 & -3 & 0 \\
1 & 1 & 1 & 2
\end{bmatrix}.

\end{align}
$$

## Problem 6

Let $U, W$ be subspaces of $V$ and let 
$$
\tau: V \rightarrow (V / U) \times (V / W)
$$
be the map (of sets) defined by $\tau(v) = (v + U, v+W)$ for all $x \in V$.

(a) Show that $\tau$ is a linear map.

In order for a map to be linear, it must respect addition and scalar multiplication. Suppose we have $v_1, v_2 \in V$ and $\lambda_1 \in F$. Addition:
$$
\begin{align}
\tau(v_1 + v_2) &= ((v_1 + v_2) + U, (v_1 + v_2) + W) \\
&= ([v_1 + v_2]_U, [v_1 + v_2]_W) \\
&= ([v_1]_U + [v_2]_U, [v_1]_W + [v_2]_W) \\
&= ([v_1]_U, [v_1]_W)  + ([v_2]_U, [v_2]_W) \\
&=\tau(v_1) + \tau(v_2).
\end{align}
$$
Scalar multiplication:
$$
\tau(\lambda v_1) = (\lambda v_1 + U, \lambda v_1 + W) \\
= (\lambda[v_1]_U, \lambda[v_1]_W) \\
= \lambda([v_1]_U, [v_1]_W) \\
= \lambda \tau(v_1).
$$


(b) Show that if $\tau$ is surjective, then $V = U + W$.

If $\tau$ is surjective, then for every $(x + U, y + W) \in (V/U)\times(V/W)$, there exists some $v \in V$ so that $\tau(v) = (x + U, y + W)$.  Then, by the definition of $\tau$, $(x + U, y + W) = (v + U, v + W)$. So $v + U = x + U$ and $v + W = y + W$, which means that $v - x \in U$ and $v - y \in W$. Then there exists $u \in U, w \in W$ so that $v = u + x = w + y$. If we take $y = 0$, then $x = w - u$. This is a linear combination of elements in $W$ and $U$, and since $x$ is arbitrary, this means that every element $x \in V$ can be written this way. So $U + W = V$.

## Problem 7

Let $\alpha = (e_1, e_2, e_3)$ be the standard ordered basis for $\mathbb{R}^3$ and let $a* = (\varepsilon_1, \varepsilon_2, \varepsilon_3)$ denote the dual basis for $\alpha$. Let
$$
\beta = (e_1 - e_2, e_2, e_2 + e_3)
$$
(which is another basis for $\mathbb{R}^3$) and denote $\beta* = (\varphi_1, \varphi_2, \varphi_3)$ the dual basis for $\beta$. Express each of $\varphi_1, \varphi_2, \varphi_3$ as a linear combination of $\varepsilon_1,\varepsilon_2, \varepsilon_3$. Show all your work.

**Solution.** 
$$
\varphi_1(e_1 - e_2) = 1, \quad \varphi_1(e_2) = 0, \quad \varphi_1(e_2 + e_3) = 0. \\[4mm]
\varphi_1(e_1) = \varphi_1(e_1 - e_2) + \varphi_1(e_2) = 1 \\
\varphi_1(e_2) = 0, \\
\varphi_1(e_3) = \varphi_1(e_2 + e_3) - \varphi_1(e_2) = 0. \\[4mm]
\varphi_1 = \varepsilon_1.
$$

$$
\varphi_2(e_1 - e_2) = 0, \quad \varphi_2(e_2) = 1, \quad \varphi_2(e_2 + e_3) = 0. \\[4mm]
\varphi_2(e_1) = \varphi_2(e_1 - e_2) + \varphi_2(e_2) = 1, \\
\varphi_2(e_2) = 1, \\
\varphi_2(e_3) = \varphi_2(e_2 + e_3) - \varphi_2(e_2) = -1. \\[4mm]
\varphi_2 = \varepsilon_1 + \varepsilon_2 - \varepsilon_3.
$$

$$
\varphi_3(e_1 - e_2) = 0, \quad \varphi_3(e_2) = 0, \quad \varphi_3(e_2 + e_3) = 1. \\[4mm]
\varphi_3(e_1) = \varphi_3(e_1 - e_2) + \varphi_3(e_2) = 0 \\
\varphi_3(e_2) = 0, \\
\varphi_3(e_3) = \varphi_3(e_2 + e_3) - \varphi_3(e_2) = 1. \\[4mm]
\varphi_3 = \varepsilon_3.
$$

## Prob