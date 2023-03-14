---
title: 2.Static Complete Info Out
categories: [major, game theory]
tag: [game theory]
math: true
---

# Game Conponents

- A set of **Actions** of all the players
- A set of **Outcomes**
- The **Association** between action combinations and outcomes
- **Preferences** of each player over outcomes

## Complete Information 

---

A game of complete information requires that all the **game components** are common knowledge among all the players.

## Strategy

---

### Strategy, Pure Strategy, Pure Strategy Profile

- A **strategy** is a plan of action(to achieve a specific goal)
- A **pure strategy** $s_i\in S_i$ is a deterministic plan of action for player i.
- A **pure strategy profile** $s = (s_1, s_2, ... , s_n)\in S_1 \times S_2 \times ... \times S_n =: S$ represents a specific combination of strategies across all the players.

## Normal Form Game

---

### Normal Form Game: Definition

In order for a normal form game to be well-defined, we should describe

$\Gamma=\{I,\{S_i\}_{i\in N}, \{\nu_i(\cdot)\}_{i\in N}\}$

* A set of players $I = {1, 2, ..., n}$ 
* A set of pure strategy for each player $\{S_i\}_{i\in I}\space or\space \{S_1, ..., S_n\}$ 
- A set of payoff functions $\{u_i()\}$ where each function assigns value to all strategy profiles
	$v_i: S_1 \times ... \times S_n \rightarrow R$ 

### Normal Form Game: Static Game vs. Dynamic Game
 
 Do any player make decision before others?
 
 **Static Game**: Plaer A and player B make decisions at the same time. Equivalently player A makes decision first and player B makes decision later but without observing player A's decision(and vice versa)

 **Dynamic Game**: Player A makes decision first and then player B observes A's decision to make the decision.

### Normal Form Game: Prediction

What assumption do we make to proceed?
1. Players are **rational** to choose payoff-maximizing strategies which are consistently with some beliefs.
2. Players are **intelligent** to know all the game components
3. 1. and 2. are **common knowledge**
4. Prediction must be **Self-Enforcing**(That is, no one has incentives to deviate)

## Mixed Strategy

--- 

(Def)**Mixed Strategy**: 
Let $S_i=\{s_{i1},...,s_{im}\}$ be a finite set of pure strategies for player i.
$\sigma_i:S_i\rightarrow[0,1]\in\Delta S_i$ is a mixed strategy if $\sum_{s\in s_I}\sigma_i(s)=1$ (That is $\sigma_i$ is a probability mass function over $S_i$)

(Def)**Mixed Strategy Profile**:
$\sigma=(\sigma_1, ...\sigma_n)$ is a mixed strategy profile if $\sigma_i$ is a mixed strategy for each i.

> To compute player i's payoff, is it sufficient to know player i's (mixed) strategy $\sigma_i$ ?
	- No. Opponents' strategies $\sigma_{-i}$ are necessary to compute the payoff.

### Mixed Strategy: Payoff

- Player i's payoff for mixed strategy profile $\sigma=(\sigma_1,...,\sigma_n)$ 
$$u_i(\sigma)=\sum_{s\in S}(\Pi_{j=1}^n \sigma(s))u_i(s)=\sum_{s\in S}\sigma_1(s_1)...\sigma_n(s_n)u_i(s_1,...,s_n)$$
$$u_i(\sigma)=u_i(\sigma_i, \sigma_{-i})=\sum_{s_{i}\in S_i}\sigma_i(s_i)u_i(s_i,\sigma_{-i})$$
$$u_i(\sigma)=u_i(\sigma_i, \sigma_{-i})=\sum_{s_{i}\in S_i}\sigma_i(s_i)u_i(s_i,\sigma_{-i})$$

> See examples for Prisoner's Dilemma
 
### Pure & Mixed Strategy
Q: Does player's pure strategy space $S_i$ lie inside her mixed strategy space $\Delta S_i$ ?
A: Since a pure strategy $s_{ik}\in S_i$ is also probability distribution over the set of pure strategies, we have $S_i \subset \Delta S_i$.  
Our choice is degenerate distribution with probability one to $s_{ik}$ so that $\sigma_i(s_{ik})=1$ and $\sigma_i(s_i)=0$ for all $s_i \not = s_{ik}$ 