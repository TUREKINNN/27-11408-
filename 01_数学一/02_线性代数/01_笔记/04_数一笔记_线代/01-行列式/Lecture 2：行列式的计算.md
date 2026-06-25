---
title: Lecture 2：行列式的计算
tags: [考研, 数学一, 线性代数, 数学]
categories: 线性代数
date: 2026-06-16
---
---

# Lecture 2：行列式的计算

行列式的计算是考研线性代数的核心题型之一。本讲系统介绍五种主要方法。

---

## 一、上三角化法（初等行变换法）

### 方法原理

> [!definition|purple] 上三角化法
> 通过初等行变换（主要是倍加变换），将行列式化为上三角形式，然后利用三角行列式的值等于主对角线元素之积来计算。
> $$
> D = \begin{vmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{n1} & a_{n2} & \cdots & a_{nn} \end{vmatrix} \xrightarrow{\text{行变换}} \begin{vmatrix} a_{11}' & a_{12}' & \cdots & a_{1n}' \\ 0 & a_{22}' & \cdots & a_{2n}' \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & a_{nn}' \end{vmatrix} = \prod_{i=1}^{n} a_{ii}'
> $$

**操作步骤：**
1. 选定第1列中某个非零元素（通常是 $a_{11}$）作为主元
2. 利用倍加变换将主元下方的元素全部化为 $0$
3. 对缩小后的子矩阵重复上述过程
4. 直到化为上三角形式

> [!warning|red] 关键注意
> 只能使用**倍加变换**（某行加另一行的 $k$ 倍），这种变换**不改变**行列式的值。不能使用倍乘变换或换行变换（会改变行列式的值或符号）。

### 经典例题

**例1：** 计算 $n$ 阶行列式
$$
D_n = \begin{vmatrix} a & b & b & \cdots & b \\ b & a & b & \cdots & b \\ b & b & a & \cdots & b \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ b & b & b & \cdots & a \end{vmatrix}
$$

**解：** 此行列式的特点是主对角线元素全为 $a$，其余元素全为 $b$。

将第2, 3, ..., $n$ 列都加到第1列上：
$$
D_n = \begin{vmatrix} a+(n-1)b & b & b & \cdots & b \\ a+(n-1)b & a & b & \cdots & b \\ a+(n-1)b & b & a & \cdots & b \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ a+(n-1)b & b & b & \cdots & a \end{vmatrix}
$$

提取第1列公因子 $[a + (n-1)b]$：
$$
= [a+(n-1)b] \begin{vmatrix} 1 & b & b & \cdots & b \\ 1 & a & b & \cdots & b \\ 1 & b & a & \cdots & b \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 1 & b & b & \cdots & a \end{vmatrix}
$$

将第1行乘 $(-1)$ 加到其余各行：
$$
= [a+(n-1)b] \begin{vmatrix} 1 & b & b & \cdots & b \\ 0 & a-b & 0 & \cdots & 0 \\ 0 & 0 & a-b & \cdots & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & 0 & \cdots & a-b \end{vmatrix}
$$

$$
\boxed{D_n = [a + (n-1)b](a-b)^{n-1}}
$$

**例2：** 计算
$$
D = \begin{vmatrix} 1 & 2 & 3 & 4 \\ 2 & 3 & 4 & 1 \\ 3 & 4 & 1 & 2 \\ 4 & 1 & 2 & 3 \end{vmatrix}
$$

**解：** 观察每行元素之和都是 $1+2+3+4 = 10$。

将第2、3、4列加到第1列：
$$
D = \begin{vmatrix} 10 & 2 & 3 & 4 \\ 10 & 3 & 4 & 1 \\ 10 & 4 & 1 & 2 \\ 10 & 1 & 2 & 3 \end{vmatrix} = 10 \begin{vmatrix} 1 & 2 & 3 & 4 \\ 1 & 3 & 4 & 1 \\ 1 & 4 & 1 & 2 \\ 1 & 1 & 2 & 3 \end{vmatrix}
$$

$r_2 - r_1, r_3 - r_1, r_4 - r_1$：
$$
= 10 \begin{vmatrix} 1 & 2 & 3 & 4 \\ 0 & 1 & 1 & -3 \\ 0 & 2 & -2 & -2 \\ 0 & -1 & -1 & -1 \end{vmatrix}
$$

按第1列展开，$r_3 - 2r_2$：
$$
= 10 \begin{vmatrix} 1 & 1 & -3 \\ 2 & -2 & -2 \\ -1 & -1 & -1 \end{vmatrix} = 10 \begin{vmatrix} 1 & 1 & -3 \\ 0 & -4 & 4 \\ 0 & 0 & -4 \end{vmatrix} = 10 \cdot 1 \cdot (-4) \cdot (-4) = 160
$$

---

## 二、按行展开递推法

### 方法原理

> [!definition|purple] 递推法
> 对含有参数 $n$ 的 $n$ 阶行列式 $D_n$，利用按行（列）展开定理，建立 $D_n$ 与低阶行列式（如 $D_{n-1}$、$D_{n-2}$）之间的递推关系，然后求解递推公式。

**常见递推形式：**
- $D_n = a D_{n-1}$ → $D_n = a^{n-1} D_1$
- $D_n = a D_{n-1} + b D_{n-2}$ → 二阶线性递推
- $D_n = a D_{n-1} + b$ → 一阶非齐次递推

### 经典例题

**例3：** 计算三对角行列式（递推法典型）
$$
D_n = \begin{vmatrix} 2 & 1 & 0 & \cdots & 0 & 0 \\ 1 & 2 & 1 & \cdots & 0 & 0 \\ 0 & 1 & 2 & \cdots & 0 & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\ 0 & 0 & 0 & \cdots & 2 & 1 \\ 0 & 0 & 0 & \cdots & 1 & 2 \end{vmatrix}
$$

**解：** 按第1行展开：
$$
D_n = 2 D_{n-1} - 1 \cdot \begin{vmatrix} 1 & 1 & 0 & \cdots & 0 \\ 0 & 2 & 1 & \cdots & 0 \\ 0 & 1 & 2 & \cdots & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & 0 & \cdots & 2 \end{vmatrix}_{n-1}
$$

对右边的行列式按第1列展开，得 $D_{n-2}$。

因此递推关系为：
$$
D_n = 2D_{n-1} - D_{n-2}
$$

初始条件：$D_1 = 2, D_2 = \begin{vmatrix} 2 & 1 \\ 1 & 2 \end{vmatrix} = 3$

特征方程：$r^2 - 2r + 1 = 0$，解得 $r = 1$（二重根）

通解：$D_n = (c_1 + c_2 n) \cdot 1^n = c_1 + c_2 n$

代入初始条件：
- $D_1 = c_1 + c_2 = 2$
- $D_2 = c_1 + 2c_2 = 3$

解得 $c_1 = 1, c_2 = 1$。

$$
\boxed{D_n = n + 1}
$$

**例4：** 计算
$$
D_n = \begin{vmatrix} x & a & a & \cdots & a \\ a & x & a & \cdots & a \\ a & a & x & \cdots & a \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ a & a & a & \cdots & x \end{vmatrix}
$$

**解：** （此题亦可用上三角化法，此处演示递推思路）

按最后一行展开或利用"各行之和相同"的技巧：

将第 $1, 2, \cdots, n-1$ 行都加到第 $n$ 行上，再提取公因子：

$$
D_n = [x + (n-1)a] \begin{vmatrix} 1 & 1 & 1 & \cdots & 1 \\ a & x & a & \cdots & a \\ a & a & x & \cdots & a \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ a & a & a & \cdots & x \end{vmatrix} \xrightarrow{c_i - c_1} [x+(n-1)a](x-a)^{n-1}
$$

---

## 三、范德蒙德（Vandermonde）行列式

> [!theorem|blue] 范德蒙德行列式公式
> $$
> V_n = \begin{vmatrix} 1 & 1 & 1 & \cdots & 1 \\ x_1 & x_2 & x_3 & \cdots & x_n \\ x_1^2 & x_2^2 & x_3^2 & \cdots & x_n^2 \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ x_1^{n-1} & x_2^{n-1} & x_3^{n-1} & \cdots & x_n^{n-1} \end{vmatrix} = \prod_{1 \le i < j \le n} (x_j - x_i)
> $$
> 即 $V_n = (x_2 - x_1)(x_3 - x_1)(x_3 - x_2) \cdots (x_n - x_{n-1})$

**记忆口诀：** "下标大的减下标小的"，所有可能的组合相乘。

**展开形式（$n=3$ 时）：**
$$
V_3 = (x_2 - x_1)(x_3 - x_1)(x_3 - x_2)
$$

> [!tip|blue] 重要推论
> 范德蒙德行列式 $V_n = 0$ 当且仅当存在 $i \neq j$ 使得 $x_i = x_j$。

### 经典例题

**例5：** 计算
$$
D = \begin{vmatrix} 1 & 1 & 1 & 1 \\ 1 & 2 & 3 & 4 \\ 1 & 4 & 9 & 16 \\ 1 & 8 & 27 & 64 \end{vmatrix}
$$

**解：** 这是 $x_1 = 1, x_2 = 2, x_3 = 3, x_4 = 4$ 的范德蒙德行列式。

$$
D = (2-1)(3-1)(4-1)(3-2)(4-2)(4-3) = 1 \cdot 2 \cdot 3 \cdot 1 \cdot 2 \cdot 1 = 12
$$

**例6：** 计算
$$
D = \begin{vmatrix} 1 & 1 & 1 \\ a & b & c \\ a^3 & b^3 & c^3 \end{vmatrix}
$$

**解：** 这不是标准的范德蒙德行列式（缺少 $x^2$ 行），需要变形。

按标准范德蒙德公式展开思路，可以添加一行再消去，或直接计算：

$$
D = \begin{vmatrix} 1 & 1 & 1 \\ a & b & c \\ a^3 & b^3 & c^3 \end{vmatrix}
$$

利用因式分解：$a^3 = a \cdot a^2$，但这不是直接的范德蒙德形式。

可以直接展开：
$$
D = (bc^3 - b^3c) - (ac^3 - a^3c) + (ab^3 - a^3b) = bc(c^2 - b^2) - ac(c^2 - a^2) + ab(b^2 - a^2)
$$
$$
= bc(c-b)(c+b) - ac(c-a)(c+a) + ab(b-a)(b+a)
$$
$$
= (a-b)(b-c)(c-a)(a+b+c)
$$

> [!tip|blue] 方法总结
> 遇到"类范德蒙德"行列式，可以：
> 1. 尝试凑成标准范德蒙德形式
> 2. 利用因式分解提取公因子
> 3. 直接展开并分组因式分解

---

## 四、拉普拉斯（Laplace）展开

> [!theorem|blue] 拉普拉斯展开定理
> 在 $n$ 阶行列式 $D$ 中，任意选定 $k$ 行（$1 \le k \le n-1$），则 $D$ 等于这 $k$ 行元素的所有 $k$ 阶子式与其对应代数余子式乘积之和。

> [!definition|purple] k阶子式与代数余子式
> 选定 $k$ 行 $i_1 < i_2 < \cdots < i_k$ 和 $k$ 列 $j_1 < j_2 < \cdots < j_k$，它们交叉处的 $k^2$ 个元素构成的 $k$ 阶行列式称为一个 **$k$ 阶子式** $M$。
>
> 划去这 $k$ 行和 $k$ 列后，剩余元素构成的 $(n-k)$ 阶行列式乘以符号 $(-1)^{(i_1+\cdots+i_k)+(j_1+\cdots+j_k)}$ 称为 $M$ 的**代数余子式**。

**最常用的情形：拉普拉斯展开取2行**

### 经典例题

**例7：** 利用拉普拉斯展开计算
$$
D = \begin{vmatrix} a & 0 & 0 & b \\ 0 & a & b & 0 \\ 0 & b & a & 0 \\ b & 0 & 0 & a \end{vmatrix}
$$

**解：** 选取第1、4行进行拉普拉斯展开。

第1、4行的2阶子式有 $\binom{4}{2} = 6$ 个，但很多为零：

选列 $\{1, 4\}$：$\begin{vmatrix} a & b \\ b & a \end{vmatrix} = a^2 - b^2$，代数余子式为 $(-1)^{(1+4)+(1+4)} \begin{vmatrix} a & b \\ b & a \end{vmatrix} = (a^2 - b^2)$

选列 $\{2, 3\}$：$\begin{vmatrix} 0 & 0 \\ 0 & 0 \end{vmatrix} = 0$

选列 $\{1, 2\}$：$\begin{vmatrix} a & 0 \\ b & 0 \end{vmatrix} = 0$

选列 $\{1, 3\}$：$\begin{vmatrix} a & 0 \\ b & 0 \end{vmatrix} = 0$

选列 $\{3, 4\}$：$\begin{vmatrix} 0 & b \\ 0 & a \end{vmatrix} = 0$

选列 $\{2, 4\}$：$\begin{vmatrix} 0 & b \\ 0 & a \end{vmatrix} = 0$

所以 $D = (a^2 - b^2)(a^2 - b^2) = (a^2 - b^2)^2$。

> [!tip|blue] 拉普拉斯展开适用场景
> 当行列式有较多零元素，特别是集中在某些行和列时，拉普拉斯展开比逐行展开更高效。

---

## 五、三对角线行列式

> [!definition|purple] 三对角线行列式
> 形如
> $$
> D_n = \begin{vmatrix} a_1 & b_1 & 0 & \cdots & 0 & 0 \\ c_1 & a_2 & b_2 & \cdots & 0 & 0 \\ 0 & c_2 & a_3 & b_3 & \cdots & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\ 0 & 0 & 0 & \cdots & a_{n-1} & b_{n-1} \\ 0 & 0 & 0 & \cdots & c_{n-1} & a_n \end{vmatrix}
> $$
> 即只有主对角线、主对角线上方和下方共三条对角线上有非零元素。

### 递推公式

按最后一行展开：
$$
D_n = a_n D_{n-1} - c_{n-1} b_{n-1} D_{n-2}
$$

> [!theorem|blue] 三对角行列式递推公式
> $$
> D_n = a_n D_{n-1} - b_{n-1} c_{n-1} D_{n-2}
> $$
> 初始条件：$D_1 = a_1$，$D_2 = a_1 a_2 - b_1 c_1$

### 经典例题

**例8：** 计算
$$
D_n = \begin{vmatrix} \alpha+\beta & \alpha\beta & 0 & \cdots & 0 \\ 1 & \alpha+\beta & \alpha\beta & \cdots & 0 \\ 0 & 1 & \alpha+\beta & \cdots & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & 0 & \cdots & \alpha+\beta \end{vmatrix}
$$

**解：** 这是三对角行列式，其中 $a_i = \alpha + \beta$，$b_i = \alpha\beta$，$c_i = 1$。

递推关系：
$$
D_n = (\alpha+\beta) D_{n-1} - \alpha\beta \cdot D_{n-2}
$$

特征方程：$r^2 - (\alpha+\beta)r + \alpha\beta = 0$，即 $(r-\alpha)(r-\beta) = 0$

解得 $r_1 = \alpha, r_2 = \beta$。

**情况1：$\alpha \neq \beta$**

$D_n = c_1 \alpha^n + c_2 \beta^n$

代入初始条件：
- $D_1 = \alpha + \beta = c_1 \alpha + c_2 \beta$
- $D_2 = (\alpha+\beta)^2 - \alpha\beta = \alpha^2 + \alpha\beta + \beta^2 = c_1 \alpha^2 + c_2 \beta^2$

解得 $c_1 = \frac{\alpha}{\alpha - \beta}$，$c_2 = \frac{-\beta}{\alpha - \beta}$

$$
\boxed{D_n = \frac{\alpha^{n+1} - \beta^{n+1}}{\alpha - \beta}}
$$

**情况2：$\alpha = \beta$**

特征方程有二重根，$D_n = (c_1 + c_2 n) \alpha^n$

代入 $D_1 = 2\alpha$，$D_2 = 3\alpha^2$，解得 $c_1 = c_2 = 1$

$$
\boxed{D_n = (n+1) \alpha^n}
$$

---

## 六、方法选择策略

> [!tip|blue] 计算行列式的决策树
> 1. **观察结构特征：**
>    - 行元素和列元素之和相同 → 上三角化法（"各行加到一行"）
>    - 三对角线结构 → 递推法
>    - 幂次排列 → 范德蒙德公式
>    - 大量零集中在某几行/列 → 拉普拉斯展开
> 2. **一般方法优先级：**
>    - 先试上三角化法（最通用）
>    - 再试按行展开（化零后展开）
>    - 最后考虑特殊公式

---

## 七、易错点总结

> [!warning|red] 常见错误清单
> 1. **范德蒙德行列式公式记错**：注意是 $\prod_{i<j}(x_j - x_i)$，下标大的在前
> 2. **递推关系求错**：展开时注意子行列式的阶数和余子式符号
> 3. **拉普拉斯展开符号**：代数余子式的指数是**行列指标之和**
> 4. **上三角化时只能用倍加变换**：不能交换行（会变号），不能某行乘常数（要乘回来）
> 5. **三对角递推初始值**：$D_1$ 和 $D_2$ 的值必须准确
> 6. **特征方程有重根时**：通解形式为 $(c_1 + c_2 n) r^n$，不要遗漏 $n$
> 7. **提取公因子后行列式的变化**：某行提取 $k$ 后，行列式乘以 $k$，别忘了
> 8. **范德蒙德的非标准形式**：缺少某幂次行时不能直接套公式

---

## 八、考研真题常见类型

| 类型 | 典型形式 | 首选方法 |
|------|---------|---------|
| 全同一元素型 | 主对角 $a$，其余 $b$ | 上三角化 |
| 三对角线型 | 仅三条对角线非零 | 递推法 |
| 范德蒙德型 | 幂次排列 | 公式法 |
| 爪型 | 首行首列特殊 | 按行展开 |
| 副对角型 | 反对角线结构 | 换行化标准 |

> [!tip|blue] 考研重点
> 范德蒙德行列式和三对角行列式是考研高频考点，必须熟练掌握公式和递推方法。上三角化法是万能方法，适用于各种结构的行列式。

---

## 关联知识点

- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/01-行列式/Lecture 1：行列式的定义与性质]] — 行列式定义
- [[01_数学一/02_线性代数/01_笔记/04_数一笔记_线代/Lecture 3：矩阵的定义及其基本运算]] — 矩阵
