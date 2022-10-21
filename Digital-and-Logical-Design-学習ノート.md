# **Digital Design and Computer Architecture**

---

## ***Contents***

- [**Digital Design and Computer Architecture**](#digital-design-and-computer-architecture)
  - [***Contents***](#contents)
  - [**Chp1. Binary**](#chp1-binary)
    - [1.1 Complexity Control](#11-complexity-control)
    - [1.2 补码运算](#12-补码运算)
    - [1.3 逻辑门](#13-逻辑门)
    - [1.4 物理限制](#14-物理限制)
    - [**习题**](#习题)
  - [**Chp2. 组合逻辑**](#chp2-组合逻辑)
    - [2.1 Black Box Abstraction](#21-black-box-abstraction)
    - [2.2 布尔代数 - 化简逻辑表达式](#22-布尔代数---化简逻辑表达式)
    - [2.3 Programmable Logic Array - PLA](#23-programmable-logic-array---pla)
    - [2.5 卡诺图 - 化简逻辑表达式](#25-卡诺图---化简逻辑表达式)
    - [3.4 Finite State Automaton (FSA)](#34-finite-state-automaton-fsa)

---

## **Chp1. Binary**

---

### 1.1 Complexity Control

- Abstraction : Hide Details
- Discipline : 如行业标准
- 3 Principle
  - Hierarchy
  - Modularity
  - Regularity

---

### 1.2 补码运算

- **补码定义**：最高位（第n位）权值为

$$
b_{n-1} = -2^{n-1}
$$

> 故加到最大值$$2^{n-1}-1$$后，循环加法到最小值$$-2^{n-1}$$，构成加法循环群。

> 目的在于，可以表示负数，且正负数在同一运算系统下，可以直接相加。

- 符号扩展 （sign extension）

$$
0011 \Longrightarrow 0000011
\\1101 \Longrightarrow 1111101
$$

> 将符号位复制到所有扩展高位中

- 补码求法：按位取反加一 （易知）

---

### 1.3 逻辑门

- 定义 - Boolean Function

  > Input ：一个或多个二进制输入
  >
  > Output ：一个二进制输出

![img](Digital-and-Logical-Design-学習ノート.assets/C2B5C16CEC36BBBAFA47BA4415583340.jpg)

- NOT gate - bubble
- **BUF gate** - Buffer - 传输大电流 / 更快中继
- AND gate
- OR gate
- XOR - “exclusive OR”
- XNOR - “XOR + NOT”
- 多输入门 - 上述几种扩展 - 多变量Boolean Expression

---

### 1.4 物理限制

- 电源电压
- **逻辑电平**

![img](Digital-and-Logical-Design-学習ノート.assets/1449F12010C69CF6DA52615D5CB431C4.jpg)

- 噪声容限：

$$
NM_L = V_{IL} - V_{OL}
\\NM_H = V_{OH} - V_{IH}
$$

- 静态约束（Q点）

  逻辑系列 - 行业标准 - 有兼容性

---

### **习题**

![img](Digital-and-Logical-Design-学習ノート.assets/456FF40572A32C3914C54665D2704F83.jpg)

![img](Digital-and-Logical-Design-学習ノート.assets/119E25E8C852D904137B1B44C5DE122C.jpg)

![img](Digital-and-Logical-Design-学習ノート.assets/D17574BB948B201C3C49EC601C15D561.jpg)

![img](Digital-and-Logical-Design-学習ノート.assets/FDFE301369C15788A248825C382D8D87.jpg)

![img](Digital-and-Logical-Design-学習ノート.assets/9EC910A7EA476236453B32A49E118FD6.jpg)

---





## **Chp2. 组合逻辑**

---

>- 对比时序逻辑（Sequential）：无记忆性、无反馈
>- Discipline: 面积、速度、功耗、易设计



- 逻辑函数表达式 == 组合逻辑（out 仅取决于 in）
- 组合逻辑分**2-level**和**Multi-level**

---

### 2.1 Black Box Abstraction

![img](Digital-and-Logical-Design-学習ノート.assets/31EA6C21DA1D49145ECCB90D5E80611C.jpg)

- Black Box 内部
  - component：E1、E2、E3
  - node：n1
- 组合逻辑电路
  - 功能规范：无记忆性
  - 时序（Timing）规范：In到Out的最大、最小延迟

![img](Digital-and-Logical-Design-学習ノート.assets/E56E4FE78889DEE576DA0F36ECAC02BD.jpg)

> 注意！：(d)不是组合电路，node6连接了两个输出

### 2.2 布尔代数 - 化简逻辑表达式

- 常用化简公式

$$
X+YZ=(X+Y)(X+Z)
$$

$$
BC+ \bar BD + CD = BC + \bar BD
$$

$$
\bar ABC = \bar ABC + \bar ABC
$$

- 和、积 相互转化（化简、优化电路）

$$
F = \bar {\bar F}
\\F = (F^*)^*
$$

---

### 2.3 Programmable Logic Array - PLA

2.3.1 电路原理图（schematic）

- Notice：
  - 反向门代替单独反向器，减少门的数量
  - CMOS中与非门、或非门优于AND、OR门（指都NOT后再输入）
  - 全功能性知，可只用NOT、AND/OR两个 (德摩根)

2.3.2 多级组合逻辑 - 减少硬件

- 推气泡法 - 优化CMOS电路

---

X和Z

---

### 2.5 卡诺图 - 化简逻辑表达式

- 原理



- 操作



- 无关项



> - 列表化简法（QM算法）
>
> [Implicant - Wiki](https://en.wikipedia.org/wiki/Implicant)
>
> [Quine-McCluskey Algorithm](https://en.wikipedia.org/wiki/Quine%E2%80%93McCluskey_algorithm)
>
> [Karnaugh map](https://en.wikipedia.org/wiki/Karnaugh_map)
>
> *note*: 找质蕴涵式(prime implicant)为NP问题，最小覆盖(minimum set cover)为NP-C问题。常近似最优（eg. *Espresso*）。
>
> > [More Logic Optimization](https://en.wikipedia.org/wiki/Logic_optimization)





### 3.4 Finite State Automaton (FSA)

- Moore
- Mealy
