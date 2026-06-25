---
title: "Lecture 45：二重积分的计算"
chapter: "08-重积分"
tags: [考研, 数学一, 高等数学, 考研数学一, 二重积分, 奇偶性, 对称性]
difficulty: ★★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 45：二重积分的计算

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，计算能力的直接考查） |
| **分值分布** | 约 10-14 分 |
| **题型** | 利用对称性简化、交换积分次序、特殊技巧 |
| **难度** | 中等偏难 |

---

## 一、利用奇偶性简化计算

### 1.1 关于坐标轴的奇偶性

> 设 $D$ 关于 $x$ 轴对称（即 $(x, y) \in D \Leftrightarrow (x, -y) \in D$），$D_1$ 为 $D$ 在 $x$ 轴上方的部分：
>
> - 若 $f(x, -y) = -f(x, y)$（关于 $y$ 为**奇函数**）：
>
> $$\boxed{\iint_D f(x, y)\,d\sigma = 0}$$
>
> - 若 $f(x, -y) = f(x, y)$（关于 $y$ 为**偶函数**）：
>
> $$\boxed{\iint_D f(x, y)\,d\sigma = 2\iint_{D_1} f(x, y)\,d\sigma}$$

> 设 $D$ 关于 $y$ 轴对称，$D_1$ 为 $D$ 在 $y$ 轴右侧的部分：
>
> - 若 $f(-x, y) = -f(x, y)$（关于 $x$ 为奇函数）：$\displaystyle\iint_D f\,d\sigma = 0$
> - 若 $f(-x, y) = f(x, y)$（关于 $x$ 为偶函数）：$\displaystyle\iint_D f\,d\sigma = 2\iint_{D_1} f\,d\sigma$

### 1.2 经典例题

**【例1】** 计算 $\displaystyle\iint_D (x^3 + y^2)\,d\sigma$，其中 $D: x^2 + y^2 \le 1$。

**解**：$D$ 关于 $x$ 轴和 $y$ 轴均对称。

- $x^3$ 关于 $x$ 是奇函数，$D$ 关于 $y$ 轴对称 $\Rightarrow$ $\displaystyle\iint_D x^3\,d\sigma = 0$
- $y^2$ 关于 $y$ 是偶函数，关于 $x$ 也是偶函数

$$\iint_D (x^3 + y^2)\,d\sigma = \iint_D y^2\,d\sigma = 4\iint_{D_1} y^2\,d\sigma$$

其中 $D_1: x \ge 0, y \ge 0, x^2+y^2 \le 1$。用极坐标：

$$= 4\int_0^{\pi/2} d\theta \int_0^1 r^2\sin^2\theta \cdot r\,dr = 4\int_0^{\pi/2}\sin^2\theta\,d\theta \int_0^1 r^3\,dr$$

$$= 4 \cdot \frac{\pi}{4} \cdot \frac{1}{4} = \frac{\pi}{4} \quad \square$$

> 由对称性 $\displaystyle\iint_D x^2\,d\sigma = \iint_D y^2\,d\sigma$，而：
>
> $$\iint_D (x^2+y^2)\,d\sigma = \int_0^{2\pi} d\theta \int_0^1 r^3\,dr = 2\pi \cdot \frac{1}{4} = \frac{\pi}{2}$$
>
> 故 $\displaystyle\iint_D y^2\,d\sigma = \frac{\pi}{4}$。

---

## 二、利用轮换对称性

> 若积分区域 $D$ 关于直线 $y = x$ 对称（即 $(x, y) \in D \Leftrightarrow (y, x) \in D$），则：
>
> $$\boxed{\iint_D f(x, y)\,d\sigma = \iint_D f(y, x)\,d\sigma}$$
>
> 特别地：
>
> $$\iint_D f(x)\,d\sigma = \iint_D f(y)\,d\sigma$$

### 2.1 经典应用

**【例2】** 设 $D: x^2 + y^2 \le R^2$，计算 $\displaystyle\iint_D \frac{a f(x) + b f(y)}{f(x) + f(y)}\,d\sigma$，其中 $f$ 连续且 $f > 0$。

**解**：$D$ 关于 $y = x$ 对称，由轮换对称性：

$$I = \iint_D \frac{af(x)+bf(y)}{f(x)+f(y)}\,d\sigma = \iint_D \frac{af(y)+bf(x)}{f(y)+f(x)}\,d\sigma$$

两式相加：

$$2I = \iint_D \frac{(a+b)[f(x)+f(y)]}{f(x)+f(y)}\,d\sigma = (a+b)\iint_D d\sigma = (a+b)\pi R^2$$

$$I = \frac{(a+b)\pi R^2}{2} \quad \square$$

---

## 三、积分区域的对称性分类

### 3.1 常见对称区域

| 对称性 | 条件 | 利用方式 |
|--------|------|----------|
| 关于 $x$ 轴对称 | $(x,y) \in D \Leftrightarrow (x,-y) \in D$ | 奇零偶倍 |
| 关于 $y$ 轴对称 | $(x,y) \in D \Leftrightarrow (-x,y) \in D$ | 奇零偶倍 |
| 关于 $y = x$ 对称 | $(x,y) \in D \Leftrightarrow (y,x) \in D$ | 轮换对称 |
| 关于原点对称 | $(x,y) \in D \Leftrightarrow (-x,-y) \in D$ | 结合函数的奇偶性 |

### 3.2 复合对称性

**【例3】** 计算 $\displaystyle\iint_D (2x + 3y)\,d\sigma$，其中 $D: (x-1)^2 + (y-1)^2 \le 1$。

**解**：$D$ 的形心为 $(1, 1)$，利用形心公式：

$$\iint_D x\,d\sigma = \bar{x} \cdot S = 1 \cdot \pi = \pi$$

$$\iint_D y\,d\sigma = \bar{y} \cdot S = 1 \cdot \pi = \pi$$

$$\iint_D (2x+3y)\,d\sigma = 2\pi + 3\pi = 5\pi \quad \square$$

> 若 $D$ 的形心为 $(\bar{x}, \bar{y})$，面积为 $S$，则：
>
> $$\iint_D x\,d\sigma = \bar{x} \cdot S, \quad \iint_D y\,d\sigma = \bar{y} \cdot S$$

---

## 四、积分限确定方法详解

### 4.1 穿线法的标准步骤

> 1. **画出区域 $D$**（这一步不可省略！）
> 2. 作竖直线段从 $D$ 的下方边界穿到上方边界
> 3. 下边界 $y = \varphi_1(x)$ 为内层积分下限
> 4. 上边界 $y = \varphi_2(x)$ 为内层积分上限
> 5. 确定 $x$ 的范围 $[a, b]$ 作为外层积分限
>
> **注意**：若 $D$ 的上下边界由不同曲线段构成，需**分段**积分！

### 4.2 分块积分的情形

**【例4】** 计算 $\displaystyle\iint_D xy\,d\sigma$，其中 $D$ 由 $y = x^2$，$y = 1$，$x = 0$ 围成。

**解**：画出区域 $D$。

X 型：$0 \le x \le 1$，$x^2 \le y \le 1$

$$\iint_D xy\,d\sigma = \int_0^1 dx \int_{x^2}^1 xy\,dy = \int_0^1 x \cdot \frac{1-x^4}{2}\,dx = \frac{1}{2}\int_0^1 (x - x^5)\,dx$$

$$= \frac{1}{2}\left(\frac{1}{2} - \frac{1}{6}\right) = \frac{1}{2} \cdot \frac{1}{3} = \frac{1}{6} \quad \square$$

### 4.3 复杂区域的处理

**【例5】** 计算 $\displaystyle\iint_D |y - x^2|\,d\sigma$，其中 $D: -1 \le x \le 1, 0 \le y \le 1$。

**解**：需去掉绝对值。在 $D$ 内，$y = x^2$ 将 $D$ 分为两部分：

- $D_1$: $y \ge x^2$（抛物线上方），此时 $|y-x^2| = y-x^2$
- $D_2$: $y < x^2$（抛物线下方），此时 $|y-x^2| = x^2-y$

$$I = \iint_{D_1}(y-x^2)\,d\sigma + \iint_{D_2}(x^2-y)\,d\sigma$$

利用 $D$ 关于 $y$ 轴的对称性（$|y-x^2|$ 关于 $x$ 为偶函数）：

$$I = 2\int_0^1 dx \left[\int_{x^2}^1 (y-x^2)\,dy + \int_0^{x^2}(x^2-y)\,dy\right]$$

$$= 2\int_0^1 dx \left[\frac{(1-x^2)^2}{2} + \frac{x^4}{2}\right] = \int_0^1 [(1-x^2)^2 + x^4]\,dx$$

$$= \int_0^1 [1 - 2x^2 + x^4 + x^4]\,dx = \int_0^1 (1 - 2x^2 + 2x^4)\,dx$$

$$= 1 - \frac{2}{3} + \frac{2}{5} = \frac{15 - 10 + 6}{15} = \frac{11}{15} \quad \square$$

---

## 五、二重积分的换元法

### 5.1 一般换元公式

> 设变换 $T: x = x(u, v)$，$y = y(u, v)$ 将 $uv$ 平面上的区域 $D'$ 一一映射到 $xy$ 平面上的区域 $D$，且雅可比行列式：
>
> $$J = \frac{\partial(x, y)}{\partial(u, v)} = \begin{vmatrix} x_u & x_v \\ y_u & y_v \end{vmatrix} \ne 0$$
>
> 则：
>
> $$\boxed{\iint_D f(x,y)\,dx\,dy = \iint_{D'} f[x(u,v), y(u,v)] \cdot |J|\,du\,dv}$$

### 5.2 极坐标是特例

极坐标 $x = r\cos\theta$，$y = r\sin\theta$ 的雅可比行列式：

$$J = \begin{vmatrix} \cos\theta & -r\sin\theta \\ \sin\theta & r\cos\theta \end{vmatrix} = r\cos^2\theta + r\sin^2\theta = r$$

故 $d\sigma = |J|\,dr\,d\theta = r\,dr\,d\theta$，与前述一致。

---

## 六、综合例题

**【例6】**（交换积分次序 + 计算）

计算 $\displaystyle\int_0^1 dy \int_y^1 e^{x^2}\,dx$。

**解**：$e^{x^2}$ 对 $x$ 无初等原函数，需交换次序。

原积分：$0 \le y \le 1$，$y \le x \le 1$

画图：三角形区域，$y = 0$，$y = x$，$x = 1$。

交换后：$0 \le x \le 1$，$0 \le y \le x$

$$\int_0^1 dx \int_0^x e^{x^2}\,dy = \int_0^1 xe^{x^2}\,dx = \frac{1}{2}e^{x^2}\bigg|_0^1 = \frac{e - 1}{2} \quad \square$$

**【例7】** 计算 $\displaystyle\iint_D \frac{x}{y}\,d\sigma$，其中 $D$ 由 $xy = 1$，$y = x$，$x = 2$ 围成。

**解**：画出区域。交点：$xy = 1$ 与 $y = x$ 交于 $(1, 1)$；$xy = 1$ 与 $x = 2$ 交于 $(2, \frac{1}{2})$；$y = x$ 与 $x = 2$ 交于 $(2, 2)$。

X 型：$1 \le x \le 2$，$\dfrac{1}{x} \le y \le x$

$$\iint_D \frac{x}{y}\,d\sigma = \int_1^2 dx \int_{1/x}^x \frac{x}{y}\,dy = \int_1^2 x[\ln y]_{1/x}^x\,dx$$

$$= \int_1^2 x[\ln x - \ln(1/x)]\,dx = \int_1^2 x \cdot 2\ln x\,dx = 2\int_1^2 x\ln x\,dx$$

分部积分：$\int x\ln x\,dx = \dfrac{x^2}{2}\ln x - \dfrac{x^2}{4} + C$

$$= 2\left[\frac{x^2}{2}\ln x - \frac{x^2}{4}\right]_1^2 = 2\left[(2\ln 2 - 1) - \left(0 - \frac{1}{4}\right)\right]$$

$$= 2\left(2\ln 2 - 1 + \frac{1}{4}\right) = 2\left(2\ln 2 - \frac{3}{4}\right) = 4\ln 2 - \frac{3}{2} \quad \square$$

---

## 七、考研真题精选

### 【真题1】（2021年数一·解答·10分）

**题目**：计算 $\displaystyle I = \iint_D \sqrt{|y - x^2|}\,d\sigma$，其中 $D: |x| \le 1, 0 \le y \le 2$。

**解**：由对称性（关于 $y$ 轴），$I = 2\displaystyle\int_0^1 dx$ 部分。

在 $D$ 内，$y = x^2$ 将区域分为 $D_1: y \ge x^2$ 和 $D_2: y < x^2$。

$$I = 2\int_0^1 dx\left[\int_{x^2}^2 \sqrt{y-x^2}\,dy + \int_0^{x^2} \sqrt{x^2-y}\,dy\right]$$

第一项：$\int_{x^2}^2 (y-x^2)^{1/2}\,dy = \dfrac{2}{3}(2-x^2)^{3/2}$

第二项：$\int_0^{x^2}(x^2-y)^{1/2}\,dy = \dfrac{2}{3}x^3$

$$I = 2\int_0^1 \frac{2}{3}[(2-x^2)^{3/2} + x^3]\,dx = \frac{4}{3}\left[\int_0^1(2-x^2)^{3/2}\,dx + \frac{1}{4}\right]$$

令 $x = \sqrt{2}\sin t$，则 $dx = \sqrt{2}\cos t\,dt$，$(2-x^2)^{3/2} = 2\sqrt{2}\cos^3 t$。

$$\int_0^1(2-x^2)^{3/2}\,dx = 4\int_0^{\pi/4}\cos^4 t\,dt = 4\left(\frac{3\pi}{32} + \frac{1}{4}\right) = \frac{3\pi}{8} + 1$$

$$I = \frac{4}{3}\left(\frac{3\pi}{8} + 1 + \frac{1}{4}\right) = \frac{4}{3}\left(\frac{3\pi}{8} + \frac{5}{4}\right) = \frac{\pi}{2} + \frac{5}{3} \quad \square$$

---

## 📝 本节要点总结

| 技巧 | 核心要点 |
|------|----------|
| 奇偶性 | 奇函数在对称区域积分为零，偶函数可折半 |
| 轮换对称性 | 关于 $y = x$ 对称时，$x$ 和 $y$ 可互换 |
| 形心公式 | $\iint_D x\,d\sigma = \bar{x} \cdot S$ |
| 穿线法 | 画图 → 穿线 → 定限 |
| 换元法 | 别忘雅可比行列式的绝对值 |

> 1. **先看对称性再计算**——很多题用对称性可直接得出结果或大幅简化
> 2. 内层积不出来 → 立即交换积分次序
> 3. 带绝对值的积分 → 用零点线分区域

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/08-重积分/Lecture 44：二重积分]] — 二重积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/08-重积分/Lecture 46：三重积分]] — 三重积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 34：定积分的应用]] — 定积分应用
