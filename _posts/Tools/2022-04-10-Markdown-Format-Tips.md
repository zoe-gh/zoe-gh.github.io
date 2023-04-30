---
title: "Markdown Format Tips"
last_modified_at: 2022-06-09
categories: 
- Tools
tags: 
- Markdown
toc: true
---

## Code

### In-line code

~~~
`code`
~~~

--> Display: `code`

### Fenced code block

~~~
    ~~~
    code 1
    code 2
    code 3
    ~~~
~~~

--> Display:

~~~
code 1
code 2
code 3
~~~

### Italic and bold in code

~~~
<code>-\*- coding: <i>encoding</i> -\*-</code>
~~~

--> Display: <code>-\*- coding: <i>encoding</i> -\*-</code>

## Table

~~~
| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |
~~~

--> Display:
| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |

## Link

~~~
[Main](https://zoe-gif.github.io/)
~~~

--> Display:
[Main](https://zoe-gif.github.io/)

## Math

- [Katex documentation](https://katex.org/docs/supported.html)
    - [Geek letter](https://katex.org/docs/supported.html#letters-and-unicode)
    - [Logic](https://katex.org/docs/supported.html#logic-and-set-theory)
    - [Operator](https://katex.org/docs/supported.html#operators)

### Inline math
~~~
$J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m} {m! \Gamma(m+\alpha+1)} {\left({\frac{x}{2}}\right)}^{2m + \alpha} \text {, <-- eample}$
~~~

--> Display: $J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m} {m! \Gamma(m+\alpha+1)} {\left({\frac{x}{2}}\right)}^{2m + \alpha} \text {, <-- eample}$

<br>

### Block math

~~~
$$ J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m} {m! \Gamma(m+\alpha+1)} {\left({\frac{x}{2}}\right)}^{2m + \alpha} \text {, <-- eample} $$
~~~

--> Display: $$ J_\alpha(x) = \sum_{m=0}^\infty \frac{(-1)^m} {m! \Gamma(m+\alpha+1)} {\left({\frac{x}{2}}\right)}^{2m + \alpha} \text {, <-- eample} $$

<br>

### Superscript and underscript

~~~
$$ x^{y^z} = (1 + e^x_1)^{-2xy^{w_0}}$$
~~~
--> Display
$$ x^{y^z} = (1 + e^{x_1})^{-2xy^w}$$

<br>

### Brackets & parentheses

- Use `\left` & `\right` for big parentheses
- `( \big( \Big( \bigg( \Bigg(` --> $( \big( \Big( \bigg( \Bigg($

~~~
$$ f(x,y,z) = 3y^2z \left( 3+\frac{7x+5}{1+y^2} \right)$$
~~~

--> Display
$$ f(x,y,z) = 3y^2z \left( 3+\frac{7x+5}{1+y^2} \right)$$

<br>

### Fraction

- `\frac {nominator} {denominator}` or `\frac {nominator \over denominator}`

~~~ 
$$\frac {a+1}{b-1} \quad or \quad {a+1 \over b-1}$$
~~~

--> Display
$$\frac {a+1}{b-1} \quad or \quad {a+1 \over b-1}$$

- Quick fraction by `\frac ab` --> $\frac ab$

<br>

### Square root

- `\sqrt [root index]{squared}`
- Default root index is 2

<br>

### Ellipsis

- `\dots`--> $\dots$
- `\underbrace{braced content}_{text}`
- `\overbrace(braced content)^{text}`

~~~
$$ f(x_1, x_2, \underbrace{\ldots}_\ldots, x_n) = x_1^2 + x_2^2$$
~~~

--> Display:
$$ f(x_1, x_2, \underbrace{\ldots}_{bottom}, x_n) = x_1^2 + x_2^2 + \underbrace{\cdots}_{center} + x_n^2$$

<br>

### Intergral

- `\int_{lower limit}^{upper limit} {integrand}`

~~~
$$ \int_0^1 {x^2}{dx}$$
~~~

--> Display:
$$ \int_0^1 {x^2}{dx}$$

<br>

### Limit

- `\lim_{variable \to limit} expression`
- `\infty`

~~~
$$\lim_{n \to \infty} \frac{1}{n(n+1)}$$
~~~

--> Display:
$$\lim_{n \to \infty} \frac{1}{n(n+1)}$$

### Sum & product

- `\sum_{lower}^{upper} expression` --> 
$\sum_{n=1}^{\infty} n^2+1$
- `\prod_{lower}^{upper} expression` --> 
$\prod_{\substack{0<i<m\\0<j<n}}$

### Common use

|Code|Example|Code|Example| 
|:---:|:---:|:---:|:---:| 
|`\le`|$\le$|`\not =`|$\not =$|
|`\ge`|$\ge$|`\hat{\theta}`|$\hat{\theta}$|
|`approx`|$\approx$|`\bar{y}`|$\bar{y}$|
|`\sub`|$\sub$|`\supset`|$\supset$|
|`\sube`|$\sube$|`\supsete`|$\supseteq$|
|`\mod`|$x \mod a$|`\pm`|$\pm$|


