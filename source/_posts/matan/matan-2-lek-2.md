---
title: 「Матан-2」Лекция-2
date: 2024-09-17 14:31:25
tags:
 - матан
 - 数学分析
 - ru
categories:
 - Матан-2
permalink: matan-2-lek-2
mathjax: true
---

###  Кратные интегралы

#### Теорема 2.1 (необходимое условие интегрируемости)

> $I$ - замкнутый брус, $f\in R(I)\Rightarrow f$ - ограничена на $I$.

<!--more-->

##### Доказательство
От противного.
1. $f\in R(I)\Rightarrow \exists A\in\mathbb{R}$, что $\forall \varepsilon>0\ \exists \delta>0\ \forall (\mathbb{T},\xi):\Delta_\mathbb{T}<\delta\ \Rightarrow\ |\sigma(f,\mathbb{T},\xi)-A|<\varepsilon$.

$A$ - конечное число, $A-\varepsilon\leqslant \sigma_f\leqslant A+\varepsilon$,
$\sigma_f$ - ограничено.

2. Пусть $f$ не ограничена на $I$ и $f\in R(I)$. $\forall \varepsilon>0\ \exists \delta>0\ \forall (\mathbb{T},\xi):\Delta_\mathbb{T}<\delta$, где $\mathbb{T}=\\{I_i\\}^k_{i=1}$, $\exists i_0$: $f$ не ограничена на $I_{i_0}$,
тогда $\sigma_f=\sum\limits_{i\neq i_0}f(\xi_i)|I_i|+f(\xi_{i_0})|I_{i_0}|\Rightarrow \sigma_f$ может принимать в зависимости от выбора $\xi_{i_0}$ любые сколько угодно большие значения(малые значения).

Из 1 и 2 получаем противоречие.

#### Свойства кратного интеграла

##### 1. Линейность: 

$$f,g\in R(I),\forall \alpha,\beta\in\mathbb{R}\Rightarrow \alpha f+\beta g\in R(I)$$
$$\int\limits_{I}(\alpha f+\beta g)=\alpha\int\limits_{I}fdx+\beta\int\limits_{I}gdx$$

**Доказательство**

$f\in R(I)\Rightarrow \forall \varepsilon>0\ \exists \delta_1>0\ \forall (\mathbb{T},\xi):\Delta_\mathbb{T}<\delta_1: |\sigma_f-A_f|<\frac{\varepsilon}{|\alpha|+|\beta|+1}$

$g\in R(I)\Rightarrow \forall \varepsilon>0\ \exists \delta_2>0\ \forall (\mathbb{T},\xi):\Delta_\mathbb{T}<\delta_2: |\sigma_g-A_g|<\frac{\varepsilon}{|\alpha|+|\beta|+1}$

$\delta=\min(\delta_1,\delta_2)$
 
$\forall (\mathbb{T},\xi):\Delta_\mathbb{T}<\delta$:

$$
\begin{align*}
|\sigma_{(\alpha f+\beta g)}-\alpha A_f-\beta A_g|&=|\alpha\sigma_f+\beta\sigma_g-\alpha A_f-\beta A_g|\\\\&
\leqslant |\alpha||\sigma_f-A_f|+|\beta||\sigma_g-A_g|\\\\&
<(|\alpha|+|\beta|)\frac{\varepsilon}{|\alpha|+|\beta|+1}<\varepsilon
\end{align*}
$$

##### 2. Монотонность

$f,g\in R(I),f\leqslant g$ на $I\Rightarrow \int\limits_{I}fdx\leqslant\int\limits_{I}gdx$

**Доказательство**

Условие аналогично линейности.

$$A_f-\varepsilon<\sigma_f\leqslant\sigma_g<\sigma_g<A_g+\varepsilon$$

$$A_f<A_g+2\varepsilon$$

Это верно $\forall\varepsilon>0$, $\varepsilon\ll 1$

$$A_f\leqslant A_g$$

##### 3. Оценка интеграла(сверху)

$f\in R(I)$, тогда $|\int\limits_{I}fdx|\leqslant\sup\limits_{I}|f|\cdot|I|$

**Доказательство**

$$\inf\limits_{I}f<f<\sup\limits_{I}f$$

$$\sup\limits_{I}|f|=\max\\{|\inf\limits_{I}f|,|\sup\limits_{I}f|\\}-\sup\limits_{I}|f|\leqslant f\leqslant\sup\limits_{I}|f|$$

Интегрируем

$$-\int\limits_{I}\sup\limits_{I}|f|dx\leqslant\int\limits_{I}fdx\leqslant\int\limits_{I}\sup\limits_{I}|f|dx$$

### Мера нуль по Лебегу

#### Определение 2.1

> Мн-во $M\subset\mathbb{R}^n$ будем называть мн-вом меры нуль по Лебегу, если $\forall\varepsilon>0$,  
>  существует не более чем счетный набор(замк.) брусов $\\{I_i\\}$: $M\subset\bigcup\limits_{i}I_i$ и $\sum\limits_{i}|I_i|<\varepsilon$.

##### Пример

Точка $x_0\in\mathbb{R}^n$ - мн-во меры нуль по Лебегу.

**Доказательство**

$x_0=(x_{01},\ldots,x_{0n})$, $I=[x_{01}-d;x_{01}+d]\times\ldots\times[x_{0n}-d;x_{0n}+d]$

$$I=\prod\limits_{i=1}^n[x_{0i}-d;x_{0i}+d]=(2d)^n<\varepsilon\Rightarrow d<\frac{\sqrt[n]{\varepsilon}}{2}$$

Возьмем $d=\frac{\sqrt[n]{\varepsilon}}{3}$.

#### Свойства мн-ва меры нуль по Лебегу

##### 1. в определеное мн-во меры нуль можно исправить открытые брысы

**Доказательство**

1\) Пусть $M\subset\mathbb{R}^n$ - мн-во меры нуль по Лебегу, тогда 
 $\forall\varepsilon>0\ \exists\\{I_i\\}$ - набор закрытых брусов: $$I_i=[a^i_1;b^i_1]\times\ldots\times[a^i_n;b^i_n]$$

Пусть $D_i=[\frac{a^i_1+b^i_1}{2}-(b^i_1-a^i_1); \frac{a^i_1+b^i_1}{2}+(b^i_1-a^i_1)]\times\ldots\times$ - открытый брус.

$|D_i|=2^n|I_i|$, чтобы $\sum\limits_{i}|D_i|<\varepsilon$, нужно $\sum\limits_{i}|I_i|<\frac{\varepsilon}{2^n}$.

2\) $\forall\varepsilon>0:\ \\{I_i\\}$ - набор открытых брусов, $M\subset I_i$ и $\sum\limits_{i}|I_i|<\varepsilon$.

Далее $\overline{I_i}$ - добавлены границы к $I_i\Rightarrow|\overline{I_i}|=|I_i|$, $I_i\subset\overline{I_i}$,
 тогда верно $M\subset I_i\subset\overline{I_i}$ и $\sum\limits_{i}|\overline{I_i}|<\varepsilon$, значит $M$ - мн-во меры нуль по Лебегу.