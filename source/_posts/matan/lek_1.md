---
title: 「Матан-2」Лекция-1
date: 2024-09-10 11:20:11
tags:
  - матан
  - 数学分析
  - ru
categories:
  - Матан-2
mathjax: true
---

###  Кратные интегралы

**Опр 1.1**
> Замкнутым брусом (промежутком, коор. пром.), называется мн-во:  
> $I=\\{x\in\mathbb{R}^n\mid a_i\leqslant x_i \leqslant b_i, i=1..n\\}$

**Опр 1.2**
> Мерой бруса будем называть его объем: $\mu(I)=|I|=\prod\limits_{i=1}^n(b_i-a_i)$
 
**Св-ва меры бруса в $\mathbb{R}^n$**

1. Однородность: $\mu(I_{\lambda a, \lambda b})=\lambda^n\mu(I_{a,b})$, где $a=(a_1,..,a_n), b=(b_1,..,b_n)$, $\lambda \geqslant 0$
2. Аддитивность: $I=\bigcup\limits_{i=1}^n I_i$, $I_i$ - непересекающиеся брусы, тогда $|I|=\sum\limits_{i=1}^n|I_i|$
3. Монотонность: $I\subset \bigcup\limits_{i=1}^n I_i$, тогда $|I|\leqslant \sum\limits_{i=1}^n|I_i|$

<!--more-->

**Опр 1.3**
> $I$ - замкнутый невырожденный брус и $I=\bigcup\limits_{i=1}^n I_i$, $I_i$ - непересекающиеся брусы, 
> тогда набор $\mathbb{T}=\\{I_i\\}^k_{i=1}$ - разбиение бруса $I$.

**Опр 1.4**
> Диаметром произвольного ограниченного мн-ва $M\subset \mathbb{R}^n$ называется
> $d(M)=\sup\limits_{x,y\in M}||x-y||$, где $||x-y||=\sqrt{\sum\limits_{i=1}^n(x_i-y_i)^2}$ - евклидова расстояние.

**Опр 1.5**
> Масштабом разбиения $\mathbb{T}=\\{I_i\\}^k_{i=1}$ бруса $I$ называется
> число $\delta(\mathbb{T})=\Delta_\mathbb{T}=\max\limits_{i=1..k}d(I_i)$.

---
$\forall I_i$ выбраны точки $x_i\in I_i$

**Опр 1.6**
> Набор $\xi=\\{x_i\\}^k_{i=1}$ называется отмеченными точками. 
 
**Опр 1.7**
> $(\mathbb{T},\xi)$ - размеченное разбиение.

---
$I$ - невыр. замкн. брус, $f:I\to \mathbb{R}$ - определена на $I$.

**Опр 1.8**
> Интегральной суммой Римана функции $f$ на $(\mathbb{T},\xi)$ называется
> величина $\sigma(f,\mathbb{T},\xi):=\sum\limits_{i=1}^kf(\xi_i)|I_i|$

**Опр 1.9**
> Будем говорить, что функция $f$ интегрируема (по Риману) на замкнутом брусе $I$, если
> $\exists A\in\mathbb{R}$, что $\forall \varepsilon>0\ \exists \delta>0\ \forall (\mathbb{T},\xi):\Delta_\mathbb{T}<\delta\ \Rightarrow\ |\sigma(f,\mathbb{T},\xi)-A|<\varepsilon$.

Тогда 

$$
A=\int_I f(x)dx=\int_I\dots\int f(x_1,..,x_n)dx_1\dots dx_n
$$

Обозначение: $f\in R(I)$

---
**Пример**
1. $f=const$.

$\forall (\mathbb{T},\xi):\sigma(f,\mathbb{T},\xi)=\sum\limits_{i=1}^k const\cdot|I_i|=const |I|$
$$
\int_I f(x)dx=const\cdot|I|
$$

2. Неинтегрируемая функция

$I=[0,1]^n$
$$
f=\begin{cases}
1, \forall i=1..n,x_i\in\mathbb{Q}\\\\
0, x_i\notin\mathbb{Q}
\end{cases}
$$

- $\forall \mathbb{T}$ всегда можно выбрать $\xi_i\in\mathbb{Q}$, тогда для такого
$(\mathbb{T},\xi)$, $\sigma(f,\mathbb{T},\xi)=\sum\limits_{i=1}^k 1\cdot|I_i|=|I|=1$

- $\forall \mathbb{T}$ всегда можно выбрать $\xi_i\notin\mathbb{Q}$, тогда для такого 
$(\mathbb{T},\xi)$, $\sigma(f,\mathbb{T},\xi)=\sum\limits_{i=1}^k 0\cdot|I_i|=0$

Поэтому $f$ неинтегрируема на $I$.

3. $\int\int\limits_{0\leqslant x\leqslant 1,0\leqslant y\leqslant 1}xydxdy$

Разделим кварад на $n^2$ маленьких квадратов. В каждом квадрате выберем точку $(x_i,y_i)$.
$$
    \sigma(f,\mathbb{T},\xi)=\sum\limits_{i=1}^n\sum\limits_{j=1}^n \frac{i}{n}\cdot\frac{j}{n}\cdot\frac{1}{n^2}=
    \frac{1}{n^4}\sum\limits_{i=1}^n\sum\limits_{j=1}^n ij=\frac{1}{n^4}\left(\sum\limits_{i=1}^n i\right)\left(\sum\limits_{j=1}^n j\right)=\frac{(n+1)^2n^2}{4n^4}\to\frac{1}{4}
$$