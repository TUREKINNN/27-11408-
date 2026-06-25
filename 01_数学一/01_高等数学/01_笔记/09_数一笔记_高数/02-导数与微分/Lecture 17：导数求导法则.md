---
title: "Lecture 17：导数求导法则"
chapter: "02-导数与微分"
tags: [考研, 数学一, 高等数学, 考研数学一, 求导法则, 链式法则]
difficulty: ★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 17：导数求导法则

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，计算能力的核心） |
| **分值分布** | 约 4-10 分（选择 1 题 + 解答中的求导步骤） |
| **题型** | 复合函数求导、四则运算求导、反函数求导 |
| **难度** | 基础～中等 |

---

## 一、四则运算求导法则

### 1.1 加减法则

> 设 $u(x)$、$v(x)$ 均可导，则
>
> $$(u \pm v)' = u' \pm v'$$
>
> 推广到有限项：$(u_1 + u_2 + \cdots + u_n)' = u_1' + u_2' + \cdots + u_n'$

### 1.2 乘法法则

> $$(uv)' = u'v + uv'$$

**推广到三个函数**：

$$\boxed{(uvw)' = u'vw + uv'w + uvw'}$$

**记忆口诀**：每个因子轮流求导，其余不变，然后相加。

### 1.3 除法法则

> $$\left(\frac{u}{v}\right)' = \frac{u'v - uv'}{v^2} \quad (v \ne 0)$$

**记忆口诀**："**下乘上导减上乘下导，除以下的平方**"

> $(uv)' \ne u'v'$，$\left(\dfrac{u}{v}\right)' \ne \dfrac{u'}{v'}$
>
> 这是最常见的初学者错误！

---

## 二、复合函数求导——链式法则

### 2.1 链式法则

> 设 $y = f(u)$，$u = g(x)$ 均可导，则复合函数 $y = f[g(x)]$ 对 $x$ 的导数为：
>
> $$\boxed{\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx} = f'(u) \cdot g'(x) = f'[g(x)] \cdot g'(x)}$$

**通俗理解**：对复合函数求导 = **对外层函数求导 × 对内层函数求导**

### 2.2 多层复合

> 设 $y = f(u)$，$u = g(v)$，$v = h(x)$，则：
>
> $$\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dv} \cdot \frac{dv}{dx} = f'(u) \cdot g'(v) \cdot h'(x)$$

**求导步骤**：
1. 分清函数的**层次结构**（由外到内）
2. 逐层求导，然后相乘
3. 最后将中间变量回代为 $x$

### 2.3 典型复合函数求导示例

**例1**：$y = \sin(x^2 + 1)$

设 $u = x^2 + 1$，则 $y = \sin u$

$$y' = \cos u \cdot u' = \cos(x^2 + 1) \cdot 2x = 2x\cos(x^2 + 1)$$

**例2**：$y = e^{\sin(\ln x)}$

设 $u = \sin(\ln x)$，再设 $v = \ln x$

$$y' = e^u \cdot u' = e^{\sin(\ln x)} \cdot \cos(\ln x) \cdot \frac{1}{x} = \frac{e^{\sin(\ln x)}\cos(\ln x)}{x}$$

**例3**：$y = \ln(x + \sqrt{x^2 + 1})$

$$y' = \frac{1}{x + \sqrt{x^2 + 1}} \cdot \left(1 + \frac{x}{\sqrt{x^2 + 1}}\right) = \frac{1}{x + \sqrt{x^2 + 1}} \cdot \frac{\sqrt{x^2+1} + x}{\sqrt{x^2+1}} = \frac{1}{\sqrt{x^2+1}}$$

> **技巧**：此例中出现了"**自相消**"现象，即分子恰好是分母的一部分，简化后结果很简洁。

**例4**：幂指函数 $y = u(x)^{v(x)}$ 的求导

方法：**对数求导法**

$$\ln y = v(x)\ln u(x)$$

两边对 $x$ 求导：

$$\frac{y'}{y} = v'(x)\ln u(x) + v(x) \cdot \frac{u'(x)}{u(x)}$$

$$\boxed{y' = u(x)^{v(x)}\left[v'(x)\ln u(x) + \frac{v(x)u'(x)}{u(x)}\right]}$$

---

## 三、反函数求导

### 3.1 反函数的一阶导数

> 设 $y = f(x)$ 可导且 $f'(x) \ne 0$，则反函数 $x = f^{-1}(y)$ 的导数为：
>
> $$\boxed{\frac{dx}{dy} = \frac{1}{\dfrac{dy}{dx}} = \frac{1}{f'(x)}}$$

**记忆**：反函数的导数 = 原函数导数的**倒数**。

### 3.2 反函数的二阶导数

> $$\frac{d^2x}{dy^2} = \frac{d}{dy}\left(\frac{1}{f'(x)}\right) = \frac{d}{dx}\left(\frac{1}{f'(x)}\right) \cdot \frac{dx}{dy}$$
>
> $$= -\frac{f''(x)}{[f'(x)]^2} \cdot \frac{1}{f'(x)} = \boxed{-\frac{f''(x)}{[f'(x)]^3}}$$

> 反函数二阶导数不是简单的 $\dfrac{1}{f''(x)}$！需要用链式法则，将 $\dfrac{d}{dy}$ 转化为 $\dfrac{d}{dx} \cdot \dfrac{dx}{dy}$。

---

## 四、对数求导法

### 4.1 适用场景

> 1. **幂指函数**：$y = u(x)^{v(x)}$
> 2. **多个因子相乘/相除**：$y = \dfrac{f_1(x) \cdot f_2(x) \cdots f_m(x)}{g_1(x) \cdot g_2(x) \cdots g_n(x)}$
> 3. **含根号的复杂函数**

### 4.2 方法步骤

1. 两边取对数：$\ln|y| = \ln|f(x)|$
2. 两边对 $x$ 求导：$\dfrac{y'}{y} = [\ln|f(x)|]'$
3. 解出：$y' = y \cdot [\ln|f(x)|]'$

### 4.3 示例

**题目**：$y = \sqrt{\dfrac{(x-1)(x-2)}{(x-3)(x-4)}}$，求 $y'$。

**解**：

$$\ln y = \frac{1}{2}[\ln|x-1| + \ln|x-2| - \ln|x-3| - \ln|x-4|]$$

$$\frac{y'}{y} = \frac{1}{2}\left(\frac{1}{x-1} + \frac{1}{x-2} - \frac{1}{x-3} - \frac{1}{x-4}\right)$$

$$\boxed{y' = \frac{1}{2}\sqrt{\frac{(x-1)(x-2)}{(x-3)(x-4)}}\left(\frac{1}{x-1} + \frac{1}{x-2} - \frac{1}{x-3} - \frac{1}{x-4}\right)}$$

---

## 五、经典例题

### 【例1】复合函数求导

**题目**：设 $y = \arctan\sqrt{\dfrac{1-x}{1+x}}$，求 $y'$。

**解**：

设 $u = \sqrt{\dfrac{1-x}{1+x}}$，则 $y = \arctan u$

$$y' = \frac{1}{1+u^2} \cdot u' = \frac{1}{1 + \frac{1-x}{1+x}} \cdot u' = \frac{1+x}{2} \cdot u'$$

求 $u' = \left(\sqrt{\dfrac{1-x}{1+x}}\right)'$：

设 $v = \dfrac{1-x}{1+x}$，则 $u = \sqrt{v}$，$v' = \dfrac{-(1+x) - (1-x)}{(1+x)^2} = \dfrac{-2}{(1+x)^2}$

$$u' = \frac{1}{2\sqrt{v}} \cdot v' = \frac{1}{2\sqrt{\frac{1-x}{1+x}}} \cdot \frac{-2}{(1+x)^2} = \frac{-1}{(1+x)^2} \cdot \sqrt{\frac{1+x}{1-x}}$$

代入：

$$y' = \frac{1+x}{2} \cdot \frac{-1}{(1+x)^2} \cdot \sqrt{\frac{1+x}{1-x}} = \frac{-1}{2(1+x)} \cdot \sqrt{\frac{1+x}{1-x}} = \frac{-1}{2\sqrt{1-x^2}}$$

### 【例2】参数方程形式的复合

**题目**：设 $y = (\sin x)^{\cos x} + (\cos x)^{\sin x}$，求 $y'$。

**解**：

设 $y_1 = (\sin x)^{\cos x}$，$y_2 = (\cos x)^{\sin x}$

对 $y_1$ 取对数：$\ln y_1 = \cos x \cdot \ln(\sin x)$

$$\frac{y_1'}{y_1} = -\sin x \cdot \ln(\sin x) + \cos x \cdot \frac{\cos x}{\sin x}$$

$$y_1' = (\sin x)^{\cos x}\left[-\sin x \ln(\sin x) + \frac{\cos^2 x}{\sin x}\right]$$

对 $y_2$ 取对数：$\ln y_2 = \sin x \cdot \ln(\cos x)$

$$\frac{y_2'}{y_2} = \cos x \cdot \ln(\cos x) + \sin x \cdot \frac{-\sin x}{\cos x}$$

$$y_2' = (\cos x)^{\sin x}\left[\cos x \ln(\cos x) - \frac{\sin^2 x}{\cos x}\right]$$

$$y' = y_1' + y_2'$$

### 【例3】抽象函数的求导

**题目**：设 $f(x)$ 二阶可导，$y = f(e^x) + e^{f(x)}$，求 $y'$ 和 $y''$。

**解**：

$$y' = f'(e^x) \cdot e^x + e^{f(x)} \cdot f'(x)$$

$$y'' = f''(e^x) \cdot (e^x)^2 + f'(e^x) \cdot e^x + e^{f(x)} \cdot [f'(x)]^2 + e^{f(x)} \cdot f''(x)$$

$$= e^{2x}f''(e^x) + e^x f'(e^x) + e^{f(x)}[f'(x)]^2 + e^{f(x)}f''(x)$$

---

## 六、考研真题精选

### 【真题1】（2012年数一·解答）

**题目**：设 $y = y(x)$ 由 $\begin{cases} x = \arctan t \\ 2y - ty^2 + e^t = 5 \end{cases}$ 确定，求 $\dfrac{dy}{dx}$。

**解**：

$\dfrac{dx}{dt} = \dfrac{1}{1+t^2}$

对第二式关于 $t$ 求导：$2\dfrac{dy}{dt} - y^2 - 2ty\dfrac{dy}{dt} + e^t = 0$

$(2 - 2ty)\dfrac{dy}{dt} = y^2 - e^t$

$\dfrac{dy}{dt} = \dfrac{y^2 - e^t}{2 - 2ty}$

$$\frac{dy}{dx} = \frac{\frac{dy}{dt}}{\frac{dx}{dt}} = \frac{y^2 - e^t}{2 - 2ty} \cdot (1 + t^2)$$

### 【真题2】（2015年数一·填空）

**题目**：设 $f(x) = x^2 \cdot 2^x$，则 $f^{(10)}(0) = $ ______。

**解**：

利用莱布尼茨公式，$(uv)^{(n)} = \sum\limits_{k=0}^{n}C_n^k u^{(k)}v^{(n-k)}$

设 $u = x^2$，$v = 2^x$。注意到 $u'' = 2$，$u''' = 0$。

$$f^{(10)}(0) = \sum_{k=0}^{10}C_{10}^k u^{(k)}(0) \cdot v^{(10-k)}(0)$$

$u(0) = 0$，$u'(0) = 0$，$u''(0) = 2$，$u^{(k)}(0) = 0$（$k \ge 3$）

$$f^{(10)}(0) = C_{10}^2 \cdot 2 \cdot v^{(8)}(0) = 45 \cdot 2 \cdot (2^x \cdot (\ln 2)^8)\bigg|_{x=0} = 90(\ln 2)^8$$

**答案**：$f^{(10)}(0) = 90(\ln 2)^8$

---

## 📝 本节要点总结

| 法则 | 公式 | 注意事项 |
|------|------|----------|
| 和差法则 | $(u\pm v)' = u' \pm v'$ | 推广到有限项 |
| 乘法法则 | $(uv)' = u'v + uv'$ | 不能写成 $u'v'$ |
| 除法法则 | $(u/v)' = (u'v-uv')/v^2$ | 分母平方 |
| 链式法则 | $\frac{dy}{dx} = \frac{dy}{du}\cdot\frac{du}{dx}$ | 逐层求导相乘 |
| 反函数 | $\frac{dx}{dy} = \frac{1}{f'(x)}$ | 二阶公式需记忆 |
| 对数求导 | $\ln y = \ln f(x)$ 再求导 | 幂指函数必用 |

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/02-导数与微分/Lecture 16：导数基本概念]] — 导数概念
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/02-导数与微分/Lecture 18：高阶导数]] — 高阶导数
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/02-导数与微分/Lecture 19：隐函数与参数方程]] — 隐函数
