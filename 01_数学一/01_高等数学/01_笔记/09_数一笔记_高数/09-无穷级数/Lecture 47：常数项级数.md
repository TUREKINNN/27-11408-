---
title: "Lecture 47：常数项级数"
chapter: "09-无穷级数"
tags: [考研, 数学一, 高等数学, 考研数学一, 无穷级数, 常数项级数, 部分和, 收敛]
difficulty: ★★★
exam_weight: ★★★★
created: 2026-06-16
---

# Lecture 47：常数项级数

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★（级数章节基础，常与审敛法结合考查） |
| **分值分布** | 约 4-6 分 |
| **题型** | 判断级数敛散性、部分和计算、性质应用 |
| **难度** | 中等 |

---

## 一、常数项级数的基本概念

### 1.1 级数的定义

> 设 $\{u_n\}$ 是一个数列，则表达式
>
> $$\sum_{n=1}^{\infty} u_n = u_1 + u_2 + u_3 + \cdots + u_n + \cdots$$
>
> 称为（常数项）**无穷级数**，简称**级数**。其中 $u_n$ 称为级数的**一般项**（通项）。

### 1.2 部分和

> 级数 $\displaystyle\sum_{n=1}^{\infty} u_n$ 的前 $n$ 项之和
>
> $$\boxed{S_n = u_1 + u_2 + \cdots + u_n = \sum_{k=1}^{n} u_k}$$
>
> 称为该级数的**部分和**。由此得到**部分和数列** $\{S_n\}$。

部分和数列与通项的关系：

$$\boxed{u_n = S_n - S_{n-1} \quad (n \ge 2), \quad u_1 = S_1}$$

> 已知部分和 $S_n$ 的表达式，求通项 $u_n$ 时，用 $u_n = S_n - S_{n-1}$（注意 $n \ge 2$），且要单独验证 $u_1 = S_1$ 是否满足此式。

### 1.3 级数收敛与发散的定义

> 若部分和数列 $\{S_n\}$ 的极限存在，即
>
> $$\boxed{\lim_{n \to \infty} S_n = S}$$
>
> 则称级数 $\displaystyle\sum_{n=1}^{\infty} u_n$ **收敛**，$S$ 称为级数的**和**，记为 $\displaystyle\sum_{n=1}^{\infty} u_n = S$。
>
> 若 $\{S_n\}$ 的极限不存在，则称级数**发散**。

### 1.4 余项

> 级数的和 $S$ 与部分和 $S_n$ 之差
>
> $$r_n = S - S_n = \sum_{k=n+1}^{\infty} u_k = u_{n+1} + u_{n+2} + \cdots$$
>
> 称为级数的**余项**。级数收敛 $\Leftrightarrow$ $\displaystyle\lim_{n \to \infty} r_n = 0$。

---

## 二、收敛级数的基本性质


**性质 1（线性性）**：若 $\displaystyle\sum_{n=1}^{\infty} u_n = S$，$\displaystyle\sum_{n=1}^{\infty} v_n = T$，则对任意常数 $\alpha, \beta$：

$$\boxed{\sum_{n=1}^{\infty} (\alpha u_n + \beta v_n) = \alpha S + \beta T}$$

即收敛级数可以逐项相加（减）和数乘。

**性质 2（去掉或添加有限项不改变敛散性）**：

级数去掉、添加或改变**有限项**，不会改变其敛散性（但可能会改变收敛级数的和）。

> 去掉前 $m$ 项后，新的部分和 $S'_n = S_{n+m} - S_m$。当 $n \to \infty$ 时，$S_m$ 是常数，故 $\{S'_n\}$ 与 $\{S_n\}$ 同时收敛或发散。

**性质 3（级数的每一项乘以同一非零常数，敛散性不变）**：

若 $\displaystyle\sum_{n=1}^{\infty} u_n$ 收敛，则对 $k \ne 0$，$\displaystyle\sum_{n=1}^{\infty} k u_n$ 也收敛，且 $\displaystyle\sum_{n=1}^{\infty} k u_n = k \sum_{n=1}^{\infty} u_n$。

**性质 4（收敛级数的"结合律"）**：

对收敛级数的项**任意加括号**后所得新级数仍然收敛，且和不变。

> 反之不成立！加括号后收敛，原级数不一定收敛。例如 $(1-1) + (1-1) + \cdots = 0$ 收敛，但 $1 - 1 + 1 - 1 + \cdots$ 发散。

**性质 5（级数收敛的必要条件）**：

$$\boxed{\text{若 } \sum_{n=1}^{\infty} u_n \text{ 收敛，则 } \lim_{n \to \infty} u_n = 0}$$

> $\displaystyle\lim_{n \to \infty} u_n = 0$ **不能**推出级数收敛！最典型的反例是**调和级数** $\displaystyle\sum_{n=1}^{\infty} \frac{1}{n}$，虽然通项趋于 $0$，但级数**发散**。

>
> $$\boxed{\text{若 } \lim_{n \to \infty} u_n \ne 0 \text{（或极限不存在），则 } \sum_{n=1}^{\infty} u_n \text{ 发散}}$$
>
> 这是判断级数发散最快速的方法！

---

## 三、几个重要的常数项级数

### 3.1 几何级数（等比级数）

>
> $$\sum_{n=0}^{\infty} aq^n = a + aq + aq^2 + \cdots \quad (a \ne 0)$$
>
> $$\boxed{\text{当 } |q| < 1 \text{ 时收敛，和为 } \frac{a}{1-q}；\text{当 } |q| \ge 1 \text{ 时发散}}$$

### 3.2 调和级数

$$\sum_{n=1}^{\infty} \frac{1}{n} = 1 + \frac{1}{2} + \frac{1}{3} + \cdots \quad \text{发散}$$

> **方法一**（加括号法）：
>
> $$1 + \frac{1}{2} + \left(\frac{1}{3} + \frac{1}{4}\right) + \left(\frac{1}{5} + \frac{1}{6} + \frac{1}{7} + \frac{1}{8}\right) + \cdots$$
>
> 每组都 $\ge \frac{1}{2}$，部分和趋于无穷。
>
> **方法二**（积分比较法）：$\displaystyle\frac{1}{n} \ge \int_n^{n+1} \frac{1}{x}dx$，累加后与 $\ln n$ 比较。

### 3.3 $p$-级数

>
> $$\sum_{n=1}^{\infty} \frac{1}{n^p} = 1 + \frac{1}{2^p} + \frac{1}{3^p} + \cdots$$
>
> $$\boxed{\text{当 } p > 1 \text{ 时收敛；当 } p \le 1 \text{ 时发散}}$$

- $p = 1$ 时即为调和级数（发散）
- $p = 2$ 时 $\displaystyle\sum_{n=1}^{\infty}\frac{1}{n^2} = \frac{\pi^2}{6}$（巴塞尔问题）

### 3.4 交错调和级数

$$\sum_{n=1}^{\infty} \frac{(-1)^{n-1}}{n} = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \cdots = \ln 2$$

此级数收敛（由莱布尼茨准则），但非绝对收敛（见 Lecture 49）。

---

## 四、部分和的计算技巧

### 4.1 裂项法

> 当通项可以拆成两项之差时，部分和中的项会相互消去（telescoping）。

**【例1】** 求 $\displaystyle\sum_{n=1}^{\infty} \frac{1}{n(n+1)}$ 的和。

**解**：

$$u_n = \frac{1}{n(n+1)} = \frac{1}{n} - \frac{1}{n+1}$$

$$S_n = \left(1 - \frac{1}{2}\right) + \left(\frac{1}{2} - \frac{1}{3}\right) + \cdots + \left(\frac{1}{n} - \frac{1}{n+1}\right) = 1 - \frac{1}{n+1}$$

$$\lim_{n \to \infty} S_n = 1$$

故 $\displaystyle\sum_{n=1}^{\infty} \frac{1}{n(n+1)} = 1 \quad \square$

**【例2】** 求 $\displaystyle\sum_{n=1}^{\infty} \frac{1}{(2n-1)(2n+1)}$ 的和。

**解**：

$$u_n = \frac{1}{(2n-1)(2n+1)} = \frac{1}{2}\left(\frac{1}{2n-1} - \frac{1}{2n+1}\right)$$

$$S_n = \frac{1}{2}\left(1 - \frac{1}{2n+1}\right) \to \frac{1}{2}$$

故和为 $\dfrac{1}{2} \quad \square$

### 4.2 等比级数拆分法

**【例3】** 求 $\displaystyle\sum_{n=1}^{\infty} \frac{2^n + 3^n}{6^n}$ 的和。

**解**：

$$\sum_{n=1}^{\infty} \frac{2^n + 3^n}{6^n} = \sum_{n=1}^{\infty} \left(\frac{1}{3}\right)^n + \sum_{n=1}^{\infty} \left(\frac{1}{2}\right)^n = \frac{1/3}{1 - 1/3} + \frac{1/2}{1 - 1/2} = \frac{1}{2} + 1 = \frac{3}{2} \quad \square$$

### 4.3 利用 $S_n$ 判断敛散性

**【例4】** 判断 $\displaystyle\sum_{n=1}^{\infty} \ln\left(1 + \frac{1}{n}\right)$ 的敛散性。

**解**：

$$u_n = \ln\left(1 + \frac{1}{n}\right) = \ln(n+1) - \ln n$$

$$S_n = \ln(n+1) - \ln 1 = \ln(n+1) \to +\infty$$

故级数**发散**。$\square$

> 虽然 $\displaystyle\lim_{n\to\infty}\ln\left(1+\frac{1}{n}\right) = 0$，但级数仍然发散，再次说明通项趋于 $0$ 不是收敛的充分条件。

---

## 五、考研真题精选

### 【真题1】（选择·4分）

**题目**：下列级数中收敛的是

(A) $\displaystyle\sum_{n=1}^{\infty} \frac{1}{\sqrt{n}}$　(B) $\displaystyle\sum_{n=1}^{\infty} \frac{n}{n+1}$　(C) $\displaystyle\sum_{n=1}^{\infty} \frac{1}{n^2}$　(D) $\displaystyle\sum_{n=1}^{\infty} \sin\frac{1}{n}$

**解**：

- (A) $p = \frac{1}{2} \le 1$，$p$-级数发散
- (B) $\displaystyle\lim_{n\to\infty}\frac{n}{n+1} = 1 \ne 0$，由必要条件知发散
- (C) $p = 2 > 1$，$p$-级数收敛 ✓
- (D) $\displaystyle\sin\frac{1}{n} \sim \frac{1}{n}$，与调和级数同发散

**答案**：(C) $\square$

### 【真题2】（填空·4分）

**题目**：设 $\displaystyle\sum_{n=1}^{\infty} u_n$ 的部分和 $S_n = \frac{n}{2n+1}$，则 $\displaystyle\sum_{n=1}^{\infty} u_n = $____。

**解**：

$$\sum_{n=1}^{\infty} u_n = \lim_{n\to\infty} S_n = \lim_{n\to\infty} \frac{n}{2n+1} = \frac{1}{2}$$

**答案**：$\dfrac{1}{2}$ $\square$

---

## 📝 本节要点总结

| 内容 | 核心要点 |
|------|----------|
| 部分和 | $S_n = \sum_{k=1}^n u_k$，收敛 $\Leftrightarrow$ $\lim S_n$ 存在 |
| 通项与部分和 | $u_n = S_n - S_{n-1}$ |
| 五条性质 | 线性性、有限项不变、数乘、加括号、必要条件 |
| 收敛必要条件 | $\lim u_n = 0$（必要不充分！） |
| 发散判别 | $\lim u_n \ne 0$ → 一定发散 |
| 几何级数 | $\|q\|<1$ 收敛，$\|q\|\ge 1$ 发散 |
| $p$-级数 | $p>1$ 收敛，$p\le 1$ 发散 |

> 1. $\displaystyle\lim_{n\to\infty} u_n = 0$ **不保证**收敛，这是选择题高频陷阱
> 2. 调和级数发散、$p$-级数敛散性是后续审敛法的比较基准
> 3. 裂项求部分和是计算级数和的重要技巧
> 4. 几何级数 $\dfrac{a}{1-q}$ 要牢记，在幂级数章节会反复使用

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 48：正项级数及其审敛准则]] — 正项级数
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 49：交错级数与任意项级数]] — 交错级数
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/05-定积分及反常积分/Lecture 33：反常积分]] — 反常积分
