# 电–热–气–氢综合能源系统优化调度模型（简化复现）

本仓库为以下论文的**简化复现与算例实现**：

> **Resource scheduling and capacity allocation optimization of an integrated electricity–heat–gas–hydrogen energy system**  
> *Applied Energy*, 2025  
> https://www.sciencedirect.com/science/article/pii/S0360544225043257

---

## 项目简介

本项目构建了一个**电–热–气–氢综合能源系统（Integrated Energy System, IES）**的优化调度模型，重点研究在可再生能源接入条件下，多能耦合系统的协同运行与资源调度问题。

模型以**短期运行调度（24 小时）**为研究对象，通过优化各类能源转换装置、储能系统及外部能源购入策略，实现系统总运行成本最小化。

---

## 与原论文的关系与简化说明

本代码**基于原论文的建模思想与系统结构**，但为便于复现与分析，对模型进行了如下简化：

- ❌ **未考虑 CO₂ 捕集系统、碳交易机制及排放约束**
- ❌ 未引入甲烷发生器等扩展装置
- ✅ 仅考虑 **电力、热力、天然气、氢能** 四类能源系统
- ✅ 保留风电与光伏发电的随机出力特性
- ✅ 建模了电、热、气、氢四类储能系统
- ✅ 引入电解槽与氢燃料电池实现电–氢耦合
- ✅ 允许外购电、外购气和外购氢
- ✅ 通过弃电惩罚项刻画可再生能源消纳行为

因此，本项目属于**面向方法验证与结果复现的简化模型**，并非对原论文的完整实现。

---

## 模型特点

- 电 / 热 / 气 / 氢 四能量系统统一优化调度
- 多能源平衡约束与能量转换机理建模
- 储能充放电互斥与 SOC 动态约束
- 风电、光伏弃电建模及惩罚机制
- 弃电惩罚系数灵敏度分析
- 基于 Gurobi 求解的混合整数线性规划模型

---

## 结果展示

模型求解后可得到以下典型结果图：

### 电能量平衡
![Electricity balance](figures/elec_balance.png)

### 天然气能量平衡
![Gas balance](figures/gas_balance.png)

### 氢能量平衡
![Hydrogen balance](figures/hydrogen_balance.png)

### 热能量平衡
![Heat balance](figures/heat_balance.png)

### 弃电惩罚系数灵敏度分析
![Curtailment sensitivity](figures/curtailment_sensitivity.png)

相关结果图像在运行代码后自动生成并保存在项目目录中。

---

## 说明与声明

- 本项目仅用于**学术研究与学习交流**
- 模型参数与算例规模为简化设定
- 若在科研工作中使用本代码，请**务必引用原论文**

---

## 参考文献

[1] Resource scheduling and capacity allocation optimization of an integrated electricity–heat–gas–hydrogen energy system,  
*Energy*, 2025.
