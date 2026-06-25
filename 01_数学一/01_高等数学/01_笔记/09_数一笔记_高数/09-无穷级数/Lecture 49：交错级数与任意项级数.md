---
title: "Lecture 49：交错级数与任意项级数"
chapter: "09-无穷级数"
tags: [考研, 数学一, 高等数学, 考研数学一, 无穷级数, 交错级数, 莱布尼茨准则, 绝对收敛, 条件收敛]
difficulty: ★★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 49：交错级数与任意项级数

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（绝对收敛/条件收敛是必考知识点） |
| **分值分布** | 约 4-8 分 |
| **题型** | 判断绝对收敛/条件收敛/发散、莱布尼茨准则应用 |
| **难度** | 中等偏难 |

---

## 一、交错级数

### 1.1 交错级数的定义

> 正负项交替出现的级数称为**交错级数**，其形式为：
>
> $$\sum_{n=1}^{\infty} (-1)^{n-1} u_n = u_1 - u_2 + u_3 - u_4 + \cdots \quad (u_n > 0)$$
>
> 或
>
> $$\sum_{n=1}^{\infty} (-1)^{n} u_n = -u_1 + u_2 - u_3 + u_4 - \cdots \quad (u_n > 0)$$

### 1.2 莱布尼茨准则（交错级数审敛法）

> 若交错级数 $\displaystyle\sum_{n=1}^{\infty}(-1)^{n-1}u_n$（$u_n > 0$）满足以下**两个条件**：
>
> $$\boxed{\text{条件①：} u_n \ge u_{n+1} \quad (n = 1, 2, 3, \ldots) \quad \text{（单调递减）}}$$
>
> $$\boxed{\text{条件②：} \lim_{n \to \infty} u_n = 0}$$
>
> 则该交错级数**收敛**，且其和 $S \le u_1$，余项 $|r_n| \le u_{n+1}$。

> - 只有条件②（通项趋于 $0$），不满足条件①（不单调递减）→ 不一定收敛
> - 只有条件①（单调递减），不满足条件②（极限不为 $0$）→ 一定发散
> - 两个条件**同时满足**时，才能判定收敛

### 1.3 余项估计

> 满足莱布尼茨准则的交错级数，余项满足：
>
> $$\boxed{|r_n| = |S - S_n| \le u_{n+1}}$$
>
> 且 $r_n$ 的正负号与第一个被省略的项 $(-1)^n u_{n+1}$ 相同。

**【例1】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{(-1)^{n-1}}{n} = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \cdots$ 的敛散性。

**解**：$u_n = \dfrac{1}{n}$

① $\dfrac{1}{n} \ge \dfrac{1}{n+1}$，单调递减 ✓

② $\displaystyle\lim_{n\to\infty}\frac{1}{n} = 0$ ✓

由莱布尼茨准则，级数收敛（且和 $= \ln 2$）。$\square$

**【例2】** 判断 $\displaystyle\sum_{n=1}^{\infty} (-1)^{n-1} \sin\frac{1}{n}$ 的敛散性。

**解**：$u_n = \sin\dfrac{1}{n}$

① $\sin x$ 在 $(0, +\infty)$ 上，$\dfrac{1}{n}$ 递减，$\sin\dfrac{1}{n}$ 也递减（当 $n$ 充分大时 $\dfrac{1}{n}$ 落在 $(0, \frac{\pi}{2})$ 内）。✓

② $\displaystyle\lim_{n\to\infty}\sin\frac{1}{n} = 0$ ✓

由莱布尼茨准则，级数收敛。$\square$

**【例3】** 判断 $\displaystyle\sum_{n=1}^{\infty} (-1)^n \frac{n}{n+1}$ 的敛散性。

**解**：$\displaystyle\lim_{n\to\infty}\frac{n}{n+1} = 1 \ne 0$

通项不趋于 $0$，级数**发散**。$\square$

---

## 二、绝对收敛与条件收敛

### 2.1 定义

> 若 $\displaystyle\sum_{n=1}^{\infty} |u_n|$ 收敛，则称 $\displaystyle\sum_{n=1}^{\infty} u_n$ **绝对收敛**。
>
> $$\boxed{\sum |u_n| \text{ 收敛} \Rightarrow \sum u_n \text{ 收敛（绝对收敛必收敛）}}$$

> 若 $\displaystyle\sum_{n=1}^{\infty} u_n$ 收敛，但 $\displaystyle\sum_{n=1}^{\infty} |u_n|$ 发散，则称 $\displaystyle\sum_{n=1}^{\infty} u_n$ **条件收敛**。
>
> $$\boxed{\sum u_n \text{ 收敛} + \sum |u_n| \text{ 发散} = \text{条件收敛}}$$

### 2.2 绝对收敛与条件收敛的关系

>
> ```
> 判断 ∑uₙ 的敛散性
>         │
>         ▼
>   先判断 ∑|uₙ| 的敛散性
>         │
>     ┌───┴───┐
>     ▼       ▼
>  ∑|uₙ|收敛  ∑|uₙ|发散
>     │       │
>     ▼       ▼
>  绝对收敛   再判断 ∑uₙ 是否收敛
>             │
>         ┌───┴───┐
>         ▼       ▼
>      ∑uₙ收敛  ∑uₙ发散
>         │       │
>         ▼       ▼
>     条件收敛    发散
> ```

### 2.3 绝对收敛的性质

>
> **性质 1**：绝对收敛 $\Rightarrow$ 收敛（反之不然）。
>
> **性质 2**：绝对收敛级数重排后仍然收敛，且和不变。
>
> **性质 3**：两个绝对收敛级数的柯西乘积仍然绝对收敛。

> 条件收敛级数重排后可以收敛到**任意给定的值**（黎曼重排定理），这是条件收敛与绝对收敛的本质区别。

---

## 三、任意项级数的审敛方法

### 3.1 判定策略

>
> **第一步**：检查 $\displaystyle\lim_{n\to\infty} u_n$ 是否为 $0$。若 $\ne 0$，直接判发散。
>
> **第二步**：判断 $\displaystyle\sum|u_n|$ 是否收敛（用正项级数的审敛法）。
> - 若 $\displaystyle\sum|u_n|$ 收敛 → 原级数**绝对收敛**
>
> **第三步**：若 $\displaystyle\sum|u_n|$ 发散，分两种情况：
> - 若是交错级数 → 用**莱布尼茨准则**判断是否条件收敛
> - 若非交错级数 → 可尝试用定义（部分和极限）或其他方法

### 3.2 典型例子

**【例4】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{(-1)^n}{\sqrt{n}}$ 的敛散性。

**解**：

先看 $\displaystyle\sum\left|\frac{(-1)^n}{\sqrt{n}}\right| = \sum\frac{1}{\sqrt{n}}$，$p = \frac{1}{2} \le 1$，发散。

再看原级数：交错级数 $u_n = \dfrac{1}{\sqrt{n}}$

① $\dfrac{1}{\sqrt{n}}$ 单调递减 ✓　② $\displaystyle\lim_{n\to\infty}\frac{1}{\sqrt{n}} = 0$ ✓

由莱布尼茨准则，原级数收敛。

故为**条件收敛**。$\square$

**【例5】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{(-1)^n}{n^2}$ 的敛散性。

**解**：

$\displaystyle\sum\left|\frac{(-1)^n}{n^2}\right| = \sum\frac{1}{n^2}$，$p = 2 > 1$，收敛。

故原级数**绝对收敛**。$\square$

**【例6】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{(-1)^n}{n} \cdot \frac{1}{\ln(n+1)}$ 的敛散性。

**解**：

$\displaystyle\sum\left|\frac{(-1)^n}{n\ln(n+1)}\right| = \sum\frac{1}{n\ln(n+1)} \sim \sum\frac{1}{n\ln n}$，由积分判别法发散。

交错级数 $u_n = \dfrac{1}{n\ln(n+1)}$：

① 单调递减 ✓　② $\to 0$ ✓

由莱布尼茨准则，级数收敛。

故为**条件收敛**。$\square$

---

## 四、绝对收敛与条件收敛的典型结论

>
> | 级数 | 敛散性 | 类型 |
> |------|--------|------|
> | $\displaystyle\sum\frac{(-1)^{n-1}}{n}$ | 收敛 | 条件收敛 |
> | $\displaystyle\sum\frac{(-1)^{n-1}}{n^2}$ | 收敛 | 绝对收敛 |
> | $\displaystyle\sum\frac{(-1)^{n-1}}{\sqrt{n}}$ | 收敛 | 条件收敛 |
> | $\displaystyle\sum\frac{(-1)^{n-1}}{n^p}$（$p > 0$） | 收敛 | $p > 1$ 绝对收敛，$0 < p \le 1$ 条件收敛 |
> | $\displaystyle\sum\frac{\sin n}{n^2}$ | 收敛 | 绝对收敛 |
> | $\displaystyle\sum\frac{\cos n}{n}$ | ？ | 需具体分析 |

### 4.1 $p$ 级数的交错版

>
> $$\boxed{\sum_{n=1}^{\infty} \frac{(-1)^{n-1}}{n^p} \begin{cases} \text{绝对收敛}, & p > 1 \\ \text{条件收敛}, & 0 < p \le 1 \\ \text{发散}, & p \le 0 \end{cases}}$$

---

## 五、绝对收敛的判别技巧

### 5.1 比值法判绝对收敛

> 对任意项级数 $\sum u_n$，若
>
> $$\lim_{n\to\infty}\left|\frac{u_{n+1}}{u_n}\right| = \rho$$
>
> - $\rho < 1$ → **绝对收敛**
> - $\rho > 1$ → $|u_{n+1}| > |u_n|$ → $u_n \not\to 0$ → **发散**

**【例7】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{(-3)^n}{n!}$ 的敛散性。

**解**：

$$\left|\frac{u_{n+1}}{u_n}\right| = \frac{3^{n+1}}{(n+1)!} \cdot \frac{n!}{3^n} = \frac{3}{n+1} \to 0 < 1$$

级数**绝对收敛**。$\square$

### 5.2 根值法判绝对收敛

**【例8】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{(-1)^n}{2^n}\left(1 + \frac{1}{n}\right)^{n^2}$ 的敛散性。

**解**：

$$\sqrt[n]{|u_n|} = \frac{1}{2}\left(1+\frac{1}{n}\right)^n \to \frac{e}{2} > 1$$

级数**发散**。$\square$

---

## 六、考研真题精选

### 【真题1】（2017年数一·选择·4分）

**题目**：设 $\displaystyle\sum_{n=1}^{\infty} a_n$ 收敛，则下列级数中一定收敛的是

(A) $\displaystyle\sum_{n=1}^{\infty} |a_n|$　(B) $\displaystyle\sum_{n=1}^{\infty} (-1)^n a_n$　(C) $\displaystyle\sum_{n=1}^{\infty} a_n a_{n+1}$　(D) $\displaystyle\sum_{n=1}^{\infty} \frac{a_n + a_{n+1}}{2}$

**解**：

- (A) 收敛不意味绝对收敛，反例：$a_n = \frac{(-1)^n}{n}$。✗
- (B) 反例：$a_n = \frac{(-1)^n}{n}$，$(-1)^n a_n = \frac{1}{n}$ 发散。✗
- (C) 反例：$a_n = \frac{(-1)^n}{\sqrt{n}}$，$a_n a_{n+1} = \frac{(-1)^{2n+1}}{\sqrt{n(n+1)}} = -\frac{1}{\sqrt{n(n+1)}} \sim -\frac{1}{n}$ 发散。✗
- (D) 由线性性，$\displaystyle\sum\frac{a_n+a_{n+1}}{2} = \frac{1}{2}\sum a_n + \frac{1}{2}\sum a_{n+1}$ 收敛。✓

**答案**：(D) $\square$

### 【真题2】（2020年数一·解答·10分）

**题目**：判断 $\displaystyle\sum_{n=1}^{\infty} (-1)^n \frac{\ln n}{n}$ 是绝对收敛、条件收敛还是发散。

**解**：

**判断绝对收敛性**：$\displaystyle\sum\frac{\ln n}{n}$

$\dfrac{\ln n}{n} > \dfrac{1}{n}$（当 $n \ge 3$），而 $\displaystyle\sum\frac{1}{n}$ 发散，故 $\displaystyle\sum\frac{\ln n}{n}$ 发散，非绝对收敛。

**判断条件收敛性**：交错级数 $u_n = \dfrac{\ln n}{n}$

① 设 $f(x) = \dfrac{\ln x}{x}$，$f'(x) = \dfrac{1 - \ln x}{x^2} < 0$（当 $x > e$），故 $u_n$ 单调递减（$n \ge 3$）。✓

② $\displaystyle\lim_{n\to\infty}\frac{\ln n}{n} = 0$ ✓

由莱布尼茨准则，原级数收敛。

故原级数**条件收敛**。$\square$

---

## 📝 本节要点总结

| 内容 | 核心要点 |
|------|----------|
| 交错级数 | 正负交替，$u_n > 0$ |
| 莱布尼茨准则 | ① 单调递减 ② $u_n \to 0$，两条件缺一不可 |
| 余项估计 | $\|r_n\| \le u_{n+1}$ |
| 绝对收敛 | $\sum\|u_n\|$ 收敛 $\Rightarrow$ $\sum u_n$ 收敛 |
| 条件收敛 | $\sum u_n$ 收敛 + $\sum\|u_n\|$ 发散 |
| 判定策略 | 先看绝对值级数，再看莱布尼茨 |

> 1. 莱布尼茨准则的两个条件**都要验证**，只写一个扣分
> 2. "收敛" $\ne$ "绝对收敛"，题目问"绝对/条件/发散"时要分清楚
> 3. $\displaystyle\sum|u_n|$ 发散不能推出 $\displaystyle\sum u_n$ 发散（交错级数可能条件收敛）
> 4. 绝对收敛级数可以任意重排，条件收敛不可以——这是理论考点
> 5. 比值法/根值法 $\rho < 1$ 时判的是**绝对收敛**，不是条件收敛

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 47：常数项级数]] — 常数项
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 48：正项级数及其审敛准则]] — 正项级数
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 50：幂级数]] — 幂级数
