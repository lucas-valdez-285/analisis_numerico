## Series y potencias de Taylor
### Ejercicio 1
* **a -** Obtener la serie de Taylor centrada en 0 para la función  $f(x)=\ln(x+1)$. Escribir la serie usando la notación de sumatorias. Dar una expresión para el resto cuando la serie es truncada en $k$ términos
$$
\begin{array}{l}
f(x)=\sum_{k=0}^{n} \frac{1}{k!}f^{(k)}(c)(x-c)^{k}+E_{n}(x) \\
\begin{array}{|l|}
\hline f(x)=\ln(x+1) \\
f(x)^{(1)}=(x+1)^{-1} \\
f(x)^{(2)}=(-1)(x+1)^{-2} \\
f(x)^{(3)}=2(-1)^{2}(x+1)^{-3} \\
f(x)^{(4)}=2\cdot 3(-1)^{3}(x+1)^{-4} \\
f(x)^{(5)}=2\cdot 3\cdot 4(-1)^{4}(x+1)^{-5} \\
\vdots \\
f(x)^{(n)}=(n-1)!(-1)^{n-1}(x+1)^{-n} \\
\hline
\end{array} \\
\text{Demostración:} \\
CB \\
f(x)^{(1)}=0!(-1)^{0}(x+1)^{-1}=(x+1)^{-1}\checkmark \\
CR \\
f(x)^{(k)}\Longrightarrow f(x)^{(k+1)} \\
f(x)^{(k+1)}=(k+1-1)!(-1)^{(k+1-1)}(x+1)^{-(k+1)}=k!(-1)^{k}(x+1)^{-k-1} \\
\frac{d}{dx}f(x)^{(k)}=(k-1)!(-1)^{k-1}(x+1)^{-k-1}k(-1)=k!(-1)^{k}(x+1)^{-k-1} \checkmark \\
 \\
\text{Polinomio de Taylor } c=0 \\
\displaystyle P_{n,0}(x)=\sum_{k=0}^{n} \frac{1}{k!}f(0)^{(k)}x^{k}=\ln(1)+\sum_{k=1}^{n} \frac{1}{k!}(k-1)!(-1)^{k-1}x^{k}=\sum_{k=1}^{n} (-1)^{k-1}\frac{x^{k}}{k} \\
\text{Serie de Taylor} \\
\displaystyle\boxed{f(x)=\sum_{k=1}^{\infty}(-1)^{k-1} \frac{x^{k}}{k}} \\
\text{Resto de Taylor} \\
\displaystyle E_{k}(x)= \frac{1}{(k+1)!}k!(-1)^{k}(\xi+1)^{-(k+1)}x^{k+1}=\frac{(-1)^{k}x^{k+1}}{(\xi+1)^{k+1}(k+1)} \\
\displaystyle \boxed {E_{k}(x)=\frac{(-1)^{k}x^{k+1}}{(\xi+1)^{k+1}(k+1)}} \quad \text{para algun }\xi\text{ entre 0 y x}
\end{array}
$$
* **b -** Estimar el número de términos que deberán incluirse en la serie para aproximar $\ln(1,5)$ con un margen de error no mayor que $10^{-10}$
$$
\begin{array}{l}
\ln(1,5)=f(0,5) \\
10^{-10}>|E_{k}(0,5)| \\
|E_{k}(0,5)|=\dfrac{1}{(\xi+1)^{k+1}(k+1)2^{k+1}} \quad\text{para algun }\xi\text{ entre 0 y 0,5} \\
\text{Tomamos el valor de }\xi\text{ que hace mas grade el error }\xi=0 \\
|E_{k}(0,5)|\leq \dfrac{1}{(k+1)2^{k+1}}<10^{-10} \iff 10^{10}<(k+1)2^{k+1} \\
\text{Estimacion} \\
\log_{2}(k+1)+(k+1)>\log_{2}(10^{10}) \\
\log_{2}(k+1)+k+1>33,219280949 \\
\log_{2}(k+1)+k>32,219280949 \quad\text{tomemos }k=28 \\
4,86+28>32,21 \\
32,86>32,21 \\
\boxed{k=28}
\end{array}
$$
### Ejercicio 2
Si la serie para $\ln(x)$ centrada en $x=1$ se corta después del término que corresponde a $(x-1)^{1000}$ y después se usa para calcular $\ln(2)$ ¿Qué cota se le puede imponer al error?
$$
\begin{array}{l}
f(x)=\ln(x) \\
f(x)^{(1)}=x^{-1} \\
f(x)^{(2)}=(-1)x^{-2} \\
f(x)^{(3)}=2!(-1)^{2}x^{-3} \\
f(x)^{(4)}=3!(-1)^{3}x^{-4} \\
f(x)^{(n)}=(n-1)!(-1)^{n-1}x^{-n} \\
f(x)^{n+1}=n!(-1)^{n}x^{-(n+1)} \\
\text{Serie de taylor }c=1 \\
\displaystyle f(x)=\sum_{k=0}^{ \infty} \frac{f^{(k)}}{k!} (1)(x-1)^{k} \\
E_{n}(x)= \dfrac{1}{(n+1)!}f^{(n+1)}(\xi)(x-1)^{n+1} \\
E_{n}(x)=\dfrac{(-1)^{n}(x-1)^{n+1}}{(n+1)\xi^{n+1}}\quad\text{Para algun }\xi\text{ entre x y 1} \\
E_{n}(2)=\dfrac{(-1)^{n}}{(n+1)\xi^{n+1}}\quad\text{Para algun }\xi \text{ entre 2 y 1} \\
|E_{1000}(2)|=\left|\dfrac{(-1)^{1000}}{1001\cdot 1^{1001}}\right|=\dfrac{1}{1001}\quad\text{Tomando }\xi=1\text{ para maximizar el error} \\
\boxed{|E_{1000}(2)|< \dfrac{1}{1001}}
\end{array}
$$
### Ejercicio 3
Verificar la siguiente igualdad y mostrar que la serie converge en el intervalo $-e<z\leq e$
$$
\ln(e+x)=1+\sum_{k=1}^{\infty}\frac{(-1)^{k-1}}{k}\left( \frac{x}{e} \right)^{k}
$$
$$
\begin{array}{l}
f(x)=\ln(e+x)\\
f^{(1)}(x)=(e+x)^{-1} \\
f^{(2)}(x)=(-1)(e+x)^{-2} \\
f^{(3)}(x)=2!(-1)^{2}(e+x)^{-3} \\
f^{(n)}(x)=(n-1)!(-1)^{n-1}(e+x)^{-n}\quad n \in\mathbb{N} \\
{\text{Serie de taylor }} c=0 \\
\displaystyle f(x)=\sum_{k=0}^{\infty} \frac{1}{k!}f^{(k)}(0)(x)^{k}=1+\sum_{k=1}^{\infty} \frac{1}{k}(-1)^{k-1}(e)^{-k}x^{k} \\
\displaystyle f(x)=1+\sum_{k=1}^{\infty} \frac{(-1)^{k-1}}{k}\left( \frac{x}{e} \right)^{k}\therefore QED \\ \\
\text{Convergencia} \\
\displaystyle \frac{d}{dx}f(x)=\sum_{k=1}^{\infty} (-1)^{k-1}\left( \frac{x}{e} \right)^{k-1}\quad\text{Serie geometrica con }r=-\frac{x}{e} \\ \\
\text{Radio de convergencia } \\
|r|<1\Longrightarrow \dfrac{|x|}{e}<1\Longrightarrow |x|<e \Longrightarrow \\
-e<x<e \\
\text{Analizamos los Extremos} \\
\displaystyle f(e)=1+\sum_{k=1}^{\infty} \frac{(-1)^{k-1}}{k}\left( \frac{e}{e} \right)^{k}=1+\sum_{k=1}^{\infty} \frac{(-1)^{k-1}}{k} \\
\text{Serie Armonica alternada, por criterio de Leibinz la serie converge en x=e} \\
\displaystyle f(-e)=1+\sum_{k=1}^{\infty} \frac{(-1)^{k-1}}{k}\left( -\frac{e}{e} \right)^{k}=1+\sum_{k=1}^{\infty}- \frac{1}{k} \\
\text{Serie Armonica, la serie diverge en x=-e} \\
\textbf{Intervalo de convergencia} \\
\boxed{-e<x\leq e}
\end{array}
$$
### Ejercicio 4
Desarrollar la función $\sqrt{ x }$ en la serie de potencias centrada en $x=1$ y verificar que utilizando la aproximación lineal de dicha función se puede aproximar $\sqrt{ 0,9999999995 }$ con un error no mayor que $10^{-10}$
$$
\begin{array}{l}
f(x)=\sqrt{x}=x^{1/2} \\
f(1)=1 \\
f^{(1)}(x)=\dfrac{x^{-1/2}}{2}\\
f^{(1)}(1)=\dfrac{1}{2} \\
f^{(2)}(x)= -\dfrac{x^{-3/2}}{4} \\
\text{Serie de Taylor } c=1 \\
\displaystyle f(x)=\sum_{k=0}^{1} \frac{1}{k!}f^{(k)}(1)(x-1)^{k}+E_{n}(x)=1+\frac{1}{2}(x-1)+E_{n}(x)=\frac{1}{2}x
+\frac{1}{2}+E_{1}(x) \\
E_{1}(x)=\dfrac{1}{2!}f^{(2)}(\xi)(x-1)^{2}=-\dfrac{1}{8\sqrt{\xi^{3}}}(x-1)^{2}\quad\text{Para algun }\xi\text{ entre x y 1} \\
|E_{1}(0,9999999995)|\thickapprox\dfrac{1}{8}(-5\cdot 10^{-10})^{2}=\dfrac{1}{8}25\cdot 10^{-20} \\
|E_{1}(0,9999999995)|\thickapprox 3,125\cdot 10^{-20}<10^{-10} \\
|E_{1}(0,9999999995)|<10^{-10}
\end{array}
$$
## Notación $O$ y $o$
### Ejercicio 5 
Verificar que las siguiente sucesiones convergen a 1 y analizar su velocidad de convergencia:
* **a -** $x_{n}=1+\left( \dfrac{1}{2} \right)^{n}=1+\dfrac{1}{2^{n}}$
$$
\begin{array}{l}
1+\dfrac{1}{2^{n}}\longrightarrow 1\text{ cuando }n\longrightarrow\infty\\
\left| \dfrac{1}{2^{n+1}}\right|\leq c\left| \dfrac{1}{2^{n}}\right|^{2} \\
\dfrac{2^{2n}}{2^{n+1}}\leq c\iff \dfrac{2^{2n}}{2^{n+1}}\leq c\iff 2^{n-1}\leq c\quad\text{concluimos que la serie no tine orden cuadratico}\\
\left| \dfrac{1}{2^{n+1}}\right|\leq c\left| \dfrac{1}{2^{n}}\right| \\ 
\dfrac{1}{2^{n+1}}\leq c \dfrac{1}{2^{n}}\iff \dfrac{2^{n}}{2^{n+1}}\leq c\iff \dfrac{1}{2}\leq c\quad\text{como }0< \dfrac{1}{2}<1\text{ la convergenica es lineal}
\end{array}
$$
* **b -** $x_{n}=1+\dfrac{1}{2^{2^{n}}}$
$$
\begin{array}{l}
x_{n}=1+\dfrac{1}{2^{2^{n}}}\longrightarrow 1\text{ cuando }n\longrightarrow\infty \\
\left|1+\dfrac{1}{2^{2^{n+1}}}-1\right|\leq c\left|1+\dfrac{1}{2^{2^{n}}}-1\right|^{2}\iff  \\
\dfrac{(2^{2^{n}})^{2}}{2^{2^{n+1}}}\leq c\iff\dfrac{2^{2^{n+1}}}{2^{2^{n+1}}}\leq c\iff 1\leq c \\
\text{como c es positivo, la serie converge cuadraticamente}
\end{array}
$$
* **c -** $x_{n}=1+\dfrac{1}{n^{n}}$
$$
\begin{array}{l}
x_{n}=1+\dfrac{1}{n^{n}}\longrightarrow 1\text{ cuando }n\longrightarrow\infty \\
\left|1+\dfrac{1}{(n+1)^{n+1}}-1\right|\leq c\left|1+\dfrac{1}{(n)^{n}}-1\right| \iff \\
\dfrac{1}{(n+1)^{n+1}}\leq c\dfrac{1}{n^{n}}\iff \dfrac{n^{n}}{(n+1)^{n+1}}\leq c\iff \dfrac{n^{n}}{(n+1)^{n}} \dfrac{n^{n}}{(n+1)} < c \\
\iff \left( \dfrac{n}{n+1} \right)^{n}\left( \dfrac{n^{n}}{n+1} \right)<c  \\
\lim_{ n \to \infty }\left( \dfrac{n}{n+1} \right)^{n}\left( \dfrac{n^{n}}{n+1} \right) =e\cdot 0=0  \\
\implies\text{la convergencia es por lo menos superlineal} \\
\end{array}
$$
### Ejercicio 6
Para $n$ fijo, demostrar que $\displaystyle\sum_{k=0}^{n}x^{k}=\frac{1}{1-x}+o(x^{n})$ cuando $x\longrightarrow 0$
$$
\begin{array}{l}
\displaystyle\sum_{k=0}^{n}x^{k}=\frac{1}{1-x}+\varepsilon_{n}x^{n}
\end{array}
$$