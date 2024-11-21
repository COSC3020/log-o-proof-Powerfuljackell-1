# Asymptotic Equivalences

"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice." 
Discussed the theory of log in class with Alex Craig, where he mentioned that different bases scale values.
https://www.khanacademy.org/math/algebra2/x2ec2f6f830c9fb89:logs/x2ec2f6f830c9fb89:change-of-base/a/logarithm-change-of-base-rule-intro

In addition I will include my prior work from my past assignment: https://github.com/COSC3020/log-o-proof-Powerfuljackell

Let a, b and n be constants greater than or equal to 0
Given the Change of Base Rule of Log: $\log_{a}n = \log_{c}n / \log_{c}a$
Let a = 5 and c = 2 so that $\log_{5}n = \log_{2}n / \log_{2}5$
The properites of big O nullifies constants, thus removing $1 / \log_{2}5$-->

Commented out to return to later. This is because within the formal definition of $O$ $T(n)$ only needs to be less than or equal to $c \cdot f(n) \forall n \geq n_0$ to be included so when comparing c to that of $f(n) \forall n \geq n_0$ as $n \to \infty$ f(n) will always be larger than c
Given $T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$, 
For all f(n): $\lim_{n \to \infty}c \cdot f(n) = f(n)$

Plugging in $(\log_{2} n) and (\log_{5} n)$

$\log_{2} n \in O(\log n) \iff \exists c, n_0: \log_{2} n \leq c \cdot \log n \forall n \geq n_0$

$\log_{5} n \in O(\log n) \iff \exists c, n_0: \log_{5} n \leq c \cdot \log n \forall n \geq n_0$

Since $log_{2} = \frac{1}{\log 2} \cdot \log n$ via the change of base

$\log_{2} n \in O(\log n) \iff \exists c, n_0: \frac{1}{\log 2} \cdot \log n \leq c \cdot \log n \forall n \geq n_0$

Since $log_{5} = \frac{1}{\log 5} \cdot \log n$ via the change of base

$\log_{5} n \in O(\log n) \iff \exists c, n_0: \frac{1}{\log 5} \cdot \log n \leq c \cdot \log n \forall n \geq n_0$

So long as there is a c that is greater than or equal too the constant values of $\frac{1}{\log 2} and \frac{1}{\log 5}$ respectfully, then they both can be disregarded as both resulting values will be less than or equal to that of c, meaning that via $O(\log n)$; $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$



In the lectures, we said that logarithms with different bases don't affect the
asymptotic complexity of an algorithm. Prove that $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$. Use the mathematical definition of $O$ -- do a formal proof,
not just the intuition.

I have started with the formal definition of $O$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$

Looking at the relationship between multiple inputs into both $\log_{2} n)$ and $\log_{5} n$
| Input for n              | $\log_{2} n)$  |    $\log_{5} n$      |
|----------------------------|:-----------:|------------------------|
| 1                  |      0      |     0    |
| 2                  |      2      |     0.431    |
| 3                  |       1.585     |     0.683    |
| 4                  |      2      |     0.861    |
| 5                  |      2.322      |      1   |
| 6                  |      2.585      |     1.113    |
| 7                  |      2.807      |      1.209    |

By analyzing the change of base rule of log, I noticed that ultimately all forms of log can be converted into $\log_{a} n = \frac{\log_{x} n}{\log_{x} a}$ where x can be an arbitrary or chosen input. 
From this, we can determine that the base of a log is constantly scaling and so therefore can be disregarded just as constants are disregarded in analysis, as they have very little impact on the asymptote.
