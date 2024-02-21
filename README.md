# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1. 
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
\\
$$

$$
\begin{gather*}
& \mathrm{T}(n) = \mathrm{T}(\frac{n}{13}) + 5 \\
\implies & \mathrm{T}(n) = \mathrm{T}(\mathrm{T}(\frac{n}{169}) + 5) + 5 \\
\implies & \mathrm{T}(n) = \mathrm{T}(\frac{n}{169}) + 10 \\
\implies & \mathrm{T}(n) = \mathrm{T}(\frac{n}{2197} + 10) + 5 \\
\implies & \mathrm{T}(n) = \mathrm{T}(\frac{n}{2197}) + 15 \\
& \vdots \\
\implies & \mathrm{T}(n) = \mathrm{T}(\frac{n}{13^{i}}) + 5i \\
& \text{Let $i = \log_{13}(n)$ to find the base case...} \\
\implies & \mathrm{T}(n) = \mathrm{T}(\frac{n}{13^{\log_{13}(n)}}) + 5\log_{13}(n) \\
\implies & \mathrm{T}(n) = \mathrm{T}(1) + 5\log_{13}(n) \\
\implies & \mathrm{T}(n) = 5\log_{13}(n) + 1 \\
\therefore & \mathrm{T}(n) \in \mathrm{\Theta}(\log(n)) \\
&& \blacksquare
\end{gather*}
$$



2. 
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

$$
\begin{gather*}
& \mathrm{T}(n) = 13\mathrm{T}(\frac{n}{13}) + 5 \\
\implies & \mathrm{T}(n) = 13(13\mathrm{T}(\frac{n}{\frac{13}{13}}) + \frac{5}{13}) + 5 \\
\implies & \mathrm{T}(n) = 169\mathrm{T}(\frac{n}{169}) + 10 \\
\implies & \mathrm{T}(n) = 169(13\mathrm{T}(\frac{n}{\frac{169}{13}} + \frac{5}{13})) + 10 \\
\implies & \mathrm{T}(n) = 2197\mathrm{T}(\frac{n}{2197}) + 15 \\
& \vdots \\
\implies & \mathrm{T}(n) = 13^{i}\mathrm{T}(\frac{n}{13^{i}}) + 5i \\
& \text{Let $i = \log_{13}(n)$ to get to the base case...} \\
\implies & \mathrm{T}(n) = 13^{\log_{13}(n)}\mathrm{T}(\frac{n}{13^{\log_{13}(n)}}) + 5\log_{13}(n) \\
\implies & \mathrm{T}(n) = n \cdot \mathrm{T}(1) + 5\log_{13}(n) \\
\implies & \mathrm{T}(n) = n \cdot 5\log_{13}(n) + 1 \\
\therefore & \mathrm{T}(n) \in \mathrm{\Theta}(n) \\
&& \blacksquare \\
\end{gather*}
$$



3. 
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$



$$
\begin{gather*}
& \mathrm{T}(n) = 13\mathrm{T}(\frac{n}{13}) + 2n \\
\implies & \mathrm{T}(n) = 13(13\mathrm{T}(\frac{n}{\frac{13}{13}}) + \frac{2n}{13}) + 2n \\
\implies & \mathrm{T}(n) = 169\mathrm{T}(\frac{n}{169}) + 4n \\
\implies & \mathrm{T}(n) = 169(13\mathrm{T}(\frac{n}{\frac{169}{13}}) + \frac{2n}{13}) + 4n \\
\implies & \mathrm{T}(n) = 2197\mathrm{T}(\frac{n}{2197}) + 6n \\
& \vdots \\
\implies & \mathrm{T}(n) = 13^{i}\mathrm{T}(\frac{n}{13^{i}}) + (i \cdot 2)n \\
& \text{Let $i = \log_{13}(n)$ to get to the base case...} \\
\implies & \mathrm{T}(n) = 13^{\log_{13}(n)}\mathrm{T}(\frac{n}{13^{\log_{13}(n)}}) + (\log_{13}(n) \cdot 2)n \\
\implies & \mathrm{T}(n) = n \cdot \mathrm{T}(1) + 2n\log_{13}(n) \\
\implies & \mathrm{T}(n) = 2n\log_{13}(n) + n \\
\therefore & \mathrm{T}(n) \in \mathrm{\Theta}(n\log(n)) \\
&& \blacksquare \\
\end{gather*}
$$
