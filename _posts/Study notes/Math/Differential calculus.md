---
title: Statistics and Probability
date: 2022-07-08
update: 2022-07-08
categories:
- Study notes
- Math
tags: Differential calculus
description: 
---

### Limits and continuity

- One-sided limits
    - $\lim\limits_{x\to1^-}f(x)$: approach 1 from left
    - $\lim\limits_{x\to1^+}f(x)$: approach 1 form right
- Limits epsilon delta definition
    - $\lim\limits_{x\to x_0}f(x) = L$
    - if for every $\epsilon > 0$ there exists $\delta > 0$ such that for all x
        - $0 < |x -x_0| < \delta \implies |f(x) - L| < \epsilon$
    - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220712220547.png" width="200" height="">
- Limits not exist if
    - Left-hand limit $\not =$ Right-hand limit
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220712213026.png" width="100" height="">
    - Vertical asymptote
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220712213034.png" width="100" height="">
    - Violent osillation
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220712213726.png" width="100" height="">
- Limit properties
    - $\lim\limits_{x \to c}(f(x) \pm g(x)) = \lim\limits_{x \to c}f(x) \pm \lim\limits_{x \to c}g(x)$ 
    - $\lim\limits_{x \to c}(f(x) * g(x)) = \lim\limits_{x \to c}f(x) * \lim\limits_{x \to c}g(x)$ 
    - $\lim\limits_{x \to c}(f(x) / g(x)) = \lim\limits_{x \to c}f(x) / \lim\limits_{x \to c}g(x)$ $(denominator \neq 0) $
    - $\lim\limits_{x \to c}kf(x) = k\lim\limits_{x \to c}f(x)$ 
    - $\lim\limits_{x \to c}(f(x))^u = (\lim\limits_{x \to c}f(x))^u$ 
- Limits of composite functions
    - $\lim\limits_{x \to c}f(g(x)) = f(\lim\limits_{x \to c}g(x)))$ 
        - $\lim\limits_{x \to c}g(x) = L$  exists
        - $f(x)$ is continous at $L$
    - Limits can still exist if theorem cannot apply
        - See if two one-sided limits equal
    - At both sides
        - If $g(x) \uparrow$ , direction of $f(g(x))$ same as $f(x)$
        - If $g(x) \downarrow$ , direction of $f(g(x))$ opposite to $f(x)$
- Continuous function
    - Continuous
        - $f(x)$ is countinuous at $x = a \iff \lim\limits_{x \to a}f(x) = f(a)$
        - Get limit by direct substitution if the function is continuous
    - Continuous over an interval
        - $f(x)$ continuous over $[a, b] \iff \lim\limits_{x \to a^+} f(x) = f(a) \  \& \ \lim\limits_{x \to b^-} f(x) = f(b)$ 
- Limits of piecewise function
    - Absolute value - change to piecewise function
- Limits by factoring, conjugates & trig identities
    - $\lim\limits_{x \to 1} \dfrac {x^2 - x -2}{x^2 - 2x -3}$ to $\lim\limits_{x \to 1} \dfrac {x -2}{x -3}$

    - $\lim\limits_{\theta \to -{\frac{\pi}{4}}} \dfrac{1 + \sqrt{2} \sin\theta}{\cos{2\theta}}$ to $\lim\limits_{\theta \to -{\frac{\pi}{4}}} \dfrac{1 + \sqrt{2 \sin\theta}} {(1+\sqrt{2}\sin\theta)(1-\sqrt{2}\sin\theta)}$
    - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220714220524.png" width="450" height="">
- Squeeze theorem (sandwich theorem)
    - $f(x) \le g(x) \le h(x)$
        - If $\lim\limits_{x \to c} f(x) = \lim\limits_{x \to c} h(x) = L$
        - $\lim\limits_{x \to c} g(x) = L$
        
    - e.g. $\lim\limits_{x \to 0} \dfrac{\sin{x}}{x}$
        - From geometry
        - <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220714231832.png" width="200" height="">
        - $|{\dfrac{\sin{x}}{2}}| \le |\dfrac{x}{2}| \le |\dfrac {\tan{x}}{2}|$

        - $1 \ge \dfrac{\sin{x}}{x} \ge \cos{x}$
- Infinite limit & limit at infinity
    - Reasoning limit at infinity
        - Find dominating term at nominator and denominator, ignore insignificant ones
        - Find the range of divided part，use inequality equation
        - Change the form by factoring, conjugates and trig identities
- Intermedia value theorem
    - If $f(x)$ continuous on an interval $[a, b]$
        - For every $L$ value between $f(a)$ and $f(b)$, there exists some $c$ in $[a, b]$ for which $f(c) = L$

### Derivative

- Definition  
    - $f'(x) = \dfrac {dy}{dx} = \dfrac{d}{dx}f(x)$

    - $f'(x) = \lim\limits_{x\to{\Delta x}}\dfrac{f(x + \Delta x) - f(x)}{\Delta x}$
        - Find tangent line using definition
            - If two function has a tangent, derivative of a point is same
    - Differentiability and continuity
        - If f is differentiable at x = c $\implies$ f is continuous at x = c
        - Not differentiable
            - Vertical tangent
            - Not continuous
            - Sharp trim
- Basic rules
    - $\dfrac{d}{dx}[x^n] = n \cdot x^{n-1}$, $(n \neq 0)$

    - $\dfrac{d}{dx}[a] = 0$, A is constant

    - $\dfrac{d}{dx}[kf(x)] = kf'(x)$

    - $\dfrac{d}{dx}[f(x) \pm g(x)] = f'(x) \pm g'(x)$

    - $\dfrac{d}{dx}[\sin x] = \cos x$

    - $\dfrac{d}{dx}[\cos x] = - \sin x$ 

        - Prove:
            - $\lim\limits_{x \to 0}\dfrac{\sin x}{x} = 1$

            - $\lim\limits_{x \to 0}\dfrac{1 - \cos x}{x} = 0$

            - Then use definition to prove
    - $\dfrac{d}{dx}[e^x] = e^{x}$
        - $ e = \lim\limits_{n \to \infty} (1+ \frac{1}{n})^n = \lim\limits_{n \to 0}(1+n)^{\frac{1}{n}}$
    - $\dfrac{d}{dx}[\ln x] = \dfrac{1}{x}$

    - $\dfrac{d}{dx}[f(x)g(x)] = f'(x)g(x) + f(x)g'(x)$

    - $\dfrac{d}{dx} [\dfrac {f(x)}{g(x)}] = \dfrac {f'(x)g(x) - f(x)g'(x)}{[g(x)]^2}$
