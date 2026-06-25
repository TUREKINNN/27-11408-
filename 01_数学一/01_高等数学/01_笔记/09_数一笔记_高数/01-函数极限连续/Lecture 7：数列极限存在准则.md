---
title: "Lecture 7：数列极限存在准则"
tags: [考研, 数学一, 高等数学, 数学, 考研数学一, 数列极限, 夹逼准则, 单调有界准则]
categories: 高等数学
  - 考研数学
  - 函数极限连续
date: 2026-06-16
---

# Lecture 7：数列极限存在准则

> 本讲讲解判断数列极限是否存在的两个核心准则：**夹逼准则（迫敛性）** 和 **单调有界准则**。这两个准则在考研中极为重要，既是求极限的工具，也是证明题的常见考点。

---

## 一、夹逼准则（迫敛性定理）

### 1.1 定理表述

> 设三个数列 $\{a_n\}$、$\{b_n\}$、$\{c_n\}$ 满足：
> 1. 存在 $N_0$，当 $n > N_0$ 时，$a_n \leq b_n \leq c_n$
> 2. $\lim_{n \to \infty} a_n = \lim_{n \to \infty} c_n = A$
>
> 则 $\lim_{n \to \infty} b_n = A$。

### 1.2 证明

**证明**：

对任意 $\varepsilon > 0$：

由 $\lim_{n \to \infty} a_n = A$，$\exists N_1$，当 $n > N_1$ 时，$A - \varepsilon < a_n < A + \varepsilon$

由 $\lim_{n \to \infty} c_n = A$，$\exists N_2$，当 $n > N_2$ 时，$A - \varepsilon < c_n < A + \varepsilon$

取 $N = \max(N_0, N_1, N_2)$，当 $n > N$ 时：

$$A - \varepsilon < a_n \leq b_n \leq c_n < A + \varepsilon$$

即 $|b_n - A| < \varepsilon$，故 $\lim_{n \to \infty} b_n = A$。$\square$

### 1.3 几何意义

```
        A + ε ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ c_n ─ ─ ─ ─
                                         b_n ─ ─ ─ ─ （被夹在中间）
        A ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
                                         a_n ─ ─ ─ ─
        A - ε ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
```

$a_n$ 和 $c_n$ 从两侧"夹逼" $b_n$，使其不得不趋向于 $A$。

### 1.4 函数极限的夹逼准则

> 若在 $x_0$ 的某个去心邻域内，$g(x) \leq f(x) \leq h(x)$，且 $\lim_{x \to x_0} g(x) = \lim_{x \to x_0} h(x) = A$，则 $\lim_{x \to x_0} f(x) = A$。
>
> 对 $x \to \infty$ 等其他极限过程也类似。

---

## 二、夹逼准则的典型应用

### 例 1：求 $\lim_{n \to \infty} \frac{n}{2^n}$

**解**：

当 $n \geq 1$ 时，$2^n = (1+1)^n = \sum_{k=0}^{n} \binom{n}{k} \geq \binom{n}{2} = \frac{n(n-1)}{2}$

故 $0 \leq \frac{n}{2^n} \leq \frac{n}{\frac{n(n-1)}{2}} = \frac{2}{n-1}$（$n \geq 2$）

由 $\lim_{n \to \infty} 0 = \lim_{n \to \infty} \frac{2}{n-1} = 0$，由夹逼准则得 $\lim_{n \to \infty} \frac{n}{2^n} = 0$。

### 例 2：求 $\lim_{n \to \infty} \sqrt[n]{a}$（$a > 0$）

**解**：

**情况 1**：$a = 1$ 时，$\sqrt[n]{1} = 1$，极限为 1。

**情况 2**：$a > 1$ 时，令 $\sqrt[n]{a} = 1 + h_n$（$h_n > 0$），则

$$a = (1 + h_n)^n \geq 1 + nh_n$$

故 $0 < h_n \leq \frac{a - 1}{n}$，由夹逼准则 $h_n \to 0$，即 $\sqrt[n]{a} \to 1$。

**情况 3**：$0 < a < 1$ 时，$\frac{1}{a} > 1$，故 $\sqrt[n]{\frac{1}{a}} \to 1$，从而 $\sqrt[n]{a} \to 1$。

综上，$\lim_{n \to \infty} \sqrt[n]{a} = 1$（$a > 0$）。

### 例 3：求 $\lim_{n \to \infty} \sqrt[n]{n}$

**解**：令 $\sqrt[n]{n} = 1 + h_n$（$h_n > 0$），则

$$n = (1 + h_n)^n \geq 1 + nh_n + \frac{n(n-1)}{2}h_n^2 \geq \frac{n(n-1)}{2}h_n^2$$

故 $h_n^2 \leq \frac{2}{n-1}$，即 $0 < h_n \leq \sqrt{\frac{2}{n-1}} \to 0$

由夹逼准则 $h_n \to 0$，故 $\sqrt[n]{n} \to 1$。

### 例 4：经典求和极限

**题目**：求 $\lim_{n \to \infty} \left(\frac{1}{\sqrt{n^2+1}} + \frac{1}{\sqrt{n^2+2}} + \cdots + \frac{1}{\sqrt{n^2+n}}\right)$

**解**：

记 $S_n = \sum_{k=1}^{n} \frac{1}{\sqrt{n^2+k}}$

由于 $\sqrt{n^2+k} \leq \sqrt{n^2+n}$（$k \leq n$），得 $\frac{1}{\sqrt{n^2+k}} \geq \frac{1}{\sqrt{n^2+n}}$

故 $S_n \geq \frac{n}{\sqrt{n^2+n}} = \frac{1}{\sqrt{1+\frac{1}{n}}}$

同理 $S_n \leq \frac{n}{\sqrt{n^2+1}} = \frac{1}{\sqrt{1+\frac{1}{n^2}}}$

由 $\lim_{n \to \infty} \frac{1}{\sqrt{1+\frac{1}{n}}} = \lim_{n \to \infty} \frac{1}{\sqrt{1+\frac{1}{n^2}}} = 1$

由夹逼准则，$\lim_{n \to \infty} S_n = 1$。

### 例 5：利用夹逼准则求含三角函数的极限

**题目**：求 $\lim_{n \to \infty} \frac{\sin n}{n}$

**解**：

由于 $|\sin n| \leq 1$，故

$$-\frac{1}{n} \leq \frac{\sin n}{n} \leq \frac{1}{n}$$

由 $\lim_{n \to \infty} \left(-\frac{1}{n}\right) = \lim_{n \to \infty} \frac{1}{n} = 0$

由夹逼准则，$\lim_{n \to \infty} \frac{\sin n}{n} = 0$。

---

## 三、单调有界准则

### 3.1 定理表述

> 1. **单调递增有上界的数列必收敛**：若 $\{a_n\}$ 单调递增且有上界（$\exists M$，$a_n \leq M$），则 $\{a_n\}$ 收敛。
> 2. **单调递减有下界的数列必收敛**：若 $\{a_n\}$ 单调递减且有下界（$\exists m$，$a_n \geq m$），则 $\{a_n\}$ 收敛。

### 3.2 直观理解

- 单调递增的数列要么趋向 $+\infty$，要么趋向某个有限值
- 如果有上界，就不能趋向 $+\infty$，所以必须趋向某个有限值
- 这个有限值就是数列的上确界 $\sup\{a_n\}$

### 3.3 注意事项

> 1. 单调有界准则**只能证明极限存在**，不能求出极限值
> 2. 要求极限值，需要在证明存在后利用递推关系 $a_{n+1} = f(a_n)$，令 $A = f(A)$ 求解
> 3. 该准则**只适用于数列**，对函数极限需要用其他方法

---

## 四、单调有界准则的典型应用

### 例 6：证明 $a_n = \left(1 + \frac{1}{n}\right)^n$ 收敛

**证明**：

**第一步：证明单调递增**

由均值不等式：

$$a_n = \underbrace{\left(1+\frac{1}{n}\right) \cdots \left(1+\frac{1}{n}\right)}_{n \text{ 个}} \cdot 1$$

这是 $n+1$ 个正数的乘积，其中 $n$ 个为 $1 + \frac{1}{n}$，1 个为 $1$。

由 AM-GM 不等式：

$$\sqrt[n+1]{a_n} \leq \frac{n \cdot \left(1+\frac{1}{n}\right) + 1}{n+1} = \frac{n+1+1}{n+1} = \frac{n+2}{n+1} = 1 + \frac{1}{n+1}$$

故 $a_n \leq \left(1 + \frac{1}{n+1}\right)^{n+1} = a_{n+1}$

所以 $\{a_n\}$ 单调递增。

**第二步：证明有上界**

由二项式展开：

$$a_n = \sum_{k=0}^{n} \binom{n}{k} \frac{1}{n^k} = \sum_{k=0}^{n} \frac{n!}{k!(n-k)!} \cdot \frac{1}{n^k}$$

$$= \sum_{k=0}^{n} \frac{1}{k!} \cdot \frac{n(n-1)\cdots(n-k+1)}{n^k}$$

$$\leq \sum_{k=0}^{n} \frac{1}{k!} \leq 1 + 1 + \frac{1}{2} + \frac{1}{2^2} + \cdots + \frac{1}{2^{n-1}} < 1 + \frac{1}{1-\frac{1}{2}} = 3$$

故 $a_n < 3$，有上界。

由单调有界准则，$\{a_n\}$ 收敛。此极限定义为 $e$。$\square$

### 例 7：递推数列的收敛性

**题目**：设 $a_1 = \sqrt{2}$，$a_{n+1} = \sqrt{2 + a_n}$，证明 $\{a_n\}$ 收敛并求极限。

**解**：

**第一步：证明有上界**

用数学归纳法。$a_1 = \sqrt{2} < 2$。

设 $a_n < 2$，则 $a_{n+1} = \sqrt{2 + a_n} < \sqrt{2 + 2} = 2$。

故所有 $a_n < 2$。

**第二步：证明单调递增**

$$a_{n+1}^2 - a_n^2 = (2 + a_n) - a_n^2 = -(a_n^2 - a_n - 2) = -(a_n - 2)(a_n + 1)$$

由于 $a_n < 2$，$a_n + 1 > 0$，故 $(a_n - 2)(a_n + 1) < 0$，即 $a_{n+1}^2 - a_n^2 > 0$。

又 $a_n > 0$，故 $a_{n+1} > a_n$，单调递增。

**第三步：求极限**

由单调有界准则，$\lim_{n \to \infty} a_n = A$ 存在。

由 $a_{n+1} = \sqrt{2 + a_n}$，取极限得 $A = \sqrt{2 + A}$，即 $A^2 = 2 + A$，$A^2 - A - 2 = 0$。

$(A - 2)(A + 1) = 0$，$A = 2$ 或 $A = -1$（舍去）。

故 $\lim_{n \to \infty} a_n = 2$。

### 例 8：利用单调性证明极限存在

**题目**：设 $a_1 = 1$，$a_{n+1} = 1 + \frac{a_n}{1 + a_n}$，证明 $\{a_n\}$ 收敛并求极限。

**解**：

**有界性**：显然 $a_n > 0$。又 $a_{n+1} = 1 + \frac{a_n}{1 + a_n} < 1 + 1 = 2$。

**单调性**：$a_{n+1} - a_n = 1 + \frac{a_n}{1 + a_n} - a_n = \frac{1 + a_n + a_n - a_n(1 + a_n)}{1 + a_n} = \frac{1 + a_n - a_n^2}{1 + a_n}$

设 $f(x) = 1 + x - x^2$，$f'(x) = 1 - 2x$。$f(x) = 0$ 时 $x = \frac{1 + \sqrt{5}}{2}$。

若 $a_n < \frac{1+\sqrt{5}}{2}$，则 $f(a_n) > 0$，$a_{n+1} > a_n$。

$a_1 = 1 < \frac{1+\sqrt{5}}{2}$，由归纳法 $a_n < \frac{1+\sqrt{5}}{2}$ 对所有 $n$ 成立，故单调递增。

由单调有界准则，$\lim a_n = A$ 存在。令 $A = 1 + \frac{A}{1+A}$，得 $A(1+A) = 1 + A + A$，$A^2 + A = 1 + 2A$，$A^2 - A - 1 = 0$。

$A = \frac{1 + \sqrt{5}}{2}$（取正根）。

---

## 五、两个准则的比较

| 特征 | 夹逼准则 | 单调有界准则 |
|------|---------|------------|
| 用途 | 可直接求出极限值 | 只能证明极限存在 |
| 适用对象 | 数列和函数 | 主要用于数列 |
| 关键步骤 | 构造合适的上下界 | 证明单调性和有界性 |
| 极限值 | 由上下界的极限确定 | 需要额外计算 |
| 难点 | 构造不等式技巧 | 证明单调性 |

---

## 六、综合例题

### 例 9：综合运用两个准则

**题目**：设 $a_n = \sum_{k=1}^{n} \frac{1}{k} - \ln n$，证明 $\{a_n\}$ 收敛。

**证明**：

**单调性**：

$$a_{n+1} - a_n = \frac{1}{n+1} - \ln(n+1) + \ln n = \frac{1}{n+1} - \ln\frac{n+1}{n} = \frac{1}{n+1} - \ln\left(1 + \frac{1}{n}\right)$$

由不等式 $\ln(1+x) > \frac{x}{1+x}$（$x > 0$），取 $x = \frac{1}{n}$：

$$\ln\left(1 + \frac{1}{n}\right) > \frac{\frac{1}{n}}{1 + \frac{1}{n}} = \frac{1}{n+1}$$

故 $a_{n+1} - a_n < 0$，$\{a_n\}$ 单调递减。

**有下界**：

$$a_n = \sum_{k=1}^{n} \frac{1}{k} - \ln n = \sum_{k=1}^{n} \frac{1}{k} - \sum_{k=1}^{n-1} \ln\frac{k+1}{k}$$

$$= 1 + \sum_{k=1}^{n-1}\left(\frac{1}{k+1} - \ln\frac{k+1}{k}\right)$$

由 $\frac{1}{k+1} < \ln\frac{k+1}{k}$（已证），故 $a_n$ 的每一项增量为负，但：

$$a_n > 1 + \sum_{k=1}^{n-1}\left(\frac{1}{k+1} - \frac{1}{k}\right) = 1 + \frac{1}{n} - 1 = \frac{1}{n} > 0$$

故 $a_n > 0$，有下界。

由单调有界准则，$\{a_n\}$ 收敛。此极限称为 **Euler 常数** $\gamma \approx 0.5772$。

---

## 七、易错点提醒

>
> 1. **夹逼准则要求三列的极限相等**：$\lim a_n = \lim c_n = A$，不能只是 $a_n \leq b_n \leq c_n$
> 2. **夹逼准则中不等号方向**：$a_n \leq b_n \leq c_n$，$a_n$ 是下界，$c_n$ 是上界
> 3. **单调有界准则只能证明存在**：求极限值需要在证明存在后利用递推关系
> 4. **证明单调性时**：常用 $a_{n+1} - a_n$ 的符号，或 $\frac{a_{n+1}}{a_n}$ 与 1 的大小关系
> 5. **证明有界性时**：常用数学归纳法
> 6. **递推数列取极限时**：需要先证明极限存在，否则 $A = f(A)$ 的解可能不正确
> 7. **单调性的判断**：不一定整个数列单调，可能从某项开始单调，这不影响结论
> 8. **夹逼准则构造不等式**：常用 $|\sin x| \leq 1$、$|\cos x| \leq 1$、均值不等式等工具

---

## 补充内容

> 武忠祥《2021考研高等数学0基础课》讲义 (5)--1.8笔记小结（极限运算法则）

### 补充一：无穷小的运算法则

>
> **定理1**：两个无穷小的**和**是无穷小。
>
> **定理2**：有界函数与无穷小的**乘积**是无穷小。
>
> **推论1**：常数与无穷小的乘积是无穷小。
>
> **推论2**：有限个无穷小的积仍是无穷小。

> - 无穷小的**和**仍是无穷小（有限个的情况）
> - 无穷小的**乘积**仍是无穷小
> - 但无穷小的**商**不一定是无穷小（$\frac{0}{0}$ 型不定式）
> - **无穷多个**无穷小的和不一定是无穷小

> 经典应用：$\sin\frac{1}{x}$ 有界（$|\sin\frac{1}{x}| \leq 1$），$x$ 是 $x \to 0$ 时的无穷小，故
> $$\lim_{x \to 0} x \sin\frac{1}{x} = 0$$
>
> 注意：此极限**不能用洛必达法则**（因为 $\sin\frac{1}{x}$ 的导数在 $x = 0$ 附近振荡）。

### 补充二：极限四则运算的数列形式

> 设 $\lim_{n \to \infty} a_n = a$，$\lim_{n \to \infty} b_n = b$，则：
>
> (1) $\lim_{n \to \infty}(a_n \pm b_n) = a \pm b$
>
> (2) $\lim_{n \to \infty}(a_n b_n) = ab$
>
> (3) $\lim_{n \to \infty}\frac{a_n}{b_n} = \frac{a}{b}$（$b \neq 0$）

### 补充三：分式函数在 $x \to \infty$ 时的极限公式

> $$\lim_{x \to \infty} \frac{a_n x^n + a_{n-1}x^{n-1} + \cdots + a_1 x + a_0}{b_m x^m + b_{m-1}x^{m-1} + \cdots + b_1 x + b_0} = \begin{cases} \frac{a_n}{b_m}, & n = m \\ 0, & n < m \\ \infty, & n > m \end{cases}$$
>
> **记忆口诀**：$x \to \infty$ 时，分子分母同除最高次幂，"抓大头"。
>
> **例子**：
> - $\lim_{x \to \infty} \frac{3x^2 + 2x - 1}{5x^2 - x + 4} = \frac{3}{5}$
> - $\lim_{x \to \infty} \frac{x^2 - x}{x^3 - 3x + 2} = 0$
> - $\lim_{x \to \infty} \frac{x^3 + 1}{x^2 + x} = \infty$

### 补充四：复合函数极限的求法

> 求复合函数 $f[g(x)]$ 的极限时，可以设中间变量 $u = g(x)$：
>
> 若 $\lim_{x \to x_0} g(x) = u_0$，$\lim_{u \to u_0} f(u) = A$，且在 $x_0$ 附近 $g(x) \neq u_0$，
> 则 $\lim_{x \to x_0} f[g(x)] = A$。
>
> **例子**：求 $\lim_{x \to 0} e^{\frac{\sin x}{x}}$
>
> 设 $u = \frac{\sin x}{x}$，当 $x \to 0$ 时 $u \to 1$，故
> $$\lim_{x \to 0} e^{\frac{\sin x}{x}} = \lim_{u \to 1} e^u = e$$

### 补充五：夹逼准则的更多应用实例

>
> **例**：求 $\lim_{x \to +\infty} (2 + \sin x)^{\frac{1}{x}}$
>
> 由于 $1 \leq 2 + \sin x \leq 3$，故
> $$1^{\frac{1}{x}} \leq (2 + \sin x)^{\frac{1}{x}} \leq 3^{\frac{1}{x}}$$
>
> 而 $\lim_{x \to +\infty} 1^{\frac{1}{x}} = 1$，$\lim_{x \to +\infty} 3^{\frac{1}{x}} = 1$，
>
> 由夹逼准则，$\lim_{x \to +\infty} (2 + \sin x)^{\frac{1}{x}} = 1$。

### 补充六：极限存在法则与两个重要极限

>
> 用夹逼准则证明 $\lim_{x \to 0} \frac{\sin x}{x} = 1$：
>
> 当 $0 < x < \frac{\pi}{2}$ 时，利用几何关系：
> $$\sin x < x < \tan x$$
>
> 各部分除以 $\sin x$（正值）：
> $$1 < \frac{x}{\sin x} < \frac{1}{\cos x}$$
>
> 取倒数：
> $$\cos x < \frac{\sin x}{x} < 1$$
>
> 由于 $\lim_{x \to 0} \cos x = 1$，$\lim_{x \to 0} 1 = 1$，由夹逼准则得 $\lim_{x \to 0} \frac{\sin x}{x} = 1$。

> $$\lim_{\Delta \to 0} \frac{\sin \Delta}{\Delta} = 1 \quad (\Delta \neq 0)$$
>
> 其中 $\Delta$ 可以是任何趋向 $0$ 的表达式。
>
> 例如：$\lim_{x \to 0} \frac{\sin(x^2)}{x^2} = 1$，$\lim_{x \to \infty} x \sin\frac{1}{x} = 1$。

> $$\lim_{x \to \infty}\left(1 + \frac{1}{x}\right)^x = e$$
>
> 等价形式：
> $$\lim_{x \to 0}(1 + x)^{\frac{1}{x}} = e$$
>
> $$\lim_{\Delta \to 0}(1 + \Delta)^{\frac{1}{\Delta}} = e \quad (\Delta \neq 0)$$

### 补充七：两个重要极限的典型应用

>
> $$\lim_{x \to 0} \frac{\tan x}{x} = 1$$
>
> $$\lim_{x \to 0} \frac{1 - \cos x}{x^2} = \frac{1}{2}$$
>
> $$\lim_{x \to 0} \frac{\arctan x}{x} = 1$$
>
> 这些都可以通过第一个重要极限和等价替换推导出来。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 6：函数极限的性质]] — 极限性质
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 10：求极限]] — 求极限
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/01-函数极限连续/Lecture 8：无穷小与无穷大]] — 无穷小
