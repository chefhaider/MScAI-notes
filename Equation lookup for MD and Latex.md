Creating a comprehensive table guideline for writing mathematical equations in Markdown involves covering various types of mathematical expressions and how to format them using LaTeX syntax. Below is a table that serves as a guide:


| **Expression**           | **Markdown Syntax**                                  | **Rendered Output**                                      |
| ------------------------ | ---------------------------------------------------- | -------------------------------------------------------- |
| **Inline Math**          | `\(\text{equation}\)`                                | $$ \text{equation} $$                                    |
| **Block Math**           | `$$ \text{equation} $$`                              | $$ \text{equation} $$                                    |
| **Subscript**            | `\(a_i\)`                                            | $$ a_i $$                                                |
| **Superscript**          | `\(a^i\)`                                            | $$ a^i $$                                                |
| **Fraction**             | `\(\frac{a}{b}\)`                                    | $$ \frac{a}{b} $$                                        |
| **Square Root**          | `\(\sqrt{a}\)`                                       | $$ \sqrt{a} $$                                           |
| **Nth Root**             | `\(\sqrt[n]{a}\)`                                    | $$ \sqrt[n]{a} $$                                        |
| **Sum**                  | `\(\sum_{i=1}^n a_i\)`                               | $$ \sum_{i=1}^n a_i $$                                   |
| **Integral**             | `\(\int_{a}^{b}su f(x) \, dx\)`                      | $$ \int_{a}^{b} f(x) \, dx $$                            |
| **Partial Derivative**   | `\(\frac{\partial f}{\partial x}\)`                  | $$ \frac{\partial f}{\partial x} $$                      |
| **Greek Letters**        | `\(\alpha, \beta, \gamma, \ldots\)`                  | $$ \alpha, \beta, \gamma, \ldots $$                      |
| **Limits**               | `\(\lim_{x \to \infty} f(x)\)`                       | $$ \lim_{x \to \infty} f(x) $$                           |
| **Matrices**             | `\(\begin{bmatrix} a & b \\ c & d \end{bmatrix}\)`   | $$ \begin{bmatrix} a & b \\ c & d \end{bmatrix} $$       |
| **Align Equations**      | `\begin{align} a &= b + c \\ d &= e + f \end{align}` | $$ \begin{align} a &= b + c \\ d &= e + f \end{align} $$ |
| **Brackets**             | `\( (a + b) \)`                                      | $$ (a + b) $$                                            |
| **Parentheses**          | `\( \left( a + b \right) \)`                         | $$ \left( a + b \right) $$                               |
| **Curly Braces**         | `\{a + b\}`                                          | $$ \{a + b\} $$                                          |
| **Absolute Value**       | `\(\left                                             | $\left a \lright$                                        |
| **Vector Notation**      | `\(\vec{a}\)`                                        | $$ \vec{a} $$                                            |
| **Overline**             | `\(\overline{a}\)`                                   | $$ \overline{a} $$                                       |
| **Hat Notation**         | `\(\hat{a}\)`                                        | $$ \hat{a} $$                                            |
| **Dot Notation**         | `\(\dot{a}\)`                                        | $$ \dot{a} $$                                            |
| **Double Dot Notation**  | `\(\ddot{a}\)`                                       | $$ \ddot{a} $$                                           |
| **Text in Math**         | `\( \text{some text} \)`                             | $$ \text{some text} $$                                   |
| **Binomial Coefficient** | `\(\binom{n}{k}\)`                                   | $$ \binom{n}{k} $$                                       |

### Examples

#### Inline Math

```markdown
Einstein's equation: \(E = mc^2\)
```
$$
E = mc^2
$$

#### Block Math

```markdown
$$
\int_{-\infty}^{\infty} e^{-x^2} \, dx = \sqrt{\pi}
$$
```
$$
\int_{-\infty}^{\infty} e^{-x^2} \, dx = \sqrt{\pi}
$$

#### Matrix

```markdown
$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$
```
$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$

#### Align Equations

```markdown
$$
\begin{align}
a &= b + c \\
d &= e + f
\end{align}
$$
```
$$
\begin{align}
a &= b + c \\
d &= e + f
\end{align}
$$

This table and examples should help you format a wide range of mathematical expressions in Markdown.