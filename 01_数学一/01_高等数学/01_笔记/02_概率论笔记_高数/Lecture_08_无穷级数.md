---
title: Lecture 08 - 无穷级数
subject: 高等数学
chapter: 第七章
lecture: 08
created: 2026-06-17
updated: 2026-06-17
  - 武忠祥《高数基础篇》
  - 《基础过关660题》高数篇
  - 张宇零基础通关讲义
  - 武忠祥《严选题》
difficulty: 基础
---

# Lecture 08: 无穷级数

## 一、常数项级数的概念

### 1.1 级数的定义

<span style="background-color: #ccc1d9">**定义（常数项级数）**</span> 给定一个数列 $u_1, u_2, u_3, \cdots, u_n, \cdots$，则表达式

$$u_1 + u_2 + u_3 + \cdots + u_n + \cdots$$

称为**常数项级数**，记作 $\sum_{n=1}^{\infty} u_n$，其中 $u_n$ 称为级数的**通项**。

### 1.2 级数的部分和

<span style="background-color: #ccc1d9">**定义（部分和）**</span> 级数 $\sum_{n=1}^{\infty} u_n$ 的前 $n$ 项和

$$S_n = u_1 + u_2 + \cdots + u_n$$

称为级数的**部分和**。

---

## 二、级数的收敛与发散

### 2.1 收敛的定义

<span style="background-color: #ccc1d9">**定义（级数收敛）**</span> 若级数 $\sum_{n=1}^{\infty} u_n$ 的部分和数列 $\{S_n\}$ 的极限存在，即 $\lim_{n \to \infty} S_n = S$（$S$ 为有限常数），则称级数**收敛**，$S$ 称为级数的**和**，记作

$$\sum_{n=1}^{\infty} u_n = S$$

若 $\lim_{n \to \infty} S_n$ 不存在，则称级数**发散**。

---

## 三、收敛级数的基本性质

<span style="background-color: #8db3e2">**定理（级数的基本性质）**</span>

1. **线性性质**：若 $\sum u_n = S$，$\sum v_n = T$，则 $\sum(\alpha u_n + \beta v_n) = \alpha S + \beta T$（$\alpha, \beta$ 为常数）

2. **有限项不影响敛散性**：去掉或加上有限项不改变级数的敛散性

3. **收敛级数的结合律**：收敛级数可以任意加括号

<span style="background-color: #8db3e2">**定理（发散判定）**</span> 若 $\sum u_n$ 收敛，则 $\lim_{n \to \infty} u_n = 0$（即收敛级数的通项必趋于零）

---

## 四、级数收敛的必要条件

<span style="background-color: #8db3e2">**定理（级数收敛的必要条件）**</span> 若 $\sum_{n=1}^{\infty} u_n$ 收敛，则 $\lim_{n \to \infty} u_n = 0$。

**逆否命题**：若 $\lim_{n \to \infty} u_n \neq 0$，则级数必发散。

**注意**：$\lim_{n \to \infty} u_n = 0$ 是必要条件，不是充分条件。

---

## 五、正项级数及其判别法

### 5.1 正项级数的定义

<span style="background-color: #ccc1d9">**定义（正项级数）**</span> 若 $u_n \geq 0$（$n = 1, 2, \cdots$），则称 $\sum_{n=1}^{\infty} u_n$ 为**正项级数**。

### 5.2 比较判别法

<span style="background-color: #8db3e2">**定理（比较判别法）**</span> 设两个正项级数 $\sum u_n$ 和 $\sum v_n$（$v_n > 0$）：

1. 若 $u_n \leq v_n$ 且 $\sum v_n$ 收敛，则 $\sum u_n$ 也收敛
2. 若 $u_n \geq v_n$ 且 $\sum v_n$ 发散，则 $\sum u_n$ 也发散

**推论（比较判别法的极限形式）**：若 $\lim_{n \to \infty} \frac{u_n}{v_n} = l$：

- $0 \leq l < +\infty$：若 $\sum v_n$ 收敛，则 $\sum u_n$ 收敛
- $0 < l \leq +\infty$：若 $\sum v_n$ 发散，则 $\sum u_n$ 发散

### 5.3 比值判别法（达朗贝尔判别法）

<span style="background-color: #8db3e2">**定理（比值判别法）**</span> 设正项级数 $\sum u_n$（$u_n > 0$），若

$$\lim_{n \to \infty} \frac{u_{n+1}}{u_n} = \rho$$

则：
- $\rho < 1$ 时，级数**收敛**
- $\rho > 1$ 时，级数**发散**
- $\rho = 1$ 时，判别法**失效**

### 5.4 根值判别法（柯西判别法）

<span style="background-color: #8db3e2">**定理（根值判别法）**</span> 设正项级数 $\sum u_n$，若

$$\lim_{n \to \infty} \sqrt[n]{u_n} = \rho$$

则：
- $\rho < 1$ 时，级数**收敛**
- $\rho > 1$ 时，级数**发散**
- $\rho = 1$ 时，判别法**失效**

---

## 六、几何级数与 p 级数

### 6.1 几何级数

<span style="background-color: #ccc1d9">**定义（几何级数）**</span> 级数 $\sum_{n=0}^{\infty} aq^n = a + aq + aq^2 + \cdots$ 称为**几何级数**（等比级数）。

<span style="background-color: #8db3e2">**定理（几何级数的敛散性）**</span>
- $|q| < 1$ 时，几何级数**收敛**，和为 $\frac{a}{1-q}$
- $|q| \geq 1$ 时，几何级数**发散**

### 6.2 p 级数

<span style="background-color: #ccc1d9">**定义（p 级数）**</span> 级数 $\sum_{n=1}^{\infty} \frac{1}{n^p}$ 称为 **p 级数**。

<span style="background-color: #8db3e2">**定理（p 级数的敛散性）**</span>
- $p > 1$ 时，p 级数**收敛**
- $p \leq 1$ 时，p 级数**发散**

**特例**：当 $p = 1$ 时，得到**调和级数** $\sum_{n=1}^{\infty} \frac{1}{n}$，它是发散的。

---

## 七、交错级数与莱布尼茨判别法

### 7.1 交错级数

<span style="background-color: #ccc1d9">**定义（交错级数）**</span> 各项符号正负相间的级数，即 $u_1 - u_2 + u_3 - u_4 + \cdots$，其中 $u_n > 0$。

### 7.2 莱布尼茨判别法

<span style="background-color: #8db3e2">**定理（莱布尼茨判别法）**</span> 若交错级数 $\sum_{n=1}^{\infty} (-1)^{n-1} u_n$（$u_n > 0$）满足：
1. $u_n \geq u_{n+1}$（单调递减）
2. $\lim_{n \to \infty} u_n = 0$

则级数**收敛**，且其和 $S \leq u_1$，余项 $R_n$ 的绝对值 $|R_n| \leq u_{n+1}$。

---

## 八、任意项级数的绝对收敛与条件收敛

### 8.1 绝对收敛

<span style="background-color: #ccc1d9">**定义（绝对收敛）**</span> 若 $\sum_{n=1}^{\infty} |u_n|$ 收敛，则称 $\sum_{n=1}^{\infty} u_n$ **绝对收敛**。

### 8.2 条件收敛

<span style="background-color: #ccc1d9">**定义（条件收敛）**</span> 若 $\sum_{n=1}^{\infty} u_n$ 收敛，而 $\sum_{n=1}^{\infty} |u_n|$ 发散，则称 $\sum_{n=1}^{\infty} u_n$ **条件收敛**。

### 8.3 绝对收敛与收敛的关系

<span style="background-color: #8db3e2">**定理（绝对收敛的性质）**</span>
1. 若 $\sum |u_n|$ 收敛，则 $\sum u_n$ 必收敛
2. 绝对收敛的级数可以任意重排，其和不变（绝对收敛级数具有可交换性）

---

## 九、函数项级数的收敛域

### 9.1 函数项级数的定义

<span style="background-color: #ccc1d9">**定义（函数项级数）**</span> 表达式 $\sum_{n=1}^{\infty} u_n(x)$ 称为**函数项级数**。

### 9.2 收敛点与收敛域

<span style="background-color: #ccc1d9">**定义（收敛点与收敛域）**</span> 若对 $x_0$，极限 $\lim_{n \to \infty} S_n(x_0)$ 存在，则称 $x_0$ 为级数的**收敛点**，所有收敛点的集合称为**收敛域**。

### 9.3 和函数

<span style="background-color: #ccc1d9">**定义（和函数）**</span> 在收敛域内，函数项级数的和是 $x$ 的函数，记作 $S(x) = \sum_{n=1}^{\infty} u_n(x)$，称为级数的**和函数**。

---

## 十、幂级数的概念

### 10.1 幂级数的定义

<span style="background-color: #ccc1d9">**定义（幂级数）**</span> 形如

$$\sum_{n=0}^{\infty} a_n (x - x_0)^n = a_0 + a_1(x - x_0) + a_2(x - x_0)^2 + \cdots$$

的函数项级数称为**幂级数**。特别地，当 $x_0 = 0$ 时，为

$$\sum_{n=0}^{\infty} a_n x^n = a_0 + a_1 x + a_2 x^2 + \cdots$$

---

## 十一、幂级数的收敛半径、收敛区间、收敛域

### 11.1 收敛半径的存在性

<span style="background-color: #8db3e2">**定理（阿贝尔定理）**</span> 幂级数 $\sum_{n=0}^{\infty} a_n x^n$ 的收敛性有且仅有以下三种可能：
1. 仅在 $x = 0$ 处收敛
2. 在整个实数轴上收敛
3. 在某个正数 $R$ 内收敛，在 $|x| > R$ 时发散

### 11.2 收敛半径

<span style="background-color: #ccc1d9">**定义（收敛半径）**</span> 上述定理中的正数 $R$ 称为幂级数 $\sum_{n=0}^{\infty} a_n x^n$ 的**收敛半径**，开区间 $(-R, R)$ 称为**收敛区间**。

<span style="background-color: #8db3e2">**定理（收敛半径公式）**</span> 若

$$\lim_{n \to \infty} \left|\frac{a_{n+1}}{a_n}\right| = \rho$$

或

$$\lim_{n \to \infty} \sqrt[n]{|a_n|} = \rho$$

则收敛半径 $R = \frac{1}{\rho}$（$\rho = 0$ 时 $R = +\infty$，$\rho = +\infty$ 时 $R = 0$）。

### 11.3 收敛域的确定

<span style="background-color: #8db3e2">**定理（收敛域的确定）**</span> 求出收敛半径 $R$ 后，再考察 $x = \pm R$ 处的敛散性，从而确定收敛域。

---

## 十二、幂级数的运算性质

### 12.1 四则运算

<span style="background-color: #8db3e2">**定理（幂级数的四则运算）**</span> 设幂级数 $\sum a_n x^n$ 和 $\sum b_n x^n$ 的收敛半径分别为 $R_1$、$R_2$，令 $R = \min\{R_1, R_2\}$，则在 $(-R, R)$ 内有：
1. $\sum a_n x^n \pm \sum b_n x^n = \sum (a_n \pm b_n) x^n$
2. $(\sum a_n x^n)(\sum b_n x^n) = \sum (a_n * b_n) x^n$

### 12.2 逐项求导

<span style="background-color: #8db3e2">**定理（逐项求导）**</span> 若幂级数 $\sum_{n=0}^{\infty} a_n x^n$ 的收敛半径为 $R$，和函数为 $S(x)$，则在 $(-R, R)$ 内：
1. $S(x)$ 连续
2. $S(x)$ 可导，且 $S'(x) = \sum_{n=1}^{\infty} n a_n x^{n-1}$（逐项求导后收敛半径不变）

### 12.3 逐项积分

<span style="background-color: #8db3e2">**定理（逐项积分）**</span> 在 $(-R, R)$ 内：

$$\int_0^x S(t) dt = \sum_{n=0}^{\infty} \int_0^x a_n t^n dt = \sum_{n=0}^{\infty} \frac{a_n}{n+1} x^{n+1}$$

（逐项积分后收敛半径也不变）

---

## 十三、幂级数的和函数

### 13.1 求和函数的方法

1. **逐项求导法**：将幂级数转化为已知级数求和
2. **逐项积分法**：将幂级数转化为已知级数求和
3. **利用已知展开式**：如 $\frac{1}{1-x} = \sum_{n=0}^{\infty} x^n$（$|x| < 1$）

---

## 十四、泰勒级数

### 14.1 泰勒级数的定义

<span style="background-color: #ccc1d9">**定义（泰勒级数）**</span> 若函数 $f(x)$ 在 $x_0$ 的某邻域内任意阶可导，则幂级数

$$f(x_0) + f'(x_0)(x - x_0) + \frac{f''(x_0)}{2!}(x - x_0)^2 + \cdots + \frac{f^{(n)}(x_0)}{n!}(x - x_0)^n + \cdots$$

称为 $f(x)$ 在 $x_0$ 处的**泰勒级数**，记作 $T(x)$。

### 14.2 麦克劳林级数

<span style="background-color: #ccc1d9">**定义（麦克劳林级数）**</span> 当 $x_0 = 0$ 时的泰勒级数

$$f(0) + f'(0)x + \frac{f''(0)}{2!}x^2 + \cdots + \frac{f^{(n)}(0)}{n!}x^n + \cdots$$

称为 $f(x)$ 的**麦克劳林级数**。

### 14.3 函数能展开成泰勒级数的条件

<span style="background-color: #8db3e2">**定理（泰勒展开的余项）**</span> $f(x)$ 在 $x_0$ 的某邻域内能展开成泰勒级数的充要条件是：余项 $R_n(x)$ 在 $n \to \infty$ 时趋于零，即

$$\lim_{n \to \infty} R_n(x) = 0$$

其中 $R_n(x) = \frac{f^{(n+1)}(\xi)}{(n+1)!}(x - x_0)^{n+1}$（拉格朗日余项），$\xi$ 介于 $x$ 与 $x_0$ 之间。

---

## 十五、常见函数的幂级数展开

### 15.1 基本展开式

<span style="background-color: #8db3e2">**定理（常用函数的麦克劳林展开）**</span>

1. **指数函数**：
$$e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots + \frac{x^n}{n!} + \cdots \quad (|x| < \infty)$$

2. **正弦函数**：
$$\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \cdots + (-1)^n \frac{x^{2n+1}}{(2n+1)!} + \cdots \quad (|x| < \infty)$$

3. **余弦函数**：
$$\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \cdots + (-1)^n \frac{x^{2n}}{(2n)!} + \cdots \quad (|x| < \infty)$$

4. **对数函数**：
$$\ln(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \cdots + (-1)^{n-1} \frac{x^n}{n} + \cdots \quad (-1 < x \leq 1)$$

5. **几何级数**：
$$\frac{1}{1-x} = 1 + x + x^2 + x^3 + \cdots + x^n + \cdots \quad (|x| < 1)$$

6. **二项式展开**：
$$(1+x)^\alpha = 1 + \alpha x + \frac{\alpha(\alpha-1)}{2!}x^2 + \cdots + \frac{\alpha(\alpha-1)\cdots(\alpha-n+1)}{n!}x^n + \cdots \quad (|x| < 1)$$

---

## 十六、傅里叶级数的概念

### 16.1 傅里叶级数的定义

<span style="background-color: #ccc1d9">**定义（傅里叶级数）**</span> 设 $f(x)$ 在 $[-l, l]$ 上可积，则称

$$a_0 + \sum_{n=1}^{\infty} (a_n \cos\frac{n\pi x}{l} + b_n \sin\frac{n\pi x}{l})$$

为 $f(x)$ 在 $[-l, l]$ 上的**傅里叶级数**，记作

$$f(x) \sim a_0 + \sum_{n=1}^{\infty} (a_n \cos\frac{n\pi x}{l} + b_n \sin\frac{n\pi x}{l})$$

其中系数

$$a_n = \frac{1}{l} \int_{-l}^{l} f(x) \cos\frac{n\pi x}{l} dx, \quad b_n = \frac{1}{l} \int_{-l}^{l} f(x) \sin\frac{n\pi x}{l} dx$$

---

## 十七、狄利克雷收敛定理

<span style="background-color: #8db3e2">**定理（狄利克雷收敛定理）**</span> 设 $f(x)$ 满足：
1. 在 $[-l, l]$ 上连续或只有有限个第一类间断点
2. 在 $[-l, l]$ 上只有有限个极值点

则 $f(x)$ 的傅里叶级数在 $[-l, l]$ 上处处收敛，且收敛于：
- $f(x)$，当 $x$ 为 $f(x)$ 的连续点
- $\frac{f(x^+) + f(x^-)}{2}$，当 $x$ 为 $f(x)$ 的间断点
- $\frac{f(-l^+) + f(l^-)}{2}$，当 $x = \pm l$

---

## 十八、函数在[-l, l]上的傅里叶级数

### 18.1 周期延拓

若 $f(x)$ 定义在 $[-l, l]$ 上，可以将其延拓为周期为 $2l$ 的周期函数，然后展开为傅里叶级数。

### 18.2 偶函数与奇函数的傅里叶级数

<span style="background-color: #8db3e2">**定理（偶函数的傅里叶级数）**</span> 若 $f(x)$ 为偶函数，则 $b_n = 0$，傅里叶级数只含余弦项（余弦级数）：

$$f(x) \sim a_0 + \sum_{n=1}^{\infty} a_n \cos\frac{n\pi x}{l}$$

其中 $a_n = \frac{2}{l} \int_{0}^{l} f(x) \cos\frac{n\pi x}{l} dx$

<span style="background-color: #8db3e2">**定理（奇函数的傅里叶级数）**</span> 若 $f(x)$ 为奇函数，则 $a_n = 0$，傅里叶级数只含正弦项（正弦级数）：

$$f(x) \sim \sum_{n=1}^{\infty} b_n \sin\frac{n\pi x}{l}$$

其中 $b_n = \frac{2}{l} \int_{0}^{l} f(x) \sin\frac{n\pi x}{l} dx$

---

## 十九、函数在[0, l]上的正弦级数和余弦级数

### 19.1 正弦级数（奇延拓）

将 $f(x)$（$0 < x < l$）奇延拓到 $(-l, 0)$，得到奇函数 $g(x)$，再展开为正弦级数。

### 19.2 余弦级数（偶延拓）

将 $f(x)$（$0 < x < l$）偶延拓到 $(-l, 0)$，得到偶函数 $g(x)$，再展开为余弦级数。

---

## 二十、典型例题

### 例题1：判断级数的敛散性

**题目**：判断级数 $\sum_{n=1}^{\infty} \frac{1}{2^n}$ 的敛散性。

**思路**：这是几何级数，公比 $q = \frac{1}{2}$，$|q| < 1$，故收敛。

**解答**：

几何级数，公比 $q = \frac{1}{2}$，$|q| < 1$，故级数收敛，和为：

$$S = \frac{a}{1-q} = \frac{1}{1-\frac{1}{2}} = 2$$

**总结**：几何级数 $|q| < 1$ 时收敛。

---

### 例题2：p 级数的敛散性

**题目**：判断级数 $\sum_{n=1}^{\infty} \frac{1}{n^2}$ 的敛散性。

**思路**：这是 p 级数，$p = 2 > 1$，故收敛。

**解答**：

p 级数，$p = 2 > 1$，故级数收敛。

**总结**：p 级数 $p > 1$ 时收敛，$p \leq 1$ 时发散。

---

### 例题3：比较判别法

**题目**：判断级数 $\sum_{n=1}^{\infty} \frac{1}{n^2 + 1}$ 的敛散性。

**思路**：与 p 级数比较，$\frac{1}{n^2 + 1} \sim \frac{1}{n^2}$。

**解答**：

由于 $\lim_{n \to \infty} \frac{\frac{1}{n^2+1}}{\frac{1}{n^2}} = 1$，而 $\sum \frac{1}{n^2}$ 收敛，故原级数收敛。

**总结**：比较判别法适用于已知敛散性的级数作比较。

---

### 例题4：幂级数的收敛半径

**题目**：求幂级数 $\sum_{n=1}^{\infty} \frac{x^n}{n}$ 的收敛半径和收敛域。

**思路**：利用比值判别法求收敛半径。

**解答**：

$$a_n = \frac{1}{n}, \quad \lim_{n \to \infty} \left|\frac{a_{n+1}}{a_n}\right| = \lim_{n \to \infty} \frac{n}{n+1} = 1$$

故收敛半径 $R = 1$。

在 $x = 1$ 处：$\sum_{n=1}^{\infty} \frac{1}{n}$ 为调和级数，发散。

在 $x = -1$ 处：$\sum_{n=1}^{\infty} \frac{(-1)^n}{n}$ 为交错调和级数，收敛（条件收敛）。

故收敛域为 $[-1, 1)$（不含 $x = 1$）。

**总结**：求幂级数收敛半径用 $\lim |\frac{a_{n+1}}{a_n}|$ 或 $\lim \sqrt[n]{|a_n|}$。

---

### 例题5：求和函数

**题目**：求幂级数 $\sum_{n=0}^{\infty} x^n = 1 + x + x^2 + \cdots$ 的和函数。

**思路**：利用几何级数求和公式。

**解答**：

当 $|x| < 1$ 时，几何级数的和为：

$$S(x) = \frac{1}{1-x}$$

**总结**：$\sum_{n=0}^{\infty} x^n = \frac{1}{1-x}$（$|x| < 1$）。

---

### 例题6：函数的幂级数展开

**题目**：将 $f(x) = e^x$ 展开成麦克劳林级数。

**思路**：利用指数函数的麦克劳林展开公式。

**解答**：

$$e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots + \frac{x^n}{n!} + \cdots \quad (|x| < \infty)$$

**总结**：记住 $e^x$ 的展开式是基础。

---

## 二十一、解题方法总结

### 21.1 正项级数判别法选择

| 方法 | 适用情况 |
|------|---------|
| 比较判别法 | 已知某级数敛散性 |
| 比值判别法 | $u_n$ 含阶乘或幂函数 |
| 根值判别法 | $u_n$ 含 $n$ 次方 |

### 21.2 级数审敛流程

1. 检查 $\lim_{n \to \infty} u_n = 0$ 是否成立
2. 若不成立，则发散
3. 若成立，再判断是正项级数还是交错级数
4. 选择合适的判别法

### 21.3 幂级数求收敛域步骤

1. 求 $\lim |\frac{a_{n+1}}{a_n}|$ 或 $\lim \sqrt[n]{|a_n|}$
2. 得收敛半径 $R$
3. 单独判断 $x = \pm R$ 处的敛散性

---

## 参考答案提示

1. 收敛，和为 2

2. 收敛

3. 收敛

4. $R = 1$，收敛域 $[-1, 1)$

5. $S(x) = \frac{1}{1-x}$（$|x| < 1$）

6. $e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!}$

---

> **注**：本 Lecture 内容涵盖常数项级数、幂级数、傅里叶级数的基本概念、敛散性判别方法及典型例题。重点掌握正项级数的比较判别法、比值判别法和幂级数的收敛半径求法。建议结合《基础过关660题》高数篇第121-130题进行练习巩固。
