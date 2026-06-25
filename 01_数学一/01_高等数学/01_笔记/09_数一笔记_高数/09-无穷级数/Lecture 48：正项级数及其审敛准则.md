---
title: "Lecture 48：正项级数及其审敛准则"
chapter: "09-无穷级数"
tags: [考研, 数学一, 高等数学, 考研数学一, 无穷级数, 正项级数, 比较审敛法, 比值审敛法, 根值审敛法]
difficulty: ★★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 48：正项级数及其审敛准则

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，选择题/大题均高频） |
| **分值分布** | 约 4-10 分 |
| **题型** | 判断正项级数敛散性、选择合适的审敛法 |
| **难度** | 中等偏难 |

---

## 一、正项级数的基本定理

> 若 $u_n \ge 0$（$n = 1, 2, 3, \ldots$），则称 $\displaystyle\sum_{n=1}^{\infty} u_n$ 为**正项级数**。

>
> $$\boxed{\text{正项级数 } \sum_{n=1}^{\infty} u_n \text{ 收敛} \Leftrightarrow \text{部分和数列 } \{S_n\} \text{ 有上界}}$$

> 正项级数的部分和 $S_n$ 单调递增。单调递增数列有上界则收敛，无上界则趋于 $+\infty$（发散）。这一性质是所有正项级数审敛法的理论基础。

---

## 二、比较审敛法

### 2.1 基本形式

> 设 $\displaystyle\sum_{n=1}^{\infty} u_n$ 和 $\displaystyle\sum_{n=1}^{\infty} v_n$ 都是正项级数，且存在正整数 $N$，当 $n \ge N$ 时 $u_n \le v_n$，则：
>
> $$\boxed{\text{若 } \sum v_n \text{ 收敛} \Rightarrow \sum u_n \text{ 收敛（大的收敛则小的收敛）}}$$
>
> $$\boxed{\text{若 } \sum u_n \text{ 发散} \Rightarrow \sum v_n \text{ 发散（小的发散则大的发散）}}$$

> - 大的收敛 → 小的收敛 ✓
> - 小的发散 → 大的发散 ✓
> - 小的收敛 → 大的不一定收敛 ✗
> - 大的发散 → 小的不一定发散 ✗

**【例1】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{1}{n^2 + 1}$ 的敛散性。

**解**：$\dfrac{1}{n^2+1} < \dfrac{1}{n^2}$，而 $\displaystyle\sum\frac{1}{n^2}$ 收敛（$p=2>1$），由比较法知 $\displaystyle\sum\frac{1}{n^2+1}$ 收敛。$\square$

**【例2】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{1}{\sqrt{n} + 1}$ 的敛散性。

**解**：$\dfrac{1}{\sqrt{n}+1} > \dfrac{1}{2\sqrt{n}} = \dfrac{1}{2} \cdot \dfrac{1}{n^{1/2}}$，而 $\displaystyle\sum\frac{1}{n^{1/2}}$ 发散（$p=\frac{1}{2}\le 1$），故原级数发散。$\square$

### 2.2 比较审敛法的极限形式

> 设 $\displaystyle\sum u_n$、$\displaystyle\sum v_n$ 为正项级数（$v_n > 0$），若
>
> $$\boxed{\lim_{n \to \infty} \frac{u_n}{v_n} = l}$$
>
> - 当 $0 < l < +\infty$ 时，两级数**同敛散**
> - 当 $l = 0$ 时，若 $\displaystyle\sum v_n$ 收敛，则 $\displaystyle\sum u_n$ 收敛
> - 当 $l = +\infty$ 时，若 $\displaystyle\sum v_n$ 发散，则 $\displaystyle\sum u_n$ 发散

> 极限形式的核心思想是**等价无穷小替换**！
>
> 当 $n \to \infty$ 时，若 $u_n \sim v_n$（即 $l = 1$），则两级数同敛散。
>
> 所以只需找到 $u_n$ 的等价无穷小，再判断等价的级数即可。

**【例3】** 判断 $\displaystyle\sum_{n=1}^{\infty} \sin\frac{1}{n}$ 的敛散性。

**解**：当 $n \to \infty$ 时，$\sin\dfrac{1}{n} \sim \dfrac{1}{n}$。

取 $v_n = \dfrac{1}{n}$，$\displaystyle\lim_{n\to\infty}\frac{\sin(1/n)}{1/n} = 1$，而 $\displaystyle\sum\frac{1}{n}$ 发散，故原级数发散。$\square$

**【例4】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{1}{n \cdot 2^n}$ 的敛散性。

**解**：$\dfrac{1}{n \cdot 2^n}$ 与 $\dfrac{1}{2^n}$ 比较：

$$\lim_{n\to\infty}\frac{1/(n\cdot 2^n)}{1/2^n} = \lim_{n\to\infty}\frac{1}{n} = 0$$

$l = 0$，而 $\displaystyle\sum\frac{1}{2^n}$ 收敛（等比级数），故原级数收敛。$\square$

---

## 三、比值审敛法（达朗贝尔判别法）

> 设 $\displaystyle\sum u_n$ 为正项级数，若
>
> $$\boxed{\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \rho}$$
>
> 则：
> - $\rho < 1$ 时，级数**收敛**
> - $\rho > 1$（或 $\rho = +\infty$）时，级数**发散**
> - $\rho = 1$ 时，**不能判定**，需用其他方法

> 通项中含 $n!$、$a^n$、$n^n$ 等**阶乘或指数**形式时，比值法最有效。

**【例5】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{n!}{n^n}$ 的敛散性。

**解**：

$$\frac{u_{n+1}}{u_n} = \frac{(n+1)!}{(n+1)^{n+1}} \cdot \frac{n^n}{n!} = \frac{n^n}{(n+1)^n} = \left(\frac{n}{n+1}\right)^n = \frac{1}{\left(1+\frac{1}{n}\right)^n}$$

$$\lim_{n\to\infty}\frac{u_{n+1}}{u_n} = \frac{1}{e} < 1$$

故级数收敛。$\square$

**【例6】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{3^n \cdot n!}{n^n}$ 的敛散性。

**解**：

$$\frac{u_{n+1}}{u_n} = \frac{3^{n+1}(n+1)!}{(n+1)^{n+1}} \cdot \frac{n^n}{3^n \cdot n!} = 3 \cdot \frac{n^n}{(n+1)^n} = \frac{3}{\left(1+\frac{1}{n}\right)^n} \to \frac{3}{e} > 1$$

故级数发散。$\square$

---

## 四、根值审敛法（柯西判别法）

> 设 $\displaystyle\sum u_n$ 为正项级数，若
>
> $$\boxed{\lim_{n \to \infty} \sqrt[n]{u_n} = \rho}$$
>
> 则：
> - $\rho < 1$ 时，级数**收敛**
> - $\rho > 1$（或 $\rho = +\infty$）时，级数**发散**
> - $\rho = 1$ 时，**不能判定**

> 通项为 $n$ 次方形式，即 $u_n = [f(n)]^n$ 时，根值法最有效。

**【例7】** 判断 $\displaystyle\sum_{n=1}^{\infty} \left(\frac{n}{2n+1}\right)^n$ 的敛散性。

**解**：

$$\sqrt[n]{u_n} = \frac{n}{2n+1} \to \frac{1}{2} < 1$$

故级数收敛。$\square$

**【例8】** 判断 $\displaystyle\sum_{n=1}^{\infty} \frac{n^n}{(2n)!}$ 的敛散性。

**解**：

$$\sqrt[n]{u_n} = \frac{n}{\sqrt[n]{(2n)!}} \to \frac{n}{\frac{2n}{e}} = \frac{e}{2} > 1$$

（利用 Stirling 公式 $\sqrt[n]{n!} \sim \frac{n}{e}$）

故级数发散。$\square$

---

## 五、积分审敛法

> 设 $f(x)$ 在 $[1, +\infty)$ 上**连续、正值、单调递减**，且 $f(n) = u_n$，则
>
> $$\boxed{\sum_{n=1}^{\infty} u_n \text{ 与 } \int_1^{+\infty} f(x)\,dx \text{ 同敛散}}$$

**【例9】** 用积分判别法证明 $p$-级数的敛散性。

**解**：$f(x) = \dfrac{1}{x^p}$ 在 $[1, +\infty)$ 上满足条件。

$$\int_1^{+\infty} \frac{1}{x^p}\,dx = \begin{cases} \frac{1}{p-1}, & p > 1 \text{（收敛）} \\ +\infty, & p \le 1 \text{（发散）} \end{cases}$$

故 $\displaystyle\sum\frac{1}{n^p}$ 在 $p > 1$ 时收敛，$p \le 1$ 时发散。$\square$

**【例10】** 判断 $\displaystyle\sum_{n=2}^{\infty} \frac{1}{n \ln n}$ 的敛散性。

**解**：

$$\int_2^{+\infty} \frac{1}{x \ln x}\,dx = \ln(\ln x)\Big|_2^{+\infty} = +\infty$$

故级数**发散**。$\square$

> $\displaystyle\sum_{n=2}^{\infty}\frac{1}{n(\ln n)^p}$ 在 $p > 1$ 时收敛，$p \le 1$ 时发散。

---

## 六、三巨头：$a^n$、$n!$、$n^n$ 的比较

> 当 $a > 1$ 时，三者的增长速度排序为：
>
> $$\boxed{a^n \ll n! \ll n^n}$$
>
> 即指数增长 < 阶乘增长 < 幂指增长。

### 6.1 证明 $n!$ 比 $a^n$ 增长快

利用比值法：

$$\frac{(n+1)!}{a^{n+1}} \cdot \frac{a^n}{n!} = \frac{n+1}{a} \to +\infty$$

比值趋于无穷，说明 $n!$ 增长更快。

### 6.2 证明 $n^n$ 比 $n!$ 增长快

$$\frac{n^n}{n!} = \frac{n}{1} \cdot \frac{n}{2} \cdot \frac{n}{3} \cdots \frac{n}{n} \ge n \to +\infty$$

### 6.3 经典推论

>
> | 级数 | 敛散性 | 方法 |
> |------|--------|------|
> | $\displaystyle\sum\frac{a^n}{n!}$ | **收敛** | 比值法，$\rho = 0$ |
> | $\displaystyle\sum\frac{n!}{n^n}$ | **收敛** | 比值法，$\rho = \frac{1}{e}$ |
> | $\displaystyle\sum\frac{a^n}{n^n}$ | **收敛** | 根值法，$\rho = 0$ |
> | $\displaystyle\sum\frac{n^n}{n!}$ | **发散** | 比值法，$\rho = e$ |
> | $\displaystyle\sum\frac{n!}{a^n}$ | **发散** | 比值法，$\rho = +\infty$ |
> | $\displaystyle\sum\frac{n^n}{a^n}$ | **发散** | 根值法，$\rho = +\infty$ |

---

## 七、审敛法选择指南

>
> 1. **先看通项极限**：$\lim u_n \ne 0$ → 直接发散
> 2. **通项含 $n!$ 或 $a^n$** → 优先用**比值法**
> 3. **通项为 $n$ 次方形式 $[f(n)]^n$** → 优先用**根值法**
> 4. **通项能与已知级数比较**（如 $\frac{1}{n^p}$、$\frac{1}{a^n}$）→ 用**比较法**或**极限比较法**
> 5. **通项含有 $\ln n$** 等 → 考虑**积分判别法**
> 6. **比值法和根值法 $\rho = 1$ 时** → 必须改用比较法或其他方法

---

## 八、考研真题精选

### 【真题1】（2018年数一·选择·4分）

**题目**：设 $\displaystyle\sum_{n=1}^{\infty} a_n$ 为正项级数，则下列结论正确的是

(A) 若 $\displaystyle\lim_{n\to\infty} na_n = 0$，则 $\displaystyle\sum a_n$ 收敛

(B) 若 $\displaystyle\sum a_n$ 收敛，则 $\displaystyle\sum a_n^2$ 收敛

(C) 若 $\displaystyle\sum a_n$ 收敛，则 $\displaystyle\sum (-1)^n a_n$ 收敛

(D) 若 $\displaystyle\sum a_n^2$ 收敛，则 $\displaystyle\sum a_n$ 收敛

**解**：

- (A) 反例：$a_n = \frac{1}{n\ln n}$，$na_n = \frac{1}{\ln n} \to 0$，但级数发散。✗
- (B) $a_n \to 0$，故 $n$ 充分大时 $a_n < 1$，$a_n^2 < a_n$，由比较法知收敛。✓
- (C) 这不是正项级数了，且交错级数的莱布尼茨条件还需 $a_n$ 单调递减。✗
- (D) 反例：$a_n = \frac{1}{n}$。✗

**答案**：(B) $\square$

### 【真题2】（解答题·10分）

**题目**：判断 $\displaystyle\sum_{n=1}^{\infty} \frac{n! \cdot 3^n}{n^n}$ 的敛散性。

**解**：

$$\frac{u_{n+1}}{u_n} = \frac{(n+1)! \cdot 3^{n+1}}{(n+1)^{n+1}} \cdot \frac{n^n}{n! \cdot 3^n} = 3 \cdot \frac{n^n}{(n+1)^n} = \frac{3}{\left(1+\frac{1}{n}\right)^n} \to \frac{3}{e} > 1$$

由比值审敛法，级数**发散**。$\square$

---

## 📝 本节要点总结

| 审敛法 | 核心条件 | 适用情形 |
|--------|----------|----------|
| 比较法（基本） | $u_n \le v_n$ | 能找到合适的比较对象 |
| 比较法（极限） | $\lim\frac{u_n}{v_n} = l$ | 等价无穷小思想，最灵活 |
| 比值法 | $\lim\frac{u_{n+1}}{u_n} = \rho$ | 含 $n!$、$a^n$ |
| 根值法 | $\lim\sqrt[n]{u_n} = \rho$ | 含 $[f(n)]^n$ |
| 积分判别法 | $\sum u_n$ 与 $\int f(x)dx$ | 含 $\ln n$ 等 |

> 1. 比值法和根值法 $\rho = 1$ 时**无效**，此时必须用比较法
> 2. 正项级数比较法的极限形式最常用，本质是等价无穷小
> 3. $a^n \ll n! \ll n^n$ 是快速判断含这三者的级数敛散性的关键
> 4. 积分判别法是 $p$-级数敛散性证明的理论依据

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 47：常数项级数]] — 常数项
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 49：交错级数与任意项级数]] — 交错级数
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 50：幂级数]] — 幂级数
