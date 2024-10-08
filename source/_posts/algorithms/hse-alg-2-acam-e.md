---
title: 「HSE АиСД-2」E. Цензура - Ахо-Корасик
date: 2024-09-12 01:11:20
updated: 2024-09-12 01:11:20
tags:
  - algorithms
  - АиСД-2
  - ru
  - Ахо-Корасик
  - AC自动机
categories: [Algorithms, АиСД-2]
permalink: hse-alg-2-acam-e
mathjax: true
published: false
---

> 给定一个长度为 $1\leq n\leq 100$ 的字符集，$0 \leq p \leq 10$ 个长度不超过 $\min(m,10)$ 的禁止串，
> 求有多少个长度为 $1\leq m\leq 100$ 
的字符串，满足其不包含任何禁止串。答案对 $10^9+7$ 取模。

> Задан набор символов длиной $1 \leq n \leq 100$,
>  $0 \leq p \leq 10$ запрещённых строк длиной не более $\min(m,10)$.  Требуется найти количество строк длиной $1 \leq m \leq 100$, 
>  которые не содержат ни одной запрещённой строки. 
> Ответ требуется вывести по модулю $10^9 + 7$.

<!--more-->

### 题解

考虑在AC自动机上dp。设 $dp[i][j]$ 为当前长度为 $i$，以状态 $j$ 结尾的合法字符串的个数。
由于我们需要考虑结尾的后缀并不多，只需要禁止串的前缀和其他剩下的，所以我们可以在AC自动机上dp。

#### dp初始化

我们初始化`dp[0][0]=1`，表示长度为 $0$ 以状态 $0$ 结尾的合法字符串只有一个，即空串。

#### dp

如果当前长度为$i$的字符串不以禁止串前缀结尾，那么这就是状态`dp[i][0]`，
我们使用根节点来表示当前字符串不以任意禁止串前缀结尾，换句话说就是**没有匹配到任何禁止串**。
根节点的意义也是这样的。

反之如果当前长度为$i$的字符串以禁止串结尾，那么这就是状态`dp[i][j]`，`j`是自动机中的一个状态。

当现在的状态是`dp[i][j]`时，我们尝试在结尾添加字符`c`，设`k`是自动机中从状态`j`通过字符`c`转移到的状态。
`k`要么是状态`j`的最长后缀，要么是状态`0`，即没有匹配到任何禁止串的前缀。我们判断`k`是否为禁止串，如果不是，
那么就可以从`dp[i][j]`转移到`dp[i+1][k]`，也就是`dp[i+1][k]+=dp[i][j]`，否则我们不做任何操作。

最后答案就是所有`dp[m][j]`的和。

### Решение

Рассмотрим дп на автомате Ахо-Корасика. Обозначим $dp[i][j]$ как количество допустимых строк длины $i$, 
которые заканчиваются состоянием $j$.

Так как нам нужно учитывать не так много суффиксов в конце строки, 
достаточно рассмотреть только префиксы запрещённых строк и другие оставшиеся суффиксы, 
поэтому можно использовать динамическое программирование на автомате Ахо-Корасика.

#### Инициализация dp

Мы инициализируем `dp[0][0]=1`, что означает,
что существует только одна допустимая строка длины $0$, 
заканчивающаяся состоянием $0$, а именно пустая строка.

#### dp

Если строка длины $i$ не заканчивается префиксом запрещённой строки, 
то это соответствует состоянию `dp[i][0]`. Мы используем корневую вершину, 
чтобы обозначить, что текущая строка не заканчивается префиксом запрещённой строки. 
Иными словами, **запрещённая строка не была найдена**. 
Корневая вершина как раз и имеет такой смысл.

В противном случае, если строка длины $i$ заканчивается запрещённой строкой, 
то это соответствует состоянию `dp[i][j]`, где $j$ — одно из состояний автомата.

Когда мы находимся в состоянии `dp[i][j]`, мы пытаемся добавить символ `c` в конец строки. 
Пусть $k$ — это состояние автомата, в которое переходит состояние $j$ при добавлении символа `c`. 
Состояние $k$ либо является самым длинным суффиксом состояния $j$, либо это состояние $0$, 
то есть не было найдено никакого префикса запрещённой строки. 
Мы проверяем, является ли $k$ запрещённой строкой. Если нет, то мы можем перейти из `dp[i][j]` в `dp[i+1][k]`, 
то есть `dp[i+1][k] += dp[i][j]`, иначе не совершаем никаких действий.

Ответом будет сумма всех значений `dp[m][j]`.

