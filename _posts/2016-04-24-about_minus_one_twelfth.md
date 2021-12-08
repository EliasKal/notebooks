---
layout: post
title: About -1/12
author: elias
markdown: kramdown
---
			

These notes are about the famous and odd result that the sum of all natural numbers is $$-1/12$$:

$$
1 + 2 + 3 + \ldots = - \frac{1}{12}
$$

or

$$
\sum_{n=0}^{\infty} n = - \frac{1}{12}.
$$

This result and a proof was presented in a [Numberphille video](https://www.youtube.com/watch?v=w-I6XTVZXww). In this video, a reference to a book [<a href="#ref_02">2</a>] about string theory is made, which makes use of this result (see page 22 of [<a href="#ref_02">2</a>]). In this book, the author arrives at the result by introducing a smoothing factor in the sum, as was also done by Casimir in his paper about the Casimir effect [<a href="#ref_03">3</a>]. However, Casimir did not calculate the value of the infinite sum, but the value of the difference between the infinite sum and an infinite integral, and this was found to be proportional to $$-1/12$$, up to some physical constants.

In a simplified version, which is different in form (as also shown by [<a href="#ref_08">8</a>]) but similar in concept, Casimir calculated the difference between

$$
S = \sum_{x=0}^{\infty} x
$$

and

$$
I = \int_{0}^{\infty} x dx.
$$
			
In order to solve this, he introduced a smoothing factor $$e^{-\delta x}$$ in both the sum and the integral:

$$
S' = \sum_{x=0}^{\infty} x e^{-\delta x}, \quad I' = \int_{0}^{\infty} x e^{-\delta x} dx.
$$

This smoothing factor has the property that when $$\delta$$ tends to $$0$$, the factor becomes $$1$$, and the sum and integral return to their original forms. Thus, this factor can be introduced in order for a result to be reached, and then $$\delta$$ can be set to $$0$$, in order to remove the effect of the smoothing factor.
			
Casimir used the Euler-Maclaurin formula to evaluate the difference $$S' - I'$$, which, letting $$f(x) = x e^{-\delta x}$$, is [<a href="#ref_04">4</a>]:

$$
S' - I' = \sum_{k=1}^p \frac{B_k}{k!} \left ( f^{(k-1)}(\infty) - f^{(k-1)}(0) \right ),
$$

where $$p$$ is how many times function $$f$$ can be differentiated.
			
However, here we will take another course and evaluate the sum and the integral separately and then compute their difference, in a way similar to what is shown in [<a href="#ref_05">5</a>].
			
The integral $$I'$$ is a special case of

$$
\int_{0}^{\infty} x^n e^{-\delta x} dx = \frac{\Gamma(n+1)}{\delta^{n+1}},
$$

for $$n = 1$$. So

\begin{equation}
	\label{integral_final}
	I' = \int_{0}^{\infty} x e^{-\delta x} dx = \frac{\Gamma(2)}{\delta^2} = \frac{1}{\delta^2}.
\end{equation}
			
The sum $$S'$$ is, also according to [<a href="#ref_06">6</a>], computed as:

$$
S' = \sum_{x=0}^{\infty} x e^{-\delta x} = \frac{e^{\delta}}{(e^{\delta} - 1)^2}.
$$

Using the definition of the hyperbolic sine, the above sum can also be written as:

\begin{equation}
	\label{sum_sinh}
	S' = \frac{1}{4 \sinh^2 \frac{\delta}{2}}.
\end{equation}
			
Eq. (\ref{sum_sinh}) can be expanded in a Laurent series, as follows:

\begin{equation}
	\label{sum_final}
	S' = \frac{1}{4 \sinh^2 \frac{\delta}{2}} = \frac{1}{\delta^2} - \frac{1}{12} + O(\delta^2),
\end{equation}

where $$O(\delta^2)$$ is a polynomial of $$\delta$$ of order higher or equal to $$2$$. As a note, the above result of Eq. (\ref{sum_final}) can be obtained using WolframAlpha [<a href="#ref_07">7</a>] and entering the following:

```
laurent series ((sinh(x/2))^(-2))/4
```
			
Using Eqs. (\ref{integral_final}) and (\ref{sum_final}), the difference $$S' - I'$$ is:

\begin{equation}
	\label{difference_final}
	S' - I' = - \frac{1}{12} + O(\delta^2).
\end{equation}
			
After this result is obtained, it is time to set $$\delta$$ back to zero and get the result of the original difference $$S - I$$. In Eq. (\ref{difference_final}), the terms of the sum and the integral that tend to infinity as $$\delta$$ tends to $$0$$ are canceled out, and the high-order polynomial term $$O(\delta^2)$$ tends to $$0$$ as $$\delta$$ tends to $$0$$, leaving only the finite term $$-1/12$$:

\begin{equation}
	\label{difference_final_2}
	S - I = - \frac{1}{12}.
\end{equation}
			
According to [<a href="#ref_03">3</a>], this finite negative result gives rise to an attractive force between two parallel conducting plates, which is the Casimir effect. However, as seen from Eq. (\ref{difference_final_2}), it is the difference $$S - I$$ that has a value of $$-1/12$$, not the infinite sum $$S$$, as stated in [<a href="#ref_02">2</a>]. This is also mentioned in [<a href="#ref_08">8</a>], where the Riemann zeta function is used to calculate the infinite sum $$S$$.  It is said that zeta function renormalization reaches the same result as that derived by Casimir, who used the above regularization, but <span style="font-style: italic;">without subtracting the sum from the integral</span>, which "suggests an important physical intuition for zeta renormalization: using the analytic continuation [...] in some sense corresponds to subtracting the electromagnetic field's inherent contribution to the ground state energy".
			
This also corresponds to what is mentioned in [<a href="#ref_09">9</a>], that $$-1/12$$ is what is left if one removes the infinity from the sum $$S$$. Similarly, in [<a href="#ref_10">10</a>], it is mentioned that the values of the Riemann zeta function for negative integers, such as $$\zeta(-1) = -1/12$$, are "nothing more than the constant terms of the asymptotic expansion of the smoothed partial sums".

