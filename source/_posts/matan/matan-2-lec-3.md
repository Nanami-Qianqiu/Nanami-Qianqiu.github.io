---
title: 「Матан-2」Лекция-3
date: 2024-10-01 11:14:14
updated: 2024-10-01 11:14:14
tags:
    - матан
    - 数学分析
    - ru
categories:
    - Матан-2
permalink: matan-2-lec-3
mathjax: true
---

### Продолжение лекции 2

#### Свойство меры Лебега 2

> $M$ - мн-во меры нуль по Лебегу, $L\subset M\Rightarrow L$ - мн-во меры нуль по Лебегу.

##### Доказательство

$\forall \varepsilon > 0\ \exists$ не более чем счётное $\\{I_n\\}$, $L\subset M \subset \bigcup I_i$, $\sum|I_i| < \varepsilon$.

#### Свойство меры Лебега 3

> Не более чем счётное объединение множеств меры нуль по Лебегу - множество меры нуль по Лебегу.

##### Доказательство

$\\{M_i\\}$ - не более чем счётное набор, где $\forall i\ M_i$ - мн-во меры нуль по Лебегу.

Значит $\forall i,\ \forall \varepsilon_i,\ \exists$ не более чем счётное $\\{I_j^i\\}$, $M_i\subset \bigcup I_j^i$ и $\sum\limits_j|I_j^i| < \varepsilon_i$, $\varepsilon_i = \frac{\varepsilon}{2^i}$.

Тогда $M=\bigcup M_i$, $M\subset \bigcup\limits_{i,j}I_j^i$, хотим, чтобы $\forall \varepsilon>0,\ \sum\limits_{i,j}|I_j^i|=\sum\limits_i\sum\limits_j|I_j^i|<\sum\limits_i\varepsilon_i<\varepsilon$.

- Случай 1. $\\{M_i\\}$ - конечное.

    $\varepsilon_1+\dots+\varepsilon_N= \frac{N}{N+1}\varepsilon < \varepsilon$.

    $\varepsilon_i = \frac{\varepsilon}{N+1}$.

### Топология в $\mathbb{R}^n$

$M\subset\mathbb{R}^n$ 

#### Определение 3.1

> $r_0\in M$ - внутренняя точка $M$, если $\exists \varepsilon > 0$, что $B_{\varepsilon}(r_0)\subset M$.

#### Определение 3.2

> $x_0\notin M,x_0\in\mathbb{R}^n\setminus M$ - внешняя точка $M$, если $\exists \varepsilon > 0$, что $B_{\varepsilon}(x_0)\subset\mathbb{R}^n\setminus M$.

#### Определение 3.3

> $x_0\in\mathbb{R}^n$ - граничная точка $M$, если $\forall \varepsilon > 0$, $$\begin{cases}B_{\varepsilon}(x_0)\cap M\neq\varnothing\\\\
> B_{\varepsilon}(x_0)\cap(\mathbb{R}^n\setminus M)\neq\varnothing\end{cases}$$

#### Определение 3.4

> $x_0\in M$ - изолированная точка $M$, если $\exists \varepsilon > 0$, что $\mathring{B}_{\varepsilon}(x_0)\cap M = \varnothing$.

#### Определение 3.5

> $x_0\in\mathbb{R}^n$ - предельная точка $M$, если $\forall \varepsilon > 0$, $\mathring{B}_{\varepsilon}(x_0)\cap M\neq\varnothing$.

#### Определение 3.6

> $x_0\in\mathbb{R}^n$ - точка прикосновения для $M$, если $\forall \varepsilon > 0$, $B_{\varepsilon}(x_0)\cap M\neq\varnothing$.

#### Определение 3.7

> Мн-во все точек прикосновения для $M$ называется замыканием $M$ и обозначается $\overline{M}$.

##### Пример

-  $M=(0;1)\cup(1;2]\cup\{3\}$

    $\overline{M}=[0;2]\cup\{3\}$

#### Определение 3.8

> $M$ - открытое мн-во, если $\forall x\in M$, $x$ - внутренняя точка $M$.

#### Определение 3.9

> $M\subset\mathbb{R}^n$ - замкнутое мн-во, если $\mathbb{R}^n\setminus M$ - открытое мн-во.

##### Замечание

- $\varnothing$ - открытое и замкнутое мн-во.

#### Определение 3.10

> $M$ - называется ограниченным, если $\exists x_0\in\mathbb{R}^n$ и $\exists r>0$, что $M\subseteq B_r(x_0)$.

#### Определение 3.11

> Мн-во $K\subset\mathbb{R}^n$ - компактное мн-во, если из любого его покрытия открытыми мн-вами можно выделить конечное подпокрытие.

##### Замечание

- если хоть для одного покрытия нельзя выделить конечное подпокрытие, то мн-во не является компактным.

#### Теорема(критерий замкнутости)

> $M$ - замкнутое $\Leftrightarrow$ $M$ содержит все свои предельные точки.

##### Доказательство

От противного.

$\Rightarrow$(необходимость)
- Пусть $x_0$ - предельная точка $M$, но $x_0\notin M$, тогда $x_0\in\mathbb{R}^n\setminus M$.
- по условию $M$ - замкнутое, т.е. $\mathbb{R}^n\setminus M$ - открытое, все его точки внутренние $\Rightarrow$ для $x_0$ из пункта 1 $\exists r>0$, что $B_r(x_0)\subset\mathbb{R}^n\setminus M$, но
$x_0$ - предельная, $\forall \varepsilon > 0$, $\mathring{B}_{\varepsilon}(x_0)\cap M\neq\varnothing$, значит $B_r(x_0)\cap M\neq\varnothing$, противоречие.