# LaTeX

## 使用Latex的好处

对于撰写数学论文的我来说，使用Latex最大的好处其实是更容易编辑数学公式。其次才是简化排版和参考文献编排。

## 有用的工具

- `latexdiff` and `git latexdiff` 用于检查不同版本之间的差异
- `latexpand` 用来展开多文件latex以及去掉中间注释

## 数学公式示例

行内公式使用 `\(...\)`，例如 \(a^2+b^2=c^2\)。行间公式使用单独一行的 `\[...\]`：

\[
E=mc^2
\]

希腊字母：

\[
\alpha,\ \beta,\ \Gamma,\ \Delta
\]

对齐公式：

\[
\begin{aligned}
f(x) &= x^2 + 1 \\
f'(x) &= 2x
\end{aligned}
\]

矩阵：

\[
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}
\]

导数和偏导数：

\[
\frac{dy}{dx}, \qquad \frac{\partial f}{\partial x}
\]

### 公式编号与引用

MathJax 使用 AMS 编号规则。下面的未加星号 `equation` 环境会自动编号。引用命令需要放在行内公式定界符中；直接写在普通文本中的引用不会被当前配置处理：

引用示例：式 \(\ref{eq:quadratic}\) 的编号为 1，括号形式为 \(\eqref{eq:quadratic}\)；解为 \(x=\pm1\)。

\begin{equation}
x^2 - 1 = 0
\label{eq:quadratic}
\end{equation}


