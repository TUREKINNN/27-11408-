---
title: "Lecture 51：函数展开成幂级数"
chapter: "09-无穷级数"
tags: [考研, 数学一, 高等数学, 考研数学一, 无穷级数, 泰勒级数, 麦克劳林展开, 函数展开]
difficulty: ★★★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 51：函数展开成幂级数

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，7个公式是计算基础） |
| **分值分布** | 约 8-12 分 |
| **题型** | 函数展开、幂级数求和、间接展开法应用 |
| **难度** | 较难 |

---

## 一、泰勒级数

### 1.1 泰勒公式回顾

> 若 $f(x)$ 在 $x_0$ 的某邻域内有 $n+1$ 阶导数，则：
>
> $$f(x) = \sum_{k=0}^{n} \frac{f^{(k)}(x_0)}{k!}(x-x_0)^k + R_n(x)$$
>
> 其中 $R_n(x)$ 为余项（拉格朗日余项 $R_n(x) = \dfrac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{n+1}$）。

### 1.2 泰勒级数的定义

> 若 $f(x)$ 在 $x_0$ 的某邻域内**任意阶可导**，则称
>
> $$\boxed{\sum_{n=0}^{\infty} \frac{f^{(n)}(x_0)}{n!}(x-x_0)^n = f(x_0) + f'(x_0)(x-x_0) + \frac{f''(x_0)}{2!}(x-x_0)^2 + \cdots}$$
>
> 为 $f(x)$ 在 $x = x_0$ 处的**泰勒级数**。

> $f(x)$ 在 $x_0$ 处任意阶可导只能保证泰勒级数**存在**，但级数是否收敛到 $f(x)$ 还需要验证余项 $R_n(x) \to 0$。
>
> $$f(x) = \sum_{n=0}^{\infty}\frac{f^{(n)}(x_0)}{n!}(x-x_0)^n \quad \Leftrightarrow \quad R_n(x) \to 0$$

### 1.3 麦克劳林级数

> 当 $x_0 = 0$ 时，泰勒级数称为**麦克劳林级数**：
>
> $$\boxed{f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(0)}{n!} x^n = f(0) + f'(0)x + \frac{f''(0)}{2!}x^2 + \frac{f'''(0)}{3!}x^3 + \cdots}$$

---

## 二、七个常用的麦克劳林展开式


**① 指数函数**

$$\boxed{e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!} = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots \quad (-\infty < x < +\infty)}$$

**② 正弦函数**

$$\boxed{\sin x = \sum_{n=0}^{\infty} \frac{(-1)^n}{(2n+1)!} x^{2n+1} = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \cdots \quad (-\infty < x < +\infty)}$$

**③ 余弦函数**

$$\boxed{\cos x = \sum_{n=0}^{\infty} \frac{(-1)^n}{(2n)!} x^{2n} = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \cdots \quad (-\infty < x < +\infty)}$$

**④ 几何级数（等比级数）**

$$\boxed{\frac{1}{1-x} = \sum_{n=0}^{\infty} x^n = 1 + x + x^2 + \cdots \quad (-1 < x < 1)}$$

**⑤ 对数函数**

$$\boxed{\ln(1+x) = \sum_{n=1}^{\infty} \frac{(-1)^{n-1}}{n} x^n = x - \frac{x^2}{2} + \frac{x^3}{3} - \cdots \quad (-1 < x \le 1)}$$

**⑥ 二项式展开**

$$\boxed{(1+x)^{\alpha} = 1 + \alpha x + \frac{\alpha(\alpha-1)}{2!}x^2 + \frac{\alpha(\alpha-1)(\alpha-2)}{3!}x^3 + \cdots \quad (-1 < x < 1)}$$

特别地，当 $\alpha = -1$ 时：$\dfrac{1}{1+x} = 1 - x + x^2 - x^3 + \cdots$

**⑦ 反正切函数**

$$\boxed{\arctan x = \sum_{n=0}^{\infty} \frac{(-1)^n}{2n+1} x^{2n+1} = x - \frac{x^3}{3} + \frac{x^5}{5} - \cdots \quad (-1 \le x \le 1)}$$

> - $e^x$：系数全 $\frac{1}{n!}$，符号全正
> - $\sin x$：只取奇次幂，系数 $\frac{1}{(2n+1)!}$，正负交替
> - $\cos x$：只取偶次幂，系数 $\frac{1}{(2n)!}$，正负交替
> - $\ln(1+x)$：系数 $\frac{1}{n}$，正负交替，从 $x$ 开始
> - $(1+x)^\alpha$：系数用组合数推广，$\binom{\alpha}{n}$

---

## 三、直接展开法

> 直接计算 $f^{(n)}(x_0)$，代入泰勒级数公式，并验证 $R_n(x) \to 0$。
>
> **步骤**：
> 1. 求 $f(x)$ 的各阶导数 $f^{(n)}(x_0)$
> 2. 写出泰勒级数 $\displaystyle\sum\frac{f^{(n)}(x_0)}{n!}(x-x_0)^n$
> 3. 验证 $R_n(x) \to 0$（对求出的范围内的 $x$）

**【例1】** 将 $f(x) = e^x$ 在 $x_0 = 0$ 处展开成麦克劳林级数。

**解**：

$f^{(n)}(x) = e^x$，$f^{(n)}(0) = 1$（对所有 $n$）

$$e^x = \sum_{n=0}^{\infty}\frac{x^n}{n!}$$

验证余项：$|R_n(x)| = \left|\dfrac{e^{\xi}}{(n+1)!}x^{n+1}\right| \le \dfrac{e^{|x|}}{(n+1)!}|x|^{n+1} \to 0$（$n\to\infty$）

故对所有 $x \in (-\infty, +\infty)$ 成立。$\square$

**【例2】** 将 $f(x) = \sin x$ 在 $x_0 = 0$ 处展开。

**解**：

$f^{(n)}(0)$ 的规律：$f(0)=0, f'(0)=1, f''(0)=0, f'''(0)=-1, f^{(4)}(0)=0, \ldots$

周期为 $4$，即 $f^{(n)}(0) = \sin\dfrac{n\pi}{2}$：

| $n$ | 0 | 1 | 2 | 3 | 4 | 5 | $\cdots$ |
|-----|---|---|---|---|---|---|----------|
| $f^{(n)}(0)$ | 0 | 1 | 0 | -1 | 0 | 1 | $\cdots$ |

$$\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \cdots = \sum_{n=0}^{\infty}\frac{(-1)^n}{(2n+1)!}x^{2n+1} \quad \square$$

> 直接展开法需要计算高阶导数并验证余项，过程繁琐。**考试中主要用间接展开法**。

---

## 四、间接展开法

> 利用已知的展开公式，通过**变量替换、逐项求导、逐项积分、四则运算**等方法，将目标函数转化为已知展开式的形式。
>
> **核心思路**：将函数"凑"成七个公式中某一个的形式。

### 4.1 变量替换法

**【例3】** 将 $e^{-x^2}$ 展开成 $x$ 的幂级数。

**解**：在 $e^x = \displaystyle\sum\frac{x^n}{n!}$ 中用 $-x^2$ 替换 $x$：

$$e^{-x^2} = \sum_{n=0}^{\infty}\frac{(-x^2)^n}{n!} = \sum_{n=0}^{\infty}\frac{(-1)^n}{n!}x^{2n} \quad (-\infty < x < +\infty) \quad \square$$

**【例4】** 将 $\dfrac{1}{1+x^2}$ 展开成 $x$ 的幂级数。

**解**：在 $\dfrac{1}{1-x} = \displaystyle\sum x^n$ 中用 $-x^2$ 替换 $x$：

$$\frac{1}{1+x^2} = \sum_{n=0}^{\infty}(-1)^n x^{2n} \quad (-1 < x < 1) \quad \square$$

### 4.2 逐项积分法

**【例5】** 将 $\ln(1+x)$ 展开成 $x$ 的幂级数。

**解**：

$$\frac{1}{1+x} = \sum_{n=0}^{\infty}(-1)^n x^n \quad (-1 < x < 1)$$

逐项积分：

$$\ln(1+x) = \int_0^x \frac{1}{1+t}\,dt = \sum_{n=0}^{\infty}(-1)^n \frac{x^{n+1}}{n+1} = \sum_{n=1}^{\infty}\frac{(-1)^{n-1}}{n}x^n \quad (-1 < x \le 1) \quad \square$$

**【例6】** 将 $\arctan x$ 展开成 $x$ 的幂级数。

**解**：

$$\frac{1}{1+x^2} = \sum_{n=0}^{\infty}(-1)^n x^{2n} \quad (-1 < x < 1)$$

逐项积分：

$$\arctan x = \int_0^x \frac{1}{1+t^2}\,dt = \sum_{n=0}^{\infty}(-1)^n\frac{x^{2n+1}}{2n+1} \quad (-1 \le x \le 1) \quad \square$$

### 4.3 逐项求导法

**【例7】** 将 $\dfrac{1}{(1-x)^2}$ 展开成 $x$ 的幂级数。

**解**：

$$\frac{1}{1-x} = \sum_{n=0}^{\infty}x^n$$

逐项求导：

$$\frac{1}{(1-x)^2} = \frac{d}{dx}\left(\frac{1}{1-x}\right) = \sum_{n=1}^{\infty}nx^{n-1} = \sum_{n=0}^{\infty}(n+1)x^n \quad (-1 < x < 1) \quad \square$$

### 4.4 代数运算法

**【例8】** 将 $\dfrac{x}{1+x-2x^2}$ 展开成 $x$ 的幂级数。

**解**：先分解：

$$\frac{x}{1+x-2x^2} = \frac{x}{(1-x)(1+2x)} = \frac{1}{3}\cdot\frac{1}{1-x} - \frac{1}{3}\cdot\frac{1}{1+2x}$$

$$= \frac{1}{3}\sum_{n=0}^{\infty}x^n - \frac{1}{3}\sum_{n=0}^{\infty}(-2x)^n = \frac{1}{3}\sum_{n=0}^{\infty}[1-(-2)^n]x^n$$

收敛域取两者的交集：$|x| < \dfrac{1}{2}$。$\square$

### 4.5 混合技巧

**【例9】** 将 $f(x) = x\ln(1+x)$ 展开到 $x^4$。

**解**：

$$\ln(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + \cdots$$

$$x\ln(1+x) = x^2 - \frac{x^3}{2} + \frac{x^4}{3} - \cdots \quad \square$$

**【例10】** 将 $f(x) = \sin^2 x$ 展开成 $x$ 的幂级数。

**解**：$\sin^2 x = \dfrac{1 - \cos 2x}{2}$

$$\cos 2x = \sum_{n=0}^{\infty}\frac{(-1)^n}{(2n)!}(2x)^{2n} = 1 - \frac{(2x)^2}{2!} + \frac{(2x)^4}{4!} - \cdots$$

$$\sin^2 x = \frac{1}{2} - \frac{1}{2}\sum_{n=0}^{\infty}\frac{(-1)^n \cdot 2^{2n}}{(2n)!}x^{2n} = \sum_{n=1}^{\infty}\frac{(-1)^{n-1}\cdot 2^{2n-1}}{(2n)!}x^{2n}$$

$$= \frac{x^2}{1!} - \frac{x^4}{3} + \cdots \quad (-\infty < x < +\infty) \quad \square$$

---

## 五、展开法的选择指南

>
> | 情形 | 方法 |
> |------|------|
> | 题目要求"用定义展开" | 直接展开法（求高阶导数） |
> | 题目只要求"展开到 $x^n$" | 间接展开法（更快更准） |
> | 函数含 $e^x$、$\sin x$、$\cos x$ | 变量替换 |
> | 函数含 $\ln$、$\arctan$ | 逐项积分 |
> | 函数含 $(1-x)^{-k}$ | 逐项求导 |
> | 函数为有理函数 | 部分分式分解 |

---

## 六、考研真题精选

### 【真题1】（2018年数一·解答·10分）

**题目**：将 $f(x) = \dfrac{1}{x^2 - 3x + 2}$ 展开成 $x$ 的幂级数。

**解**：

$$\frac{1}{x^2-3x+2} = \frac{1}{(1-x)(2-x)} = \frac{1}{1-x} - \frac{1}{2-x}$$

$$= \sum_{n=0}^{\infty}x^n - \frac{1}{2}\sum_{n=0}^{\infty}\frac{x^n}{2^n} = \sum_{n=0}^{\infty}\left(1 - \frac{1}{2^{n+1}}\right)x^n$$

收敛域 $|x| < 1$。$\square$

### 【真题2】（解答题·10分）

**题目**：将 $f(x) = \ln(2 + x - x^2)$ 展开成 $x$ 的幂级数。

**解**：

$$\ln(2+x-x^2) = \ln(1+x)(2-x) = \ln(1+x) + \ln(2-x)$$

$$\ln(1+x) = \sum_{n=1}^{\infty}\frac{(-1)^{n-1}}{n}x^n \quad (-1 < x \le 1)$$

$$\ln(2-x) = \ln 2 + \ln\left(1-\frac{x}{2}\right) = \ln 2 - \sum_{n=1}^{\infty}\frac{x^n}{n\cdot 2^n} \quad (-2 \le x < 2)$$

$$f(x) = \ln 2 + \sum_{n=1}^{\infty}\left[\frac{(-1)^{n-1}}{n} - \frac{1}{n\cdot 2^n}\right]x^n$$

收敛域 $(-1, 1]$（两个级数收敛域的交集）。$\square$

### 【真题3】（2021年数一·解答·12分）

**题目**：设 $f(x) = \dfrac{\arctan x - x}{x^3}$，将 $f(x)$ 展开成 $x$ 的幂级数（写到 $x^4$ 项）。

**解**：

$$\arctan x = x - \frac{x^3}{3} + \frac{x^5}{5} - \cdots$$

$$\arctan x - x = -\frac{x^3}{3} + \frac{x^5}{5} - \cdots$$

$$f(x) = \frac{\arctan x - x}{x^3} = -\frac{1}{3} + \frac{x^2}{5} - \frac{x^4}{7} + \cdots \quad \square$$

---

## 📝 本节要点总结

| 内容 | 核心要点 |
|------|----------|
| 泰勒级数 | $\sum\frac{f^{(n)}(x_0)}{n!}(x-x_0)^n$ |
| 麦克劳林级数 | $x_0 = 0$ 的特殊情况 |
| 七个公式 | $e^x, \sin x, \cos x, \frac{1}{1-x}, \ln(1+x), (1+x)^\alpha, \arctan x$ |
| 直接展开法 | 求高阶导 + 验证余项 |
| 间接展开法 | 替换、求导、积分、四则运算 |

> 1. **七个展开公式必须背熟**，这是整个幂级数章节的基础
> 2. 考试中优先用间接展开法，效率远高于直接展开法
> 3. 展开时注意**收敛域**，两个级数运算后的收敛域取交集
> 4. $\ln(1+x)$ 和 $\arctan x$ 的展开式在端点 $x = \pm 1$ 处要单独讨论
> 5. 注意展开式中 $x$ 的范围与最终结果的范围可能不同（如 $e^{-x^2}$ 仍是全实数）
> 6. 局部展开（只写到某阶）可以只算必要的项，不必求一般表达式

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 50：幂级数]] — 幂级数
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/09-无穷级数/Lecture 52：傅里叶级数]] — 傅里叶
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/03-微分中值定理与导数应用/Lecture 23：泰勒公式]] — 泰勒公式
