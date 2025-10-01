---
title: "Prelab Expectations and Recommendations"
author: [Department of Physics | University of Colorado Boulder]
---

Prelabs are essential activities designed to prepare you for the lab activities. They are due before the lab (see Canvas for the due dates), and are graded on completion. However, correctness is essential for being able to complete the labs correctly. It is recommended to corroborate with peers and/or come to office hours to ensure your prelabs are done correctly and you are properly prepared for lab.

# Modularize your work

You will be asked to perform calculations in the prelab using predetermined or given values. For example, you may be asked to calculate the parallel resistance of 2 resistors

$$\frac{1}{R_\text{total}} = \frac{1}{R_1}+\frac{1}{R_2}$$

using $50\ \Omega$ and $100\ \Omega$. When you get to lab and grab those resistors, you will measure them and they could be something like $50.5\ \Omega$ and $98.4\ \Omega$. It will save you time to write your calculations as functions (in Python, Mathematica, etc.) so that you can re-call the function with updated input values.

For example (in Python) instead of

```python
r = 1. / (1. / 50. + 1. / 100.)
```

You should

```python
def parallel_r(r1, r2):
    return 1. / (1. / r1 + 1. / r2)

print(parallel_r(50., 100.))
```

This way you can re-call the function later in the lab with the updated values without copy-pasting a bunch of code and editing it (this is very bad practice).

## Recycling functions

Many of the functions you build could be used several times throughout the course. The `parallel_r()` function above is a great example of one you may use repeatedly.

A decent way to make it easy to access all your functions is to make a `.py` script in the directory you will be working in. You can call it whatever you want, but for sake of example, here we will call it `jlab.py`.

In `jlab.py` you can write all your scripts, and then in your Jupyter notebooks, you can import and access your functions like this

```python
import jlab as jl

print(jl.parallel_r(50.5, 98.4))
```

# Including images/scans

If you make a directory called "images" in your working directory, and place all your images in there, you can call


`![](images/filename.png)`

# Exporting to PDF

![](header.PNG)
You can export to PDF directly through VS Code. [Here's some more info on setting up](https://code.visualstudio.com/docs/datascience/jupyter-notebooks).

## HTML alternative

If you're having trouble exporting to PDF (I did), you can export to HTML and then convert the HTML to PDF with an online tool like [Cloud Convert](https://cloudconvert.com/html-to-pdf).
