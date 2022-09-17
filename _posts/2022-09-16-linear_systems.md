---
layout: post
title:  "Linear Systems with Numpy and Scipy"
date: 2022-09-16 17:00
categories: jekyll update
tags: featured
image: /assets/images/data_science.jpg
mathjax: true
---
In the following we want to understand how to use `numpy` and `scipy` to solve Linear Systems with Python. 

To fix the notation, given a matrix $A \in \mathbb{R}^{n \times n}$ and a vector $y \in \mathbb{R}^n$, *solving* a linear system means finding (when exists) a vector $x \in \mathbb{R}^n$ such that it solves

$$
    Ax = y
$$

This is not hard to do in `numpy`, since it implements a function `np.linalg.solve`, taking as input a 2-dimensional array `A` and a 1-dimensional array `y`, and returns the solution `x` to the linear system. In particular:

```
# Generates the problem
A = np.array([[1, 1, 1], [2, 1, 2], [0, 0, 1]])
y = np.array([0, 1, 0])

# Solve the system
x_sol = np.linalg.solve(A, y)
print(f"The solution is {x_sol}.")
```

## Testing the accuracy
You already studied that, when the matrix $A$ is ill-conditioned, the solution of a linear system won't be correct, since the small perturbations on $y$ introduced by the floating point system will be amplified and the corresponding solution will be drammatically distant to the true solution. 

## Homework
Please refer to the [Homework PDF]({{ "/_download/homework1.pdf" | prepend: site.baseurl }}).