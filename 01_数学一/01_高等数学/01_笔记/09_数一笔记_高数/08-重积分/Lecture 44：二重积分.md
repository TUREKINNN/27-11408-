---
title: "Lecture 44：二重积分"
chapter: "08-重积分"
tags: [考研, 数学一, 高等数学, 考研数学一, 二重积分, 直角坐标, 极坐标]
difficulty: ★★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 44：二重积分

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，计算题高频） |
| **分值分布** | 约 10-12 分 |
| **题型** | 二重积分计算、交换积分次序、极坐标计算 |
| **难度** | 中等 |

---

## 一、二重积分的定义

> 设 $f(x, y)$ 在有界闭区域 $D$ 上有界，将 $D$ 任意分割为 $n$ 个小区域 $\Delta\sigma_i$（面积也记为 $\Delta\sigma_i$），在每个小区域内任取一点 $(\xi_i, \eta_i)$，作和式：
>
> $$\sum_{i=1}^{n} f(\xi_i, \eta_i) \Delta\sigma_i$$
>
> 若当各小区域直径的最大值 $\lambda \to 0$ 时，此和式的极限**存在**且与分割方式和取点方式无关，则称此极限为 $f(x, y)$ 在 $D$ 上的**二重积分**，记为：
>
> $$\boxed{\iint_D f(x, y)\,d\sigma = \lim_{\lambda \to 0} \sum_{i=1}^{n} f(\xi_i, \eta_i) \Delta\sigma_i}$$

### 1.1 二重积分的几何意义

- 当 $f(x, y) \ge 0$ 时，$\displaystyle\iint_D f(x, y)\,d\sigma$ 表示以 $D$ 为底、$z = f(x, y)$ 为顶的**曲顶柱体的体积**
- 一般情况下，$f > 0$ 的部分取正，$f < 0$ 的部分取负

### 1.2 二重积分存在的条件

> 若 $f(x, y)$ 在有界闭区域 $D$ 上**连续**，则 $\displaystyle\iint_D f(x, y)\,d\sigma$ 存在。

---

## 二、二重积分的性质


**性质 1（线性性）**：

$$\iint_D [\alpha f(x,y) + \beta g(x,y)]\,d\sigma = \alpha\iint_D f\,d\sigma + \beta\iint_D g\,d\sigma$$

**性质 2（区域可加性）**：

若 $D = D_1 \cup D_2$，$D_1 \cap D_2$ 为零面积集，则：

$$\iint_D f\,d\sigma = \iint_{D_1} f\,d\sigma + \iint_{D_2} f\,d\sigma$$

**性质 3（保号性）**：若 $f(x, y) \ge 0$ 在 $D$ 上成立，则 $\displaystyle\iint_D f\,d\sigma \ge 0$。

**推论**：若 $f(x, y) \ge g(x, y)$，则 $\displaystyle\iint_D f\,d\sigma \ge \iint_D g\,d\sigma$。

**性质 4（估值定理）**：设 $m \le f(x, y) \le M$，$S$ 为 $D$ 的面积，则：

$$mS \le \iint_D f\,d\sigma \le MS$$

**性质 5（中值定理）**：设 $f(x, y)$ 在有界闭区域 $D$ 上连续，则 $\exists\, (\xi, \eta) \in D$，使得：

$$\iint_D f(x, y)\,d\sigma = f(\xi, \eta) \cdot S$$

其中 $S$ 为 $D$ 的面积。

---

## 三、直角坐标下二重积分的计算

### 3.1 X 型区域

> 若 $D$ 可表示为：$a \le x \le b$，$\varphi_1(x) \le y \le \varphi_2(x)$，则：
>
> $$\boxed{\iint_D f(x,y)\,d\sigma = \int_a^b dx \int_{\varphi_1(x)}^{\varphi_2(x)} f(x,y)\,dy}$$
>
> 先对 $y$ 积分（$x$ 视为常数），将 $y$ 的上下限用 $x$ 表示，再对 $x$ 积分。

### 3.2 Y 型区域

> 若 $D$ 可表示为：$c \le y \le d$，$\psi_1(y) \le x \le \psi_2(y)$，则：
>
> $$\boxed{\iint_D f(x,y)\,d\sigma = \int_c^d dy \int_{\psi_1(y)}^{\psi_2(y)} f(x,y)\,dx}$$

### 3.3 穿线法确定积分限

> 以 X 型为例：
> 1. 画出积分区域 $D$
> 2. 作一条竖线（平行于 $y$ 轴），从下往上穿过 $D$
> 3. **进入** $D$ 的边界 $y = \varphi_1(x)$ 为内层积分**下限**
> 4. **离开** $D$ 的边界 $y = \varphi_2(x)$ 为内层积分**上限**
> 5. 外层积分限为 $D$ 在 $x$ 轴上的投影 $[a, b]$

### 3.4 经典例题

**【例1】** 计算 $\displaystyle\iint_D xy\,d\sigma$，其中 $D$ 由 $y = x$ 和 $y = x^2$ 围成。

**解**：画出区域，交点为 $(0, 0)$ 和 $(1, 1)$。

X 型：$0 \le x \le 1$，$x^2 \le y \le x$

$$\iint_D xy\,d\sigma = \int_0^1 dx \int_{x^2}^{x} xy\,dy = \int_0^1 x \cdot \frac{y^2}{2}\bigg|_{x^2}^{x} dx$$

$$= \int_0^1 x \cdot \frac{x^2 - x^4}{2}\,dx = \frac{1}{2}\int_0^1 (x^3 - x^5)\,dx$$

$$= \frac{1}{2}\left(\frac{1}{4} - \frac{1}{6}\right) = \frac{1}{2} \cdot \frac{1}{12} = \frac{1}{24} \quad \square$$

**【例2】** 计算 $\displaystyle\iint_D e^{-y^2}\,d\sigma$，其中 $D$ 由 $y = x$，$y = 1$，$x = 0$ 围成。

**解**：$e^{-y^2}$ 对 $y$ 无初等原函数，故**不能**先对 $y$ 积分。

改用 Y 型：$0 \le y \le 1$，$0 \le x \le y$

$$\iint_D e^{-y^2}\,d\sigma = \int_0^1 dy \int_0^y e^{-y^2}\,dx = \int_0^1 ye^{-y^2}\,dy$$

$$= -\frac{1}{2}e^{-y^2}\bigg|_0^1 = -\frac{1}{2}(e^{-1} - 1) = \frac{1}{2}\left(1 - \frac{1}{e}\right) \quad \square$$

> 当内层积分无法用初等函数表示时，必须**交换积分次序**。

---

## 四、极坐标下二重积分的计算

### 4.1 极坐标变换

> 令 $x = r\cos\theta$，$y = r\sin\theta$，面积元素 $d\sigma = r\,dr\,d\theta$：
>
> $$\boxed{\iint_D f(x, y)\,d\sigma = \iint_{D'} f(r\cos\theta, r\sin\theta) \cdot r\,dr\,d\theta}$$

> 极坐标下面积元素为 $r\,dr\,d\theta$，不是 $dr\,d\theta$。这是最常犯的错误。

### 4.2 适用极坐标的情形

> 1. 积分区域 $D$ 是**圆**或圆的一部分（圆环、扇形等）
> 2. 被积函数含 $x^2 + y^2$、$\dfrac{y}{x}$、$\dfrac{x}{y}$ 等形式
> 3. 积分限在直角坐标下难以表达

### 4.3 极坐标下积分限的确定

> 1. 以原点为端点作射线，从 $\theta = \alpha$ 到 $\theta = \beta$ 扫过区域
> 2. 对每个 $\theta$，射线**进入** $D$ 的 $r$ 值为下限，**离开**为上限
> 3. 若原点在 $D$ 内部，下限通常为 $r = 0$

常见极坐标区域：

| 区域 | 极坐标表示 |
|------|-----------|
| 圆 $x^2+y^2 \le R^2$ | $0 \le r \le R$，$0 \le \theta \le 2\pi$ |
| 上半圆 $x^2+y^2 \le R^2, y \ge 0$ | $0 \le r \le R$，$0 \le \theta \le \pi$ |
| 扇形 $x^2+y^2 \le R^2, x \ge 0, y \ge 0$ | $0 \le r \le R$，$0 \le \theta \le \frac{\pi}{2}$ |
| 圆环 $R_1^2 \le x^2+y^2 \le R_2^2$ | $R_1 \le r \le R_2$，$0 \le \theta \le 2\pi$ |

### 4.4 经典例题

**【例3】** 计算 $\displaystyle\iint_D \sqrt{x^2+y^2}\,d\sigma$，其中 $D: x^2 + y^2 \le 2x$。

**解**：$D$ 是圆心 $(1, 0)$ 半径 $1$ 的圆，极坐标下 $r = 2\cos\theta$。

$$\iint_D \sqrt{x^2+y^2}\,d\sigma = \int_{-\pi/2}^{\pi/2} d\theta \int_0^{2\cos\theta} r \cdot r\,dr = \int_{-\pi/2}^{\pi/2} \frac{r^3}{3}\bigg|_0^{2\cos\theta} d\theta$$

$$= \frac{8}{3}\int_{-\pi/2}^{\pi/2} \cos^3\theta\,d\theta = \frac{8}{3} \cdot 2\int_0^{\pi/2} \cos^3\theta\,d\theta$$

$$= \frac{16}{3} \cdot \frac{2}{3} = \frac{32}{9} \quad \square$$

**【例4】** 计算 $\displaystyle\iint_D e^{-(x^2+y^2)}\,d\sigma$，其中 $D: x^2 + y^2 \le R^2$。

**解**：

$$\iint_D e^{-(x^2+y^2)}\,d\sigma = \int_0^{2\pi} d\theta \int_0^R e^{-r^2} \cdot r\,dr = 2\pi \cdot \left(-\frac{1}{2}e^{-r^2}\right)\bigg|_0^R$$

$$= 2\pi \cdot \frac{1}{2}(1 - e^{-R^2}) = \pi(1 - e^{-R^2}) \quad \square$$

> 利用此结果可证明著名的泊松积分：
>
> $$\int_{-\infty}^{+\infty} e^{-x^2}\,dx = \sqrt{\pi}$$

---

## 五、交换积分次序

> 1. 根据原积分限画出积分区域 $D$
> 2. 按另一个方向用穿线法确定新的积分限
> 3. 写出新的累次积分

**【例5】** 交换积分次序：$\displaystyle\int_0^1 dx \int_x^1 f(x, y)\,dy$。

**解**：

原积分：$0 \le x \le 1$，$x \le y \le 1$

区域 $D$：由 $y = x$，$y = 1$，$x = 0$ 围成的三角形。

交换后：$0 \le y \le 1$，$0 \le x \le y$

$$\int_0^1 dy \int_0^y f(x, y)\,dx \quad \square$$

---

## 六、考研真题精选

### 【真题1】（2019年数一·选择·4分）

**题目**：设 $D = \{(x, y) \mid x^2 + y^2 \le 1\}$，则 $\displaystyle\iint_D (x^2 - y^2)\,d\sigma = $

(A) $0$ (B) $\dfrac{\pi}{4}$ (C) $\dfrac{\pi}{2}$ (D) $\pi$

**解**：由对称性，$D$ 关于 $x, y$ 对称，$\displaystyle\iint_D x^2\,d\sigma = \iint_D y^2\,d\sigma$。

故 $\displaystyle\iint_D (x^2 - y^2)\,d\sigma = 0$。

**答案**：(A) $\square$

---

## 📝 本节要点总结

| 内容 | 核心要点 |
|------|----------|
| 定义 | 分割、取点、求和、取极限 |
| 直角坐标 | X 型（先 $y$ 后 $x$）、Y 型（先 $x$ 后 $y$） |
| 极坐标 | $d\sigma = r\,dr\,d\theta$，别忘 $r$ |
| 积分次序 | 内层积不出时必须换序 |

> 1. 极坐标面积元素是 $r\,dr\,d\theta$，忘写 $r$ 是最常见错误
> 2. 交换积分次序必考，画图是关键
> 3. 利用对称性可简化计算

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/08-重积分/Lecture 45：二重积分的计算]] — 计算
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/08-重积分/Lecture 46：三重积分]] — 三重积分
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 31：定积分的基本概念]] — 定积分
