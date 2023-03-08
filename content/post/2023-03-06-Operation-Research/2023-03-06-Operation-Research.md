---
title: Opteration Research
mathjax: true
categories: [major, Operation Research]
date: 2023-03-06 14:11:54
tags:
---

# The Simplex Method单纯 形法

Dantzig(1947)
比较CPF（角点可行解）

- **Constraint boundary equation** for any constraint
	- Obtained by replacing its <=, = or >= sign with and = sign
	- Defines a "flat" geometric shape(hyperplane)
 - The **boundary** of the feasible region
	 - Contains just those feasible solutions that satisfy one or more of the constraint boundary equations
	 - Any point on the boundary of the feasible region lies on at least one of the hyperplanes
- **Corner-point feasible(CPF)** solution
	- Feasible solution not on any line segment connecting two other feasible solutions
- Define Equation （定义方程)
	- 相交构成CPF的几个超平面方程

## 相邻的CPF

如果连接两个CPF的线段是可行域的**边**，则两个CPF相邻

## 最优性检验

1. Initialization: Choose(0,0) as he initial CPF solution to examine.
2. Optimality Test.

## Properties of CPF Solutions

- Property 1:
	- If there is exactly one optimal solution, then it must be a CPF solution
	- If there are multiple optimal solutions and a bounded feasible region, then at least two must be adjacent CPF solutions
- Property 2: There are only  finite number of CPF solutions
- Property 3: If a CPF solution has no adjacent CPF solutions that are better, then there are no better CPF solutions anywhere. Therefore, such a CPF solution must be an optimal solution, assuming that the problem possesses feasible solutions and a bounded feasible region.
- The feasible region always has the property of being a convex set(凸集)

## Setting up the Simplex Method

- First step: convert functional inequlity constraints into equlity constraints
	- Done by introducing **slack variables**
		- Example: constraint $x_1\le 4$ is equivalent to $x_1+x_3=4\space and\space x_3 \ge 0$ 
	- Resulting form known as **augmented form** 增广
每个CP对应一个Basic solution
CPF 对应 Basic feasible
 