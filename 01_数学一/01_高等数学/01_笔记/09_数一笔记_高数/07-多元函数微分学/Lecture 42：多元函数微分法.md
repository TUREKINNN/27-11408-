---
title: "Lecture 42：多元函数微分法"
chapter: "07-多元函数微分学"
tags: [考研, 数学一, 高等数学, 考研数学一, 链式法则, 隐函数求导, 全微分]
difficulty: ★★★★
exam_weight: ★★★★★
created: 2026-06-16
---

# Lecture 42：多元函数微分法

## 📊 考情分析

| 项目 | 内容 |
|------|------|
| **考查频率** | ★★★★★（每年必考，解答题高频考点） |
| **分值分布** | 约 10-12 分 |
| **题型** | 复合函数求偏导、隐函数求导、全微分 |
| **难度** | 中等偏难 |

---

## 一、多元复合函数的链式法则

### 1.1 复合函数的链式法则（一）

> 设 $z = f(u, v)$ 可微，$u = \varphi(t)$，$v = \psi(t)$ 均可导，则 $z = f[\varphi(t), \psi(t)]$ 可导，且：
>
> $$\boxed{\frac{dz}{dt} = \frac{\partial f}{\partial u}\frac{du}{dt} + \frac{\partial f}{\partial v}\frac{dv}{dt}}$$
>
> 此时 $\dfrac{dz}{dt}$ 称为**全导数**。

**链路图**：

```
       z
      ╱ ╲
     u   v
     |   |
      t
```

每条从 $z$ 到 $t$ 的路径贡献一项偏导 × 导数。

### 1.2 复合函数的链式法则（二）

> 设 $z = f(u, v)$ 可微，$u = \varphi(x, y)$，$v = \psi(x, y)$ 均有偏导数，则：
>
> $$\boxed{\frac{\partial z}{\partial x} = \frac{\partial f}{\partial u}\frac{\partial u}{\partial x} + \frac{\partial f}{\partial v}\frac{\partial v}{\partial x}}$$
>
> $$\boxed{\frac{\partial z}{\partial y} = \frac{\partial f}{\partial u}\frac{\partial u}{\partial y} + \frac{\partial f}{\partial v}\frac{\partial v}{\partial y}}$$

**链路图**：

```
           z
          ╱ ╲
         u   v
        ╱╲   ╱╲
       x  y  x  y
```

### 1.3 复合函数的链式法则（三）

> 设 $z = f(x, y, t)$，其中 $x = \varphi(s, t)$，$y = \psi(s, t)$，则：
>
> $$\frac{\partial z}{\partial t} = \frac{\partial f}{\partial x}\frac{\partial x}{\partial t} + \frac{\partial f}{\partial y}\frac{\partial y}{\partial t} + \frac{\partial f}{\partial t}$$
>
> 注意最后一项 $\dfrac{\partial f}{\partial t}$ 是 $f$ 对第**三**个位置变量的偏导，而 $\dfrac{\partial z}{\partial t}$ 是 $z$ 作为 $s, t$ 函数对 $t$ 的偏导。

> $\dfrac{\partial z}{\partial t}$ 和 $\dfrac{\partial f}{\partial t}$ 含义不同！前者是最终对 $t$ 的偏导，后者是 $f$ 对第三位置变量的偏导，不可混淆。

### 1.4 经典例题

**【例1】** 设 $z = e^{u}\sin v$，$u = xy$，$v = x + y$，求 $\dfrac{\partial z}{\partial x}$，$\dfrac{\partial z}{\partial y}$。

**解**：

$$\frac{\partial f}{\partial u} = e^u \sin v, \quad \frac{\partial f}{\partial v} = e^u \cos v$$

$$\frac{\partial u}{\partial x} = y, \quad \frac{\partial u}{\partial y} = x, \quad \frac{\partial v}{\partial x} = 1, \quad \frac{\partial v}{\partial y} = 1$$

$$\frac{\partial z}{\partial x} = e^{xy}\sin(x+y) \cdot y + e^{xy}\cos(x+y) \cdot 1 = e^{xy}[y\sin(x+y) + \cos(x+y)]$$

$$\frac{\partial z}{\partial y} = e^{xy}\sin(x+y) \cdot x + e^{xy}\cos(x+y) \cdot 1 = e^{xy}[x\sin(x+y) + \cos(x+y)] \quad \square$$

**【例2】** 设 $z = f(x^2 - y^2, e^{xy})$，其中 $f$ 有连续偏导数，求 $\dfrac{\partial z}{\partial x}$，$\dfrac{\partial z}{\partial y}$。

**解**：令 $u = x^2 - y^2$，$v = e^{xy}$，则：

$$\frac{\partial z}{\partial x} = f_1' \cdot 2x + f_2' \cdot ye^{xy} = 2xf_1' + ye^{xy}f_2'$$

$$\frac{\partial z}{\partial y} = f_1' \cdot (-2y) + f_2' \cdot xe^{xy} = -2yf_1' + xe^{xy}f_2' \quad \square$$

> 用 $f_1'$ 表示 $f$ 对**第一个中间变量**的偏导，$f_2'$ 表示对**第二个**的偏导，简洁高效。

**【例3】** 设 $z = f(x, xy)$，$f$ 有二阶连续偏导数，求 $\dfrac{\partial^2 z}{\partial x \partial y}$。

**解**：令 $u = x$，$v = xy$：

$$\frac{\partial z}{\partial x} = f_1' + yf_2'$$

$$\frac{\partial^2 z}{\partial x \partial y} = \frac{\partial}{\partial y}(f_1' + yf_2')$$

$$= \frac{\partial f_1'}{\partial y} + f_2' + y\frac{\partial f_2'}{\partial y}$$

$$= (f_{11}'' \cdot 0 + f_{12}'' \cdot x) + f_2' + y(f_{21}'' \cdot 0 + f_{22}'' \cdot x)$$

$$= xf_{12}'' + f_2' + xyf_{22}'' \quad \square$$

---

## 二、隐函数求导

### 2.1 由一个方程确定的隐函数

> 设 $F(x, y)$ 在 $(x_0, y_0)$ 的某邻域内有连续偏导数，$F(x_0, y_0) = 0$，$F_y(x_0, y_0) \ne 0$，则方程 $F(x, y) = 0$ 在 $(x_0, y_0)$ 的某邻域内**唯一确定**一个连续可导函数 $y = f(x)$，且：
>
> $$\boxed{\frac{dy}{dx} = -\frac{F_x}{F_y}}$$

> 对 $F(x, y) = 0$ 两边对 $x$ 求导（$y$ 是 $x$ 的函数）：
>
> $$F_x + F_y \cdot \frac{dy}{dx} = 0 \implies \frac{dy}{dx} = -\frac{F_x}{F_y}$$

### 2.2 由方程组确定的隐函数

> 设 $\begin{cases} F(x, y, u, v) = 0 \\ G(x, y, u, v) = 0 \end{cases}$，在某点处雅可比行列式：
>
> $$J = \frac{\partial(F, G)}{\partial(u, v)} = \begin{vmatrix} F_u & F_v \\ G_u & G_v \end{vmatrix} \ne 0$$
>
> 则可确定 $u = u(x, y)$，$v = v(x, y)$。
>
> 求导方法：对每个方程分别对 $x$（或 $y$）求偏导，得到关于 $\dfrac{\partial u}{\partial x}$、$\dfrac{\partial v}{\partial x}$ 的方程组，解之。

### 2.3 经典例题

**【例4】** 设 $e^y + xy - e = 0$，求 $\dfrac{dy}{dx}$ 和 $\dfrac{d^2y}{dx^2}$。

**解**：令 $F(x,y) = e^y + xy - e$：

$$F_x = y, \quad F_y = e^y + x$$

$$\frac{dy}{dx} = -\frac{F_x}{F_y} = -\frac{y}{e^y + x}$$

注意原方程给出 $e^y = e - xy$，代入：

$$\frac{dy}{dx} = -\frac{y}{e - xy + x} = -\frac{y}{e + x(1-y)}$$

再求二阶导（对 $\dfrac{dy}{dx} = -\dfrac{y}{e^y+x}$ 两边对 $x$ 求导）：

$$\frac{d^2y}{dx^2} = -\frac{y'(e^y+x) - y(e^y y' + 1)}{(e^y+x)^2}$$

代入 $y' = -\dfrac{y}{e^y+x}$ 化简即可。$\square$

**【例5】** 设 $F(x-y, y-z, z-x) = 0$ 确定 $z = z(x, y)$，求 $\dfrac{\partial z}{\partial x}$、$\dfrac{\partial z}{\partial y}$。

**解**：令 $u = x-y$，$v = y-z$，$w = z-x$，对 $F(u, v, w) = 0$ 关于 $x$ 求偏导：

$$F_1' \cdot 1 + F_2' \cdot \left(-\frac{\partial z}{\partial x}\right) + F_3' \cdot \left(\frac{\partial z}{\partial x} - 1\right) = 0$$

$$F_1' - F_2' z_x + F_3' z_x - F_3' = 0$$

$$z_x(F_3' - F_2') = F_3' - F_1'$$

$$\boxed{\frac{\partial z}{\partial x} = \frac{F_3' - F_1'}{F_3' - F_2'}}$$

类似地，关于 $y$ 求偏导：

$$F_1'(-1) + F_2'\left(1 - \frac{\partial z}{\partial y}\right) + F_3' \frac{\partial z}{\partial y} = 0$$

$$\boxed{\frac{\partial z}{\partial y} = \frac{F_1' - F_2'}{F_3' - F_2'}} \quad \square$$

---

## 三、全微分形式不变性

> 不论 $u, v$ 是自变量还是中间变量，全微分的形式**保持不变**：
>
> $$\boxed{dz = \frac{\partial z}{\partial u}du + \frac{\partial z}{\partial dv}dv}$$

### 3.1 应用示例

**【例6】** 利用全微分形式不变性求偏导数：设 $z = f(x^2+y^2, xy)$，求 $\dfrac{\partial z}{\partial x}$。

**解**：

$$dz = f_1' d(x^2+y^2) + f_2' d(xy) = f_1'(2x\,dx + 2y\,dy) + f_2'(y\,dx + x\,dy)$$

$$= (2xf_1' + yf_2')dx + (2yf_1' + xf_2')dy$$

由 $dz = z_x\,dx + z_y\,dy$ 对比系数：

$$\frac{\partial z}{\partial x} = 2xf_1' + yf_2', \quad \frac{\partial z}{\partial y} = 2yf_1' + xf_2' \quad \square$$

### 3.2 全微分的四则运算法则

> - $d(u \pm v) = du \pm dv$
> - $d(uv) = v\,du + u\,dv$
> - $d\left(\dfrac{u}{v}\right) = \dfrac{v\,du - u\,dv}{v^2}$

---

## 四、多元函数微分法的综合应用

### 4.1 变量替换化简方程

**【例7】** 利用变换 $u = x + ay$，$v = x + by$ 将方程 $\dfrac{\partial^2 z}{\partial x^2} + 4\dfrac{\partial^2 z}{\partial x \partial y} + 3\dfrac{\partial^2 z}{\partial y^2} = 0$ 化简为 $\dfrac{\partial^2 z}{\partial u \partial v} = 0$，求 $a, b$。

**解**：由链式法则：

$$\frac{\partial z}{\partial x} = \frac{\partial z}{\partial u} + \frac{\partial z}{\partial v}$$

$$\frac{\partial z}{\partial y} = a\frac{\partial z}{\partial u} + b\frac{\partial z}{\partial v}$$

$$\frac{\partial^2 z}{\partial x^2} = z_{uu} + 2z_{uv} + z_{vv}$$

$$\frac{\partial^2 z}{\partial x \partial y} = az_{uu} + (a+b)z_{uv} + bz_{vv}$$

$$\frac{\partial^2 z}{\partial y^2} = a^2 z_{uu} + 2abz_{uv} + b^2 z_{vv}$$

代入原方程：

$$(1+4a+3a^2)z_{uu} + (2+4(a+b)+6ab)z_{uv} + (1+4b+3b^2)z_{vv} = 0$$

要化为 $z_{uv} = 0$，需：

$$\begin{cases} 1+4a+3a^2 = 0 \\ 1+4b+3b^2 = 0 \end{cases}$$

$(3a+1)(a+1) = 0$，$a = -1$ 或 $a = -\dfrac{1}{3}$。

取 $a = -1, b = -\dfrac{1}{3}$（或 $a = -\dfrac{1}{3}, b = -1$）。$\square$

---

## 五、考研真题精选

### 【真题1】（2020年数一·解答·10分）

**题目**：设 $z = f(e^x \cos y)$，其中 $f$ 有二阶连续导数，证明 $\dfrac{\partial^2 z}{\partial x^2} + \dfrac{\partial^2 z}{\partial y^2} = e^{2x}f''(e^x\cos y)$。

**证明**：

令 $u = e^x \cos y$，则 $z = f(u)$。

$$\frac{\partial z}{\partial x} = f'(u) \cdot e^x\cos y = f'(u) \cdot u$$

$$\frac{\partial z}{\partial y} = f'(u) \cdot (-e^x\sin y)$$

$$\frac{\partial^2 z}{\partial x^2} = f''(u)(e^x\cos y)^2 + f'(u)e^x\cos y = u^2 f''(u) + uf'(u)$$

$$\frac{\partial^2 z}{\partial y^2} = f''(u)(-e^x\sin y)^2 + f'(u)(-e^x\cos y) = e^{2x}\sin^2 y \cdot f''(u) - uf'(u)$$

相加：

$$z_{xx} + z_{yy} = (u^2 + e^{2x}\sin^2 y)f''(u) = e^{2x}(\cos^2 y + \sin^2 y)f''(u) = e^{2x}f''(u) \quad \blacksquare$$

---

## 📝 本节要点总结

| 内容 | 核心公式 |
|------|----------|
| 链式法则 | 每条路径贡献"外层偏导 × 内层导数"之和 |
| 隐函数求导 | $\dfrac{dy}{dx} = -\dfrac{F_x}{F_y}$ |
| 方程组隐函数 | 对各方程求导后解方程组 |
| 全微分形式不变性 | $dz = z_u\,du + z_v\,dv$ 无论 $u, v$ 是否为自变量 |

> 复合函数求偏导是解答题常考内容。画清**链路图**是正确使用链式法则的关键。隐函数求导要注意符号和各项的完整性。

---

## 关联知识点

- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/07-多元函数微分学/Lecture 41：多元复合函数基础]] — 基础
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/07-多元函数微分学/Lecture 43：多元函数的极值与最值]] — 极值
- [[01_数学一/01_高等数学/01_笔记/09_数一笔记_高数/02-导数与微分/Lecture 17：导数求导法则]] — 一元求导
