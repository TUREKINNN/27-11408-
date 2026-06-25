---
title: Lecture 06 - 二次型
subject: 线性代数
chapter: 第六章
lecture: 06
created: 2026-06-17
updated: 2026-06-17
  - 李永乐《线性代数基础》
  - 《基础过关660题》线代篇
  - 张宇《基础30讲》线代
  - 张宇《线性代数9讲》
difficulty: 基础
---

# Lecture 06: 二次型

## 一、二次型的概念

### 1.1 二次型的定义

<span style="background-color: #ccc1d9">**定义（二次型）**</span> 含有 $n$ 个变量 $x_1, x_2, \cdots, x_n$ 的二次齐次多项式

$$f(x_1, x_2, \cdots, x_n) = \sum_{i=1}^{n} \sum_{j=1}^{n} a_{ij}x_i x_j \quad (a_{ij} = a_{ji})$$

称为 $n$ 元**二次型**，简称**二次型**。

### 1.2 二次型的矩阵形式

<span style="background-color: #ccc1d9">**定义（二次型的矩阵）**</span> 二次型 $f = \mathbf{x}^T\mathbf{A}\mathbf{x}$ 中，$\mathbf{A}$ 为对称矩阵，称 $\mathbf{A}$ 为二次型 $f$ 的**矩阵**，$r(\mathbf{A})$ 称为二次型的**秩**。

记 $\mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix}$，则

$$f(x_1, x_2, \cdots, x_n) = \mathbf{x}^T \begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & & \vdots \\ a_{n1} & a_{n2} & \cdots & a_{nn} \end{bmatrix} \mathbf{x}$$

---

## 二、二次型的矩阵表示

### 2.1 对称矩阵的构造

对于二次型 $f(x_1, x_2, \cdots, x_n) = \sum_{i,j} a_{ij}x_i x_j$，其矩阵 $\mathbf{A}$ 的元素满足：

- $a_{ii}$ 是 $x_i^2$ 的系数
- $a_{ij} = a_{ji}$ 是 $x_i x_j$ 系数的一半（$i \neq j$）

### 2.2 示例

二次型 $f(x_1, x_2, x_3) = x_1^2 + 2x_2^2 + 3x_3^2 + 4x_1x_2 + 5x_1x_3 + 6x_2x_3$

对应的矩阵：

$$\mathbf{A} = \begin{bmatrix} 1 & 2 & \frac{5}{2} \\ 2 & 2 & 3 \\ \frac{5}{2} & 3 & 3 \end{bmatrix}$$

---

## 三、合同变换

### 3.1 合同矩阵的定义

<span style="background-color: #ccc1d9">**定义（合同矩阵）**</span> 设 $\mathbf{A}, \mathbf{B}$ 均为 $n$ 阶矩阵，若存在可逆矩阵 $\mathbf{C}$ 使得

$$\mathbf{C}^T \mathbf{A} \mathbf{C} = \mathbf{B}$$

则称 $\mathbf{A}$ 与 $\mathbf{B}$ **合同**，记作 $\mathbf{A} \simeq \mathbf{B}$。

### 3.2 合同变换的性质

<span style="background-color: #8db3e2">**性质**</span>
- 若 $\mathbf{A} \simeq \mathbf{B}$，则 $r(\mathbf{A}) = r(\mathbf{B})$
- 若 $\mathbf{A}$ 为对称矩阵，则 $\mathbf{C}^T \mathbf{A} \mathbf{C}$ 也是对称矩阵
- 合同变换不改变二次型的正定性

---

## 四、二次型的标准形与规范形

### 4.1 标准形

<span style="background-color: #ccc1d9">**定义（标准形）**</span> 只含平方项的二次型称为**标准形**：

$$f = d_1 y_1^2 + d_2 y_2^2 + \cdots + d_n y_n^2$$

### 4.2 规范形

<span style="background-color: #ccc1d9">**定义（规范形）**</span> 标准形中正平方项系数化为 $1$，负平方项系数化为 $-1$，零项不变：

$$f = y_1^2 + \cdots + y_p^2 - y_{p+1}^2 - \cdots - y_{p+q}^2$$

其中 $p$ 称为**正惯性指数**，$q$ 称为**负惯性指数**。

### 4.3 化二次型为标准形的方法

**配方法**：通过配方将混合项消去，化为平方和。

**正交变换法**：利用特征值和特征向量，$\mathbf{x} = \mathbf{Q}\mathbf{y}$，其中 $\mathbf{Q}$ 为正交矩阵。

---

## 五、惯性定理

<span style="background-color: #8db3e2">**定理（惯性定理）**</span> 任意二次型 $f = \mathbf{x}^T \mathbf{A} \mathbf{x}$ 经过可逆线性变换 $\mathbf{x} = \mathbf{C}\mathbf{y}$ 化为标准形后，其正平方项的个数 $p$（正惯性指数）和负平方项的个数 $q$（负惯性指数）保持不变。

<span style="background-color: #8db3e2">**推论**</span> 任意二次型 $f = \mathbf{x}^T \mathbf{A} \mathbf{x}$ 合同于对角矩阵 $\text{diag}(1,\cdots,1,-1,\cdots,-1,0,\cdots,0)$，其中正惯性指数 $p$ 和负惯性指数 $q$ 由 $\mathbf{A}$ 唯一确定。

---

## 六、正定二次型与正定矩阵

### 6.1 正定二次型的定义

<span style="background-color: #ccc1d9">**定义（正定二次型）**</span> 对于二次型 $f(\mathbf{x}) = \mathbf{x}^T \mathbf{A} \mathbf{x}$，若对任意非零向量 $\mathbf{x} \in \mathbb{R}^n$，都有 $f(\mathbf{x}) > 0$，则称 $f$ 为**正定二次型**，称 $\mathbf{A}$ 为**正定矩阵**。

### 6.2 正定的判定条件

<span style="background-color: #8db3e2">**定理（顺序主子式）**</span> $n$ 阶对称矩阵 $\mathbf{A}$ 正定的充要条件是 $\mathbf{A}$ 的所有顺序主子式都大于零：

$$\Delta_1 = a_{11} > 0, \quad \Delta_2 = \begin{vmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{vmatrix} > 0, \quad \cdots, \quad \Delta_n = |\mathbf{A}| > 0$$

<span style="background-color: #8db3e2">**定理（特征值）**</span> $\mathbf{A}$ 正定的充要条件是 $\mathbf{A}$ 的所有特征值都大于零。

<span style="background-color: #8db3e2">**定理（主子式）**</span> $\mathbf{A}$ 正定的充要条件是 $\mathbf{A}$ 的所有主子式都大于零（顺序主子式只是主子式的一种特殊情况）。

<span style="background-color: #8db3e2">**定理（定义）**</span> $\mathbf{A}$ 正定的充要条件是存在可逆矩阵 $\mathbf{C}$ 使得 $\mathbf{A} = \mathbf{C}^T \mathbf{C}$。

---

## 七、二次型及其矩阵的正定性

### 7.1 负定与半正定

<span style="background-color: #ccc1d9">**定义（负定）**</span> 若对任意 $\mathbf{x} \neq \mathbf{0}$，有 $f(\mathbf{x}) < 0$，则称 $f$ 为**负定二次型**。

<span style="background-color: #ccc1d9">**定义（半正定）**</span> 若对任意 $\mathbf{x} \neq \mathbf{0}$，有 $f(\mathbf{x}) \geq 0$，则称 $f$ 为**半正定二次型**。

### 7.2 负定的判定

<span style="background-color: #8db3e2">**定理**</span> $n$ 阶对称矩阵 $\mathbf{A}$ 负定的充要条件是：
- $(-1)^k \Delta_k > 0$（奇数阶顺序主子式小于零，偶数阶顺序主子式大于零）
- 或者 $\mathbf{A}$ 的所有特征值都小于零

### 7.3 正定矩阵的性质

<span style="background-color: #8db3e2">**性质**</span>
- 若 $\mathbf{A}$ 正定，则 $\mathbf{A}^{-1}$ 也正定
- 若 $\mathbf{A}, \mathbf{B}$ 正定，则 $\mathbf{A} + \mathbf{B}$ 也正定
- 若 $\mathbf{A}$ 正定，则 $|\mathbf{A}| > 0$
- 若 $\mathbf{A}$ 正定，则 $a_{ii} > 0$（对角元素为正）

---

## 八、典型例题

### 例题1：二次型矩阵与标准形

**题目**（660题-404变式）二次型 $f(x_1,x_2,x_3) = 2x_2^2 + 2x_3^2 + 4x_1x_2 - 4x_1x_3 + 8x_2x_3$ 的规范形为（）。

(A) $y_1^2 + y_2^2 + y_3^2$
(B) $y_1^2 + y_2^2 - y_3^2$
(C) $y_1^2 - y_2^2 - y_3^2$
(D) $y_1^2 - y_2^2$

**思路**：求二次型矩阵的特征值，确定正负惯性指数。

**解答**：
二次型矩阵 $\mathbf{A} = \begin{bmatrix} 0 & 2 & -2 \\ 2 & 2 & 4 \\ -2 & 4 & 2 \end{bmatrix}$

$|\lambda\mathbf{E} - \mathbf{A}| = \begin{vmatrix} \lambda & -2 & 2 \\ -2 & \lambda-2 & -4 \\ 2 & -4 & \lambda-2 \end{vmatrix} = (\lambda-6)(\lambda+4)(\lambda-2)$

特征值 $\lambda_1 = 6, \lambda_2 = 2, \lambda_3 = -4$

正惯性指数 $p = 2$（6和2为正），负惯性指数 $q = 1$（-4为负）

规范形为 $y_1^2 + y_2^2 - y_3^2$

**答案**：选 (B)

**总结**：规范形由正负惯性指数决定，特征值的符号决定惯性指数。

---

### 例题2：正定矩阵的判定

**题目**（660题-406变式）二次型 $f(x_1,x_2,x_3) = x_1^2 + 2x_2^2 + 3x_3^2 + 2x_1x_2 + 2x_1x_3 + 2x_2x_3$，判断其正定性。

**思路**：计算顺序主子式或特征值。

**解答**：
二次型矩阵 $\mathbf{A} = \begin{bmatrix} 1 & 1 & 1 \\ 1 & 2 & 1 \\ 1 & 1 & 3 \end{bmatrix}$

计算顺序主子式：

$\Delta_1 = 1 > 0$

$\Delta_2 = \begin{vmatrix} 1 & 1 \\ 1 & 2 \end{vmatrix} = 1 > 0$

$\Delta_3 = |\mathbf{A}| = \begin{vmatrix} 1 & 1 & 1 \\ 1 & 2 & 1 \\ 1 & 1 & 3 \end{vmatrix} = \begin{vmatrix} 1 & 1 & 1 \\ 0 & 1 & 0 \\ 0 & 0 & 2 \end{vmatrix} = 2 > 0$

所有顺序主子式均大于零，$\mathbf{A}$ 正定，$f$ 是正定二次型。

**总结**：顺序主子式法是判断正定性最直接的方法。

---

### 例题3：参数确定与正定性

**题目**（660题-407变式）二次型 $f(x_1,x_2,x_3) = x_1^2 + 2tx_1x_2 - 2x_1x_3 + x_2^2 + 4x_2x_3 + 5x_3^2$ 正定，则 $t$ 的取值范围是____。

**思路**：计算顺序主子式，要求都大于零。

**解答**：
二次型矩阵 $\mathbf{A} = \begin{bmatrix} 1 & t & -1 \\ t & 1 & 2 \\ -1 & 2 & 5 \end{bmatrix}$

$\Delta_1 = 1 > 0$

$\Delta_2 = \begin{vmatrix} 1 & t \\ t & 1 \end{vmatrix} = 1 - t^2 > 0 \Rightarrow -1 < t < 1$

$\Delta_3 = |\mathbf{A}| = \begin{vmatrix} 1 & t & -1 \\ t & 1 & 2 \\ -1 & 2 & 5 \end{vmatrix} = 1(5-4) - t(5t+2) -1(2t-1) = 1 - 5t^2 - 2t - 2t + 1 = 2 - 5t^2 - 4t$

$= -5t^2 - 4t + 2 > 0 \Rightarrow 5t^2 + 4t - 2 < 0$

解 $5t^2 + 4t - 2 = 0$ 得 $t = \frac{-4 \pm \sqrt{16 + 40}}{10} = \frac{-4 \pm \sqrt{56}}{10} = \frac{-4 \pm 2\sqrt{14}}{10} = \frac{-2 \pm \sqrt{14}}{5}$

所以 $-\frac{2 + \sqrt{14}}{5} < t < -\frac{2 - \sqrt{14}}{5}$

结合 $-1 < t < 1$，取交集得 $-\frac{4}{5} < t < 0$

**总结**：正定要求所有顺序主子式大于零，需要解不等式组。

---

### 例题4：合同矩阵与惯性指数

**题目**（660题-405变式）设 $\mathbf{A} = \begin{bmatrix} 1 & 2 \\ 2 & 1 \end{bmatrix}$，判断与 $\mathbf{A}$ 合同的矩阵是否唯一。

**思路**：求 $\mathbf{A}$ 的特征值，确定合同标准形。

**解答**：
$|\lambda\mathbf{E} - \mathbf{A}| = \begin{vmatrix} \lambda-1 & -2 \\ -2 & \lambda-1 \end{vmatrix} = (\lambda-1)^2 - 4 = (\lambda-3)(\lambda+1)$

特征值 $\lambda_1 = 3, \lambda_2 = -1$

正惯性指数 $p = 1$，负惯性指数 $q = 1$

$\mathbf{A}$ 合同于 $\begin{bmatrix} 1 & 0 \\ 0 & -1 \end{bmatrix}$

但与 $\mathbf{A}$ 合同的矩阵不唯一，因为若有 $\mathbf{C}^T\mathbf{A}\mathbf{C} = \mathbf{B}$，则对任意可逆矩阵 $\mathbf{P}$，有 $(\mathbf{C}\mathbf{P})^T\mathbf{A}(\mathbf{C}\mathbf{P}) = \mathbf{P}^T\mathbf{B}\mathbf{P}$，所以有无穷多个合同矩阵。

**总结**：合同矩阵有无穷多个，但合同标准形（惯性指数）是唯一的。

---

## 九、解题方法总结

### 9.1 二次型标准化方法

| 方法 | 步骤 | 适用情况 |
|------|------|----------|
| 配方法 | 配方、换元 | 一般情况 |
| 正交变换法 | 求特征值和特征向量 | 需要正交矩阵时 |
| 初等变换法 | 对 $[\mathbf{A}, \mathbf{E}]$ 做合同变换 | 计算量较小 |

### 9.2 正定性判定方法

| 方法 | 条件 |
|------|------|
| 顺序主子式 | 所有顺序主子式 $> 0$ |
| 特征值 | 所有特征值 $> 0$ |
| 定义 | 对任意 $\mathbf{x} \neq \mathbf{0}$，$f(\mathbf{x}) > 0$ |
| 合同标准形 | 正惯性指数 $= n$ |

### 9.3 常见易错点

1. **混淆合同与相似**：合同要求 $\mathbf{C}^T\mathbf{A}\mathbf{C}$，相似要求 $\mathbf{C}^{-1}\mathbf{A}\mathbf{C}$
2. **顺序主子式计算**：$3 \times 3$ 矩阵要算到三阶
3. **正交变换 vs 可逆变换**：只有正交变换才保持向量长度
4. **惯性指数唯一**：合同变换保持惯性指数

---

## 十、练习题精选

### 基础练习

1. 将二次型 $f(x_1,x_2) = x_1^2 + 4x_1x_2 + x_2^2$ 化为标准形。

2. 判断下列矩阵是否正定：
   - $\mathbf{A} = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}$
   - $\mathbf{B} = \begin{bmatrix} 1 & 2 \\ 2 & 1 \end{bmatrix}$

3. 求二次型 $f(x_1,x_2,x_3) = x_1^2 + x_2^2 + x_3^2 + 4x_1x_2 + 4x_2x_3$ 的正惯性指数。

### 提高练习

4. 证明：若 $\mathbf{A}$ 正定，则存在可逆矩阵 $\mathbf{C}$ 使得 $\mathbf{A} = \mathbf{C}^T\mathbf{C}$。

5. 设 $\mathbf{A}, \mathbf{B}$ 均为 $n$ 阶正定矩阵，证明 $\mathbf{A}\mathbf{B}$ 正定的充要条件是 $\mathbf{A}$ 与 $\mathbf{B}$ 可交换。

---

## 参考答案提示

1. $f = (x_1 + 2x_2)^2 - 3x_2^2$，标准形 $y_1^2 - 3y_2^2$

2. $\mathbf{A}$ 正定（特征值 $1, 3$）；$\mathbf{B}$ 不正定（特征值 $3, -1$，有负特征值）

3. 矩阵 $\mathbf{A} = \begin{bmatrix} 1 & 2 & 0 \\ 2 & 1 & 2 \\ 0 & 2 & 1 \end{bmatrix}$，求特征值或算顺序主子式：
   $\Delta_1 = 1 > 0$，$\Delta_2 = -3 < 0$，不正定

4. 提示：由正交变换 $\mathbf{A} = \mathbf{Q}\text{diag}(\lambda_1,\cdots,\lambda_n)\mathbf{Q}^T$，$\lambda_i > 0$，取 $\mathbf{C} = \text{diag}(\sqrt{\lambda_1},\cdots,\sqrt{\lambda_n})\mathbf{Q}^T$

5. 提示：$\mathbf{A}\mathbf{B}$ 正定 $\Leftrightarrow$ 对任意 $\mathbf{x} \neq \mathbf{0}$，$\mathbf{x}^T\mathbf{A}\mathbf{B}\mathbf{x} > 0$ $\Leftrightarrow$ $\mathbf{B}^{1/2}\mathbf{A}\mathbf{B}^{1/2}$ 正定 $\Leftrightarrow$ $\mathbf{A}\mathbf{B} = \mathbf{B}\mathbf{A}$

---

> **注**：本 Lecture 内容涵盖二次型的核心知识点。建议结合《基础过关660题》第404-410题进行练习巩固。
