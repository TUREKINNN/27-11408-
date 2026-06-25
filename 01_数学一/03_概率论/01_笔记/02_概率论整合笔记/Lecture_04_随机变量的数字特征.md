---
title: Lecture 04 - 随机变量的数字特征
subject: 概率论与数理统计
chapter: 第四章
lecture: 04
created: 2026-06-17
updated: 2026-06-17
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
  - 李永乐660题-概率篇
  - 张宇《概率论与数理统计基础30讲》
  - 《基础过关660题》概率篇
difficulty: 基础
---

# Lecture 04: 随机变量的数字特征

## 一、数学期望

### 1.1 数学期望的定义

<span style="background-color: #ccc1d9">**定义（数学期望）**</span> 

1. **离散型**：设 $X$ 的分布律为 $P\{X = x_i\} = p_i, i = 1, 2, \cdots$，若级数 $\sum_{i=1}^{\infty} x_i p_i$ 绝对收敛，则称

$$E(X) = \sum_{i=1}^{\infty} x_i p_i$$

为 $X$ 的**数学期望**，简称期望或均值。

2. **连续型**：设 $X$ 的概率密度为 $f(x)$，若积分 $\int_{-\infty}^{+\infty} x f(x) dx$ 绝对收敛，则称

$$E(X) = \int_{-\infty}^{+\infty} x f(x) dx$$

为 $X$ 的**数学期望**。

### 1.2 随机变量函数的数学期望

设 $Y = g(X)$，则：

- **离散型**：$E(Y) = \sum_{i=1}^{\infty} g(x_i) p_i$
- **连续型**：$E(Y) = \int_{-\infty}^{+\infty} g(x) f(x) dx$

设 $Z = g(X, Y)$，则：

- **离散型**：$E(Z) = \sum_{i=1}^{\infty} \sum_{j=1}^{\infty} g(x_i, y_j) p_{ij}$
- **连续型**：$E(Z) = \int_{-\infty}^{+\infty} \int_{-\infty}^{+\infty} g(x, y) f(x, y) dx dy$

### 1.3 数学期望的性质

<span style="background-color: #8db3e2">**定理（数学期望的性质）**</span> 

1. **线性性**：$E(aX + b) = aE(X) + b$
2. **可加性**：$E(X + Y) = E(X) + E(Y)$（不要求独立）
3. **独立性**：若 $X$ 与 $Y$ 独立，则 $E(XY) = E(X)E(Y)$
4. **单调性**：若 $X \geq 0$，则 $E(X) \geq 0$；若 $X \geq Y$，则 $E(X) \geq E(Y)$

---

## 二、方差

### 2.1 方差的定义

<span style="background-color: #ccc1d9">**定义（方差）**</span> 设 $X$ 是随机变量，若 $E[(X - E(X))^2]$ 存在，则称

$$D(X) = E[(X - E(X))^2]$$

为 $X$ 的**方差**。称 $\sqrt{D(X)}$ 为 $X$ 的**标准差**或**均方差**。

### 2.2 方差的计算公式

$$D(X) = E(X^2) - [E(X)]^2$$

### 2.3 方差的性质

<span style="background-color: #8db3e2">**定理（方差的性质）**</span> 

1. **非负性**：$D(X) \geq 0$，等号成立当且仅当 $X$ 为常数
2. **齐次性**：$D(aX + b) = a^2 D(X)$
3. **可加性**：$D(X + Y) = D(X) + D(Y) + 2\mathrm{Cov}(X, Y)$
4. **独立性**：若 $X$ 与 $Y$ 独立，则 $D(X + Y) = D(X) + D(Y)$
5. **切比雪夫不等式**：$P\{|X - E(X)| \geq \varepsilon\} \leq \frac{D(X)}{\varepsilon^2}$

---

## 三、协方差

### 3.1 协方差的定义

<span style="background-color: #ccc1d9">**定义（协方差）**</span> 设 $(X, Y)$ 是二维随机变量，若 $E[(X - E(X))(Y - E(Y))]$ 存在，则称

$$\mathrm{Cov}(X, Y) = E[(X - E(X))(Y - E(Y))]$$

为 $X$ 与 $Y$ 的**协方差**。

### 3.2 协方差的计算公式

$$\mathrm{Cov}(X, Y) = E(XY) - E(X)E(Y)$$

### 3.3 协方差的性质

<span style="background-color: #8db3e2">**定理（协方差的性质）**</span> 

1. **对称性**：$\mathrm{Cov}(X, Y) = \mathrm{Cov}(Y, X)$
2. **线性性**：$\mathrm{Cov}(aX + b, Y) = a\mathrm{Cov}(X, Y)$
3. **分配律**：$\mathrm{Cov}(X_1 + X_2, Y) = \mathrm{Cov}(X_1, Y) + \mathrm{Cov}(X_2, Y)$
4. **与方差的关系**：$D(X \pm Y) = D(X) + D(Y) \pm 2\mathrm{Cov}(X, Y)$

---

## 四、相关系数

### 4.1 相关系数的定义

<span style="background-color: #ccc1d9">**定义（相关系数）**</span> 设 $(X, Y)$ 是二维随机变量，$D(X) > 0, D(Y) > 0$，则称

$$\rho_{XY} = \frac{\mathrm{Cov}(X, Y)}{\sqrt{D(X)D(Y)}}$$

为 $X$ 与 $Y$ 的**相关系数**。

### 4.2 相关系数的性质

<span style="background-color: #8db3e2">**定理（相关系数的性质）**</span> 

1. **有界性**：$|\rho_{XY}| \leq 1$
2. **极值条件**：$|\rho_{XY}| = 1$ 当且仅当存在常数 $a, b$，使得 $P\{Y = aX + b\} = 1$
3. **不相关**：若 $\rho_{XY} = 0$，称 $X$ 与 $Y$ **不相关**
4. **独立性与不相关**：独立 $\Rightarrow$ 不相关，但反之不成立（二维正态分布除外）

---

## 五、矩的概念

### 5.1 原点矩

<span style="background-color: #ccc1d9">**定义（原点矩）**</span> 设 $X$ 是随机变量，若 $E(X^k)$ 存在，则称

$$\mu_k = E(X^k)$$

为 $X$ 的**$k$ 阶原点矩**。

### 5.2 中心矩

<span style="background-color: #ccc1d9">**定义（中心矩）**</span> 设 $X$ 是随机变量，若 $E[(X - E(X))^k]$ 存在，则称

$$\nu_k = E[(X - E(X))^k]$$

为 $X$ 的**$k$ 阶中心矩**。

### 5.3 混合矩

<span style="background-color: #ccc1d9">**定义（混合矩）**</span> 设 $(X, Y)$ 是二维随机变量，若 $E(X^k Y^l)$ 存在，则称

$$E(X^k Y^l)$$

为 $X$ 与 $Y$ 的**$k+l$ 阶混合原点矩**。

若 $E[(X - E(X))^k (Y - E(Y))^l]$ 存在，则称

$$E[(X - E(X))^k (Y - E(Y))^l]$$

为 $X$ 与 $Y$ 的**$k+l$ 阶混合中心矩**。

---

## 六、常见分布的数字特征

| 分布 | 记号 | 数学期望 | 方差 |
|------|------|----------|------|
| 0-1分布 | $B(1, p)$ | $p$ | $p(1-p)$ |
| 二项分布 | $B(n, p)$ | $np$ | $np(1-p)$ |
| 泊松分布 | $P(\lambda)$ | $\lambda$ | $\lambda$ |
| 均匀分布 | $U(a, b)$ | $\frac{a+b}{2}$ | $\frac{(b-a)^2}{12}$ |
| 指数分布 | $E(\lambda)$ | $\frac{1}{\lambda}$ | $\frac{1}{\lambda^2}$ |
| 正态分布 | $N(\mu, \sigma^2)$ | $\mu$ | $\sigma^2$ |

---

## 七、典型例题

### 例题1：数学期望的计算（660题第541题）

**题目**：设随机变量 $X$ 的分布律为 $P\{X=k\}=\frac{1}{2^{k}k!(\sqrt{e}-1)}, k=1,2,\cdots$，则 $X$ 的数学期望 $E(X)=$ ____。

**思路**：利用级数展开式计算期望。

**解答**：
$$E(X) = \sum_{k=1}^{\infty} k \cdot \frac{1}{2^k k! (\sqrt{e} - 1)} = \frac{1}{\sqrt{e} - 1} \sum_{k=1}^{\infty} \frac{1}{2^k (k-1)!}$$

$$= \frac{1}{2(\sqrt{e} - 1)} \sum_{k=1}^{\infty} \frac{(1/2)^{k-1}}{(k-1)!} = \frac{1}{2(\sqrt{e} - 1)} e^{1/2}$$

$$= \frac{\sqrt{e}}{2(\sqrt{e} - 1)} = \frac{\sqrt{e}(\sqrt{e} + 1)}{2(e - 1)} = \frac{e + \sqrt{e}}{2(e - 1)}$$

**总结**：利用 $e^x = \sum_{k=0}^{\infty} \frac{x^k}{k!}$ 是计算期望的常用技巧。

---

### 例题2：相关系数的计算（660题第542题）

**题目**：设随机变量 $X$ 服从参数为 3 的泊松分布，$Y \sim N(-1, 2)$ 且 $D(X + Y) = 1$，则 $X$ 与 $Y$ 的相关系数 $\rho =$ ____。

**思路**：利用方差的性质和相关系数定义。

**解答**：
$X \sim P(3)$，则 $D(X) = 3$；$Y \sim N(-1, 2)$，则 $D(Y) = 2$

$$D(X + Y) = D(X) + D(Y) + 2\mathrm{Cov}(X, Y) = 1$$

$$3 + 2 + 2\mathrm{Cov}(X, Y) = 1 \Rightarrow \mathrm{Cov}(X, Y) = -2$$

$$\rho = \frac{\mathrm{Cov}(X, Y)}{\sqrt{D(X)D(Y)}} = \frac{-2}{\sqrt{3 \times 2}} = \frac{-2}{\sqrt{6}} = -\frac{\sqrt{6}}{3}$$

**总结**：方差的可加性公式是解题关键。

---

### 例题3：期望的绝对值计算（660题第543题）

**题目**：设随机变量 $X$ 服从参数为 2 的泊松分布，则 $E(|X - E(X)|) =$ ____。

**思路**：利用泊松分布的性质和期望定义。

**解答**：
$X \sim P(2)$，则 $E(X) = 2$

$$E(|X - 2|) = \sum_{k=0}^{\infty} |k - 2| \cdot \frac{2^k}{k!} e^{-2}$$

$$= |0-2|\cdot\frac{2^0}{0!}e^{-2} + |1-2|\cdot\frac{2^1}{1!}e^{-2} + |2-2|\cdot\frac{2^2}{2!}e^{-2} + \sum_{k=3}^{\infty} (k-2)\cdot\frac{2^k}{k!}e^{-2}$$

$$= 2e^{-2} + 2e^{-2} + 0 + \sum_{k=3}^{\infty} \frac{2^k}{(k-1)!}e^{-2} - 2\sum_{k=3}^{\infty} \frac{2^k}{k!}e^{-2}$$

$$= 4e^{-2} + 2\sum_{m=2}^{\infty} \frac{2^m}{m!}e^{-2} - 2\left(e^2 - e^{-2}(1 + 2 + 2)\right)$$

$$= 4e^{-2} + 2(e - 3e^{-2}) - 2(e - 5e^{-2}) = \frac{4}{e^2}$$

**总结**：利用泊松分布的概率分布律直接计算。

---

### 例题4：协方差的计算（660题第545题）

**题目**：设随机变量 $X_{1}, X_{2}, \cdots, X_{n} (n > 1)$ 独立同分布，且方差为 $\sigma^{2} > 0$，记 $Y_{1} = \sum_{i=2}^{n} X_{i}$ 和 $Y_{n} = \sum_{j=1}^{n-1} X_{j}$，则 $Y_{1}$ 和 $Y_{n}$ 的协方差 $\mathrm{Cov}(Y_{1}, Y_{n}) =$ ____。

**思路**：利用协方差的性质展开计算。

**解答**：
$$\mathrm{Cov}(Y_1, Y_n) = \mathrm{Cov}\left(\sum_{i=2}^{n} X_i, \sum_{j=1}^{n-1} X_j\right)$$

$$= \sum_{i=2}^{n} \sum_{j=1}^{n-1} \mathrm{Cov}(X_i, X_j)$$

由于 $X_i$ 独立，$\mathrm{Cov}(X_i, X_j) = 0$ 当 $i \neq j$，当 $i = j$ 时 $\mathrm{Cov}(X_i, X_i) = D(X_i) = \sigma^2$

$$= \sum_{k=2}^{n-1} \sigma^2 = (n-2)\sigma^2$$

**总结**：协方差对和的分配律是关键。

---

### 例题5：方差的计算（660题第546题）

**题目**：相互独立的随机变量 $X_{1}, X_{2}, \cdots, X_{n}$ 具有相同的方差 $\sigma^{2} > 0$，记 $\overline{X} = \frac{1}{n} \sum_{i=1}^{n} X_{i}$，则 $D(X_{1} - \overline{X}) =$ ____。

**思路**：利用方差的性质计算。

**解答**：
$$D(X_1 - \overline{X}) = D\left(X_1 - \frac{1}{n}\sum_{i=1}^{n}X_i\right) = D\left(\frac{n-1}{n}X_1 - \frac{1}{n}\sum_{i=2}^{n}X_i\right)$$

由于 $X_i$ 独立：
$$= \left(\frac{n-1}{n}\right)^2 D(X_1) + \sum_{i=2}^{n} \left(\frac{1}{n}\right)^2 D(X_i)$$

$$= \frac{(n-1)^2}{n^2}\sigma^2 + \frac{n-1}{n^2}\sigma^2 = \frac{(n-1)^2 + (n-1)}{n^2}\sigma^2 = \frac{(n-1)n}{n^2}\sigma^2 = \frac{n-1}{n}\sigma^2$$

**总结**：$X_1$ 与 $\overline{X}$ 不独立，不能直接用 $D(X-Y) = D(X)+D(Y)$。

---

### 例题6：数学期望的计算（660题第547题）

**题目**：设随机变量 $X$ 服从分布 $E(1)$，记 $Y = \min \{|X|, 1\}$，则 $Y$ 的数学期望 $E(Y) =$ ____。

**思路**：将 $Y$ 分段表示后计算期望。

**解答**：
$X \sim E(1)$，则 $f(x) = e^{-x}, x > 0$

$$Y = \begin{cases} |X|, & |X| \leq 1 \\ 1, & |X| > 1 \end{cases} = \begin{cases} X, & 0 < X \leq 1 \\ 1, & X > 1 \end{cases}$$

$$E(Y) = \int_{0}^{1} x e^{-x} dx + \int_{1}^{+\infty} 1 \cdot e^{-x} dx$$

$$= \left[-xe^{-x}\right]_0^1 + \int_{0}^{1} e^{-x} dx + \left[-e^{-x}\right]_1^{+\infty}$$

$$= -e^{-1} + \left[-e^{-x}\right]_0^1 + e^{-1} = -e^{-1} + (1 - e^{-1}) + e^{-1} = 1 - e^{-1}$$

**总结**：分段函数的期望需要分段积分。

---

### 例题7：方差的计算（660题第548题）

**题目**：设随机变量 $X \sim U(0,3)$，随机变量 $Y$ 服从参数为 3 的泊松分布，且 $X$ 与 $Y$ 的协方差为 -2，则 $D(2X - 3Y + 4) =$ ____。

**思路**：利用方差的性质计算。

**解答**：
$X \sim U(0,3)$，则 $D(X) = \frac{9}{12} = \frac{3}{4}$；$Y \sim P(3)$，则 $D(Y) = 3$

$$D(2X - 3Y + 4) = 4D(X) + 9D(Y) - 12\mathrm{Cov}(X, Y)$$

$$= 4 \times \frac{3}{4} + 9 \times 3 - 12 \times (-2) = 3 + 27 + 24 = 54$$

**总结**：方差对线性组合的公式 $D(aX + bY) = a^2D(X) + b^2D(Y) + 2ab\mathrm{Cov}(X,Y)$。

---

### 例题8：方差的计算（660题第549题）

**题目**：相互独立的随机变量 $X_{1}$ 和 $X_{2}$ 均服从正态分布 $N\left(0, \frac{1}{2}\right)$，则 $D(|X_{1} - X_{2}|) =$ ____。

**思路**：先求 $X_1 - X_2$ 的分布，再计算绝对值的方差。

**解答**：
令 $Z = X_1 - X_2$，由于 $X_1, X_2$ 独立且 $X_i \sim N(0, \frac{1}{2})$，则 $Z \sim N(0, 1)$

$$D(|Z|) = E(Z^2) - [E(|Z|)]^2$$

$$E(Z^2) = D(Z) + [E(Z)]^2 = 1 + 0 = 1$$

$$E(|Z|) = \int_{-\infty}^{+\infty} |z| \cdot \frac{1}{\sqrt{2\pi}} e^{-z^2/2} dz = \sqrt{\frac{2}{\pi}}$$

$$D(|Z|) = 1 - \left(\sqrt{\frac{2}{\pi}}\right)^2 = 1 - \frac{2}{\pi}$$

**总结**：正态分布的线性组合仍为正态分布。

---

### 例题9：方差的计算（660题第550题）

**题目**：设二维随机变量 $(X, Y)$ 的概率密度为

$$f(x, y) = \begin{cases} e^{-x}, & x > 0, 0 < y < 1, \\ 0, & \text{其他}, \end{cases}$$

则 $D(X+Y)=$ ____。

**思路**：先判断独立性，再计算方差。

**解答**：
$$f_X(x) = \int_{0}^{1} e^{-x} dy = e^{-x}, x > 0$$

$$f_Y(y) = \int_{0}^{+\infty} e^{-x} dx = 1, 0 < y < 1$$

$f(x, y) = f_X(x)f_Y(y)$，故 $X$ 与 $Y$ 独立。

$X \sim E(1)$，$D(X) = 1$；$Y \sim U(0,1)$，$D(Y) = \frac{1}{12}$

$$D(X+Y) = D(X) + D(Y) = 1 + \frac{1}{12} = \frac{13}{12}$$

**总结**：独立随机变量和的方差等于方差之和。

---

## 八、解题方法总结

### 8.1 主要方法

| 类型 | 方法 |
|------|------|
| 数学期望计算 | 直接利用定义或随机变量函数的期望公式 |
| 方差计算 | $D(X) = E(X^2) - [E(X)]^2$ |
| 协方差计算 | $\mathrm{Cov}(X,Y) = E(XY) - E(X)E(Y)$ |
| 相关系数计算 | $\rho = \frac{\mathrm{Cov}(X,Y)}{\sqrt{D(X)D(Y)}}$ |
| 独立性判定 | $f(x,y) = f_X(x)f_Y(y)$ |

### 8.2 常见易错点

1. **数学期望的线性性**：$E(X+Y) = E(X)+E(Y)$ 不要求独立
2. **方差的可加性**：$D(X+Y) = D(X)+D(Y)$ 要求独立或 $\mathrm{Cov}(X,Y)=0$
3. **独立性与不相关**：独立一定不相关，但不相关不一定独立
4. **协方差的符号**：$\mathrm{Cov}(X,Y)$ 可正可负，反映线性相关的方向

---

## 九、练习题精选

### 基础练习

1. 设 $X \sim B(n, p)$，求 $E(X^2)$。

2. 设 $X \sim N(\mu, \sigma^2)$，求 $E(|X - \mu|)$。

### 提高练习

3. 设 $X_1, X_2, \cdots, X_n$ 独立同分布，$E(X_i) = \mu, D(X_i) = \sigma^2$，求 $\overline{X} = \frac{1}{n}\sum_{i=1}^{n}X_i$ 的期望和方差。

4. 设 $X \sim U(-1, 1)$，$Y = X^2$，求 $\mathrm{Cov}(X, Y)$。

---

## 参考答案提示

1. $E(X^2) = np(1-p) + (np)^2$（提示：利用 $D(X) = E(X^2) - [E(X)]^2$）

2. $E(|X - \mu|) = \sigma\sqrt{\frac{2}{\pi}}$（提示：积分计算）

3. $E(\overline{X}) = \mu$，$D(\overline{X}) = \frac{\sigma^2}{n}$（提示：期望和方差的性质）

4. $\mathrm{Cov}(X, Y) = 0$（提示：$X$ 为奇函数，$X^3$ 的期望为0）

---

> **注**：本 Lecture 内容涵盖数学期望、方差、协方差、相关系数及常见分布的数字特征。建议结合《基础过关660题》第541-550题进行练习巩固。

### 补充：协方差矩阵

<span style="background-color: #8db3e2">**协方差矩阵的定义**</span>

设 $(X_1, X_2, \cdots, X_n)$ 是 $n$ 维随机变量，记 $\sigma_{ij} = \mathrm{Cov}(X_i, X_j)$，则矩阵

$$\Sigma = \begin{pmatrix} \sigma_{11} & \sigma_{12} & \cdots & \sigma_{1n} \\ \sigma_{21} & \sigma_{22} & \cdots & \sigma_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ \sigma_{n1} & \sigma_{n2} & \cdots & \sigma_{nn} \end{pmatrix}$$

称为协方差矩阵。

**性质**：
- 协方差矩阵是对称矩阵（$\sigma_{ij} = \sigma_{ji}$）
- 协方差矩阵是半正定矩阵
- 若随机变量相互独立，则协方差矩阵为对角矩阵

### 补充：条件数学期望

<span style="background-color: #ccc1d9">**条件数学期望**</span>

- **离散型**：$E(X \mid Y=y_j) = \sum_i x_i P\{X=x_i \mid Y=y_j\}$
- **连续型**：$E(X \mid Y=y) = \int_{-\infty}^{+\infty} x f_{X|Y}(x|y) dx$

**全期望公式**：
$$E(X) = E[E(X \mid Y)] = \begin{cases} \sum_j E(X \mid Y=y_j) P\{Y=y_j\}, & \text{离散} \\ \int_{-\infty}^{+\infty} E(X \mid Y=y) f_Y(y) dy, & \text{连续} \end{cases}$$
