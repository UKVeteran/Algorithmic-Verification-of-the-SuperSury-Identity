<div align="center">
  <h1>Algorithmic Verification of the SuperSury Identity</h1>
  <p><b>A generalized framework for linear recurrence convolutions and structural identity mappings.</b></p>
</div>

---

## 📖 Overview

This repository contains the computational verification framework and mathematical documentation for the **SuperSury Identity**. 

The SuperSury identity represents a recent, major advancement in the theory of linear recurrence convolutions. Proposed initially by Dresden and Gao, it establishes a fundamental inversion of the mathematical degrees of freedom used in historical approaches to generalized Sury identities.

This repository demonstrates the identity's structural robustness through exhaustive computational verification against standard classical sequences and randomized high-order recurrences.

---

## 🧮 The Mathematics: The Paradigm Shift

Classical generalizations (such as those by Marques, Edgar, and Abd-Elhameed & Zeyada) forced a user to pick an arbitrary exponential base $t$, which distorted the internal algebra of the summand to preserve equality. This resulted in complicated, hybrid summands. 

The **SuperSury Framework** fundamentally shifts this approach:
* **Summand Simplicity:** It completely eliminates hybrid terms. The summand contains only a singular, unmixed element of the target sequence $(X_{i+k})$. 
* **Dynamic Base Locking:** The user selects an arbitrary second-order recurrence sequence $X_{n}$ and an arbitrary structural index offset $k$. The framework dynamically dictates the unique geometric base $t$ required to satisfy closure.
* **Sequence Autonomy:** It detaches from rigid boundary conditions ($i=0$), allowing summations to initiate from any arbitrary offset position $k$, including negative index boundaries.

### Theorem 1 (The SuperSury Identity)
Let $X_{n}$ be an arbitrary second-order linear recurrence sequence defined by $X_{n}=c_{1}X_{n-1}+c_{2}X_{n-2}$ with arbitrary initial values $X_{0}$ and $X_{1}$. 

For any fixed integer index shift $k$ such that $X_{k}$ and $X_{k-1}$ are non-zero, the geometric base is structurally locked to $t=-\frac{c_{2}X_{k-1}}{X_{k}}$, yielding the identity:

$$X_{0}X_{n+2}-X_{1}X_{n+1}=\frac{X_{0}X_{2}-X_{1}^{2}}{X_{k}}\sum_{i=0}^{n}(-\frac{c_{2}X_{k-1}}{X_{k}})^{n-i}X_{i+k}$$

---

## 🔍 Special Case Corollaries

The framework's flexibility allows it to beautifully collapse into clean arithmetic formulations for classical sequences.

### 1. The Fibonacci Instance
For the standard Fibonacci sequence ($X_{n}=F_{n}$) with an arbitrary shift index of $k=3$, the geometric base dynamically locks to $t=-1/2$. This simplifies the system to:

$$-F_{n+1}=-\frac{1}{2}\sum_{i=0}^{n}(-\frac{1}{2})^{n-i}F_{i+3}$$

### 2. The Lucas Instance
For the standard Lucas sequence ($X_{n}=L_{n}$) with an arbitrary shift index of $k=1$, the configuration forces the geometric base to lock into a clean negative integer value, $t=-2$. This yields:

$$2L_{n+2}-L_{n+1}=5\sum_{i=0}^{n}(-2)^{n-i}L_{i+1}$$

Because the left-hand side expansion elements satisfy the baseline sequence relation, this uncovers an elegant, alternating weighted identity that maps Lucas summations directly to scalable Fibonacci outputs:

$$2L_{n+2}-L_{n+1}=5F_{n+1}$$

---

## 💻 Computational Verification

To establish absolute algebraic rigor, all configurations in this repository were verified using exact rational arithmetic, completely bypassing floating-point roundoff issues. 

The verification suite evaluates:
1. **Classical Sequences:** Fibonacci ($k=3, t=-1/2$) and Lucas ($k=1, t=-2$) formulations.
2. **Identity 1 (Lucas 3-step):** Evaluated under a higher-order sequence transformation $(Y_{n}=-7Y_{n-1}+12Y_{n-2}-4Y_{n-3})$.
3. **Identity 2 (A015530):** Evaluated using the classic OEIS sequence ($c_{1}=4, c_{2}=3, X_{0}=1, X_{1}=4$).
4. **General Case Validation:** A randomized pattern ($X_{0}=3, X_{1}=7, c_{1}=5, c_{2}=-2, k=2$) locking to $t=14/29$.

### Sample Trace: Fibonacci ($k=3, t=-1/2$)

| $n$ | Fibonacci Formula LHS | Fibonacci Formula RHS | Match |
|:---:|:---:|:---:|:---:|
| 0 | -1 | -1 | True |
| 1 | -1 | -1 | True |
| 2 | -2 | -2 | True |
| 3 | -3 | -3 | True |
| 4 | -5 | -5 | True |
| 5 | -8 | -8 | True |

---

## 🚀 Conclusion

The computational evidence gathered confirms that the Dresden-Gao approach provides a universal mechanism for generating weighted sum identities for second-order recurrences. By shifting the mathematical focus from parameter tuning to sequence autonomy, the SuperSury Identity uncovers hidden symmetrical structures within classical number theory and provides a clear blueprint for higher-order sequence extensions.

---

## 📚 Bibliography

* **Ashfaque, Johar M.** (2026). *Algorithmic Verification of the SuperSury Identity*. July 2, 2026.
