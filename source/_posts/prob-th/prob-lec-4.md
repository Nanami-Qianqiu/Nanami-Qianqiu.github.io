---
title: 「Теорвер」Лекция-4
date: 2024-09-23 10:52:43
updated: 2024-09-23 10:52:43
tags: [Теория вероятностей]
permalink: prob-lec-4
mathjax: true
published: true
---

### Независимость случайных величин
#### Определение
> СВ $X$, $Y$ независимы,...

#### Теорема

##### Метатеорема
> Дискретные $X$, $Y$ независимы $\iff P(X=x, Y=y)=P(X=x)P(Y=y)$, другими словами $\\{X=x\\}$ и $\\{Y=y\\}$ независимы.

<!--more-->

##### Доказательство

Любое док-во про дискретные СВ получается перестановкой слагаемых.

**Пример**

$A=\\{x\\}, $ $B=\\{y\\}$

$\widetilde{A}=A\cap\text{Image}(X)$, $\widetilde{B}=B\cap\text{Image}(Y)$

$$\begin{align*}
P(X\in A, Y\in B)&=P(X\in\widetilde{A}, Y\in\widetilde{B})\\\\&=
\sum\limits_{x\in\widetilde{A}}\sum\limits_{y\in\widetilde{B}}P(X=x, Y=y)\\\\&=
\sum\limits_{x\in\widetilde{A}}\sum\limits_{y\in\widetilde{B}}P(X=x)P(Y=y)\\\\&=
\sum\limits_{x\in\widetilde{A}}P(X=x)\sum\limits_{y\in\widetilde{B}}P(Y=y)
\end{align*}$$

#### Теорема
> СВ $X$ и $Y$ независимы, если и только если $\forall f: \mathbb{R}\to\mathbb{R}$, 
> $\forall g: \mathbb{R}\to\mathbb{R}$, $$E(f(X)g(Y))=E(f(X))E(g(Y))$$

**Пример**

$E(X^2Y^2)=E(X^2)E(Y^2)$

##### Следствие

Если $X$, $Y$ независимы, то $E(XY)=E(X)E(Y)$

### Эксперимент

Подбрасываем монетку $n$ раз. $P(H)=p$, $P(T)=q=1-p$

Броски независимы, $X$ - кол-во H, $Y$ - кол-во T. $p=\frac{1}{2}$

---

- $\Omega = \\{HHHHH,\dots,TTTTT\\}$ - язык мн-ва
- [HT]{5} - язык регулярного выражения
- $f(H,T) = HHHHH+\dots+TTTTT=(H+T)^5$ - язык функции

$P(X=3),P(X=3,Y=2),E(X),E(X^2),E(X^2Y)$ - ?

---

#### $P(X=3)$

HHHTT, HTHHT, THHHT, ...

$f(\frac{1}{2}h,\frac{1}{2}t)=h^3t^2(\frac{1}{2})^5+h^3t^2(\frac{1}{2})^5+\dots$

---

#### $P(X=3, Y=2)$

$$\frac{\partial^5f(\frac{1}{2}h,\frac{1}{2}t)}{\partial h^3\partial t^2}=5!(\frac{1}{2})^5$$

$$P(X=3,Y=2)=\frac{1}{3!2!}\frac{\partial^5f(\frac{1}{2}h,\frac{1}{2}t)}{(\partial h)^3(\partial t)^2}|_{h=0,t=0}$$

---

#### $E(X)$
$$f = \dots + HHHTT + \dots$$
$$E(X)=\dots+(\frac{1}{2})^5\cdot 3 + \dots$$

Пусть $T=\frac{1}{2}$, $H=\frac{1}{2}h$, тогда 
$$E(X)=\frac{\partial f(\frac{1}{2}h,\frac{1}{2})}{\partial h}|_{h=1}$$

---

#### $E(X^2)$
$f=\dots+HHHTT+\dots$

$f(\frac{1}{2}e^h,\frac{1}{2})=\dots+(\frac{1}{2})^5\cdot e^{3h}+\dots$

$$\frac{\partial^2f(\frac{1}{2}e^h,\frac{1}{2})}{\partial h^2}=\dots+(\frac{1}{2})^5 e^{3h}\cdot 3^2+\dots$$
$$E(X^2)=\dots+(\frac{1}{2})^5 e^{3h}\cdot 3^2+\dots=\frac{\partial^2f(\frac{1}{2}e^h,\frac{1}{2})}{\partial h^2}|_{h=0}$$

---

#### $E(X^2Y)$

$$E(X^2Y)=\frac{\partial^3f(\frac{1}{2}e^h,\frac{1}{2}e^t)}{\partial h^2\partial t}|_{h=0,t=0}$$

---

### Упражнение

Подбрасываем монетку до 3 H. $P(H)=\frac{1}{3}$, $P(T)=\frac{2}{3}$

$X$ - кол-во H, $Y$ - кол-во T.

$E(Y^2)$ - ?

- $f=(1+T+T^2+\dots)\cdot H\cdot (1+T+T^2+\dots)\cdot H\cdot (1+T+T^2+\dots)H=\frac{1}{1-T}H\frac{1}{1-T}H\frac{1}{1-T}H$
$$E(Y^2)=\frac{\partial^2f(\frac{1}{3},\frac{2}{3}e^t)}{\partial t^2}|_{t=0}$$

---

### Формальные определения

#### Определение
> СВ $X$ имеет биноимиальное распределение $X\sim Bin(n,p)$, если $P(X=k)=C_n^kp^k(1-p)^{n-k}, то есть 
> вероятность получить ровно $k$ успехов в серии из $n$ не зависимых испытаний с вероятностью успеха $p$.

#### Определение
> СВ $X$ имеет геометрическое распределение $X\sim Geom(p)$, 
> если $P(X=k)=(1-p)^{k-1}p$, то есть 
> вероятность получить $k$ неудач до первого успеха в серии независимых испытаний с вероятностью успеха $p$.

#### Определение
> СВ $X$ имеет отрицательное биномиальное распределение $X\sim NBin(r,p)$, если $P(X=k)=C_{k-1}^{r-1}p^r(1-p)^{k-r}$, то есть
> вероятность получить ровно $k$ неудач до получения $r$-го успеха по счету.

#### Определение
> Если $X$ принимает целые неотр. значения, то $g(t)$ - фунция производящая вероятности, если 
> $$g(t)=E(t^X)=\sum\limits_{x}P(X=x)t^x$$

- $g'(1)=E(X)$

#### Определение
> $m(t)$ - фунция производящая моменты, если
> $$m(t)=E(e^{tX})=\sum\limits_{x}P(X=x)e^{tx}$$

- $m'(0)=E(X)$
- $m''(0)=E(X^2)$

#### Определение
> СВ $X$ и $Y$ принимают неотр. значения. $g(t,s)$ - фунция производящая вероятности, если
> $$g(t,s)=E(t^Xs^Y)=\sum\limits_{x,y}P(X=x,Y=y)t^xs^y$$

$$\frac{1}{3!2!}\frac{\partial^5g(t,s)}{\partial t^3\partial s^2}|_{t=0,s=0}=P(X=3,Y=2)$$

#### Определение
> $m(t,s)$ - фунция производящая моменты для $t$ и $s$, если
> $$m(t,s)=E(e^{tX}s^Y)=\sum\limits_{x,y}P(X=x,Y=y)e^{tx}s^y$$