---
title: "Lab Skill Activity 1 - Mathematica Introduction"
author: [Department of Physics | University of Colorado Boulder]
---

# Goals

The big picture learning goals for the Mathematica Lab Skill activities are that you would be able to successfully use Mathematica throughout this course for presenting data, data analysis, computational modeling, and documenting your work in a well-organized and efficient way. By working through these lessons together, using the same program (Mathematica), we will have a shared experience with a powerful computational tool. In addition to the instructor, your classmates become a valuable resource for problem solving when you are using Mathematica, similar to working in a research lab. Also, the Mathematica screencasts are always available on YouTube for reference when you are completing similar tasks in the lab.

 You will be…

1. …able to use Mathematica as a calculator.

2. …able to use Mathematica's built in help.

3. …able to efficiently enter data into Mathematica.

4.    …able to create plots of functions and data.

5.    …able to create nicely formatted and well-organized Mathematica notebooks.

6. …motivated to learn Mathematica.

# Why Mathematica?

Mathematica has four essential features:

1. It is commonly used in the Physics Department at CU and elsewhere (MATLAB is also extremely common in Physics labs).
2. It has all the essential capabilities for computational modeling, plotting, and data analysis needed for this course. Once you learn these skills in one software package, it is much easier to learn another package.

3. Computer modeling is a way to tackle problems which are not analytically solvable, and for visualization of both simple and sophisticated problems.

4. Mathematica is *free* for all faculty and students through a university site license.

Other possible options were not as desirable for a few reasons. CU does not have a site license for MATLAB that allows for installation on student machines. Python is free with all the necessary functionality, but is less commonly used than Mathematica or MATLAB.

# Using Mathematica as a Calculator

Watch the [Introduction to Mathematica screencast.](https://tinyurl.com/2p83frb2) 

Start Mathematica and create a new notebook. **Keep all of your work in this Lab Skill Activity in this Mathematica notebook. You will turn in this Mathematica Notebook as evidence of completing the activity.**

1. Evaluate the following math expressions in Mathematica:
   1. $3\pi^2+4.1$
   2. $2+\frac{\sqrt{3}}{2}j$
   3. $e^{1.6\pi j}$
2. Assign the following variables and evaluate:
   1. $c=2\pi$
   2. $d=5\pi$
   3. $c+d=?$
3. Evaluate the following expressions:
   1. $sin^2(\frac{\pi}{4})$
   2. $log(2+\sqrt{3})$
   3. $|3+4j|^2$
4. Evaluate the following expressions:
   1. $(sin(2\pi +3)+cos(3\pi))^{1/2}$
   2. The vector $\vec{v} = (3,4,5)$

# Plotting Functions

You will often find it useful to plot functions. For example, in the process of doing an experiment, you may
need to visualize a theoretical prediction. Another common example is plotting fitted curve to the data.
This screencast takes you through the basics of plotting functions using the `Plot` function.

Watch a [screencast on plotting functions with Mathematica.](https://tinyurl.com/42kt2xyb)

1. Plot $sin^2\theta$ for $\theta$ between $0$ and $4\pi$.
2. Plot $sin~2t$ and $cos~3t$ together on the same plot for $t$ between $0$ and $10$.

# Manually Entering Data into Mathematica

Entering data efficiently into Mathematica will be useful anytime you take data by hand. You may have to
enter data from your lab notebook into Mathematica, or you may enter it directly into Mathematica. Even in the case of computerized data acquisition you will often have to record the filename and location and other settings which are not saved in the data file.

| $\lambda (m)$ |  $n$  |
| :-----------: | :---: |
|      0.3      | 1.553 |
|      0.4      | 1.531 |
|      0.5      | 1.521 |
|      0.6      | 1.516 |
|      0.7      | 1.513 |
|      0.8      | 1.511 |

Table: Wavelength dependence of the index of refraction of BK7 glass. BK7 glass is on of the most common glasses for lenses for visible wavelengths. {#tbl:1}

***Option 1: Entering data as a Mathematica list***

Regardless of how you input the data, it is always represented as a Mathematica list. Lists are like arrays. The following data from Table 1 has been directly entered as a list. The downside is it requires many curly brackets, and we lose the row-column format of the original data which may make you more prone to mistakes as you enter the data.

````
{% raw %}data = {{0.3,1.553},{0.4,1.531},{0.5,1.521},{0.6,1.516},{0.7,1.513},{0.8,1.511}}{% endraw %}
````

***Option 2: Entering data as a nicely formatted table***

In Mathematica you can directly enter data in the form of a table. Keyboard shortcuts make it very easy to
create additional rows and columns. `<ctrl+comma>` or `<cmd+comma>` creates a new column. `<ctrl+enter>` or `<cmd+enter>` creates a new row.

Watch the [screencast on entering data as a table and plotting it.](https://tinyurl.com/mubm43zy)

There is an [optional screencast](http://www.wolfram.com/broadcast/video.php?sx=grid&c=89&v=581) produced by Wolfram which is informative. 

# Plotting Data

Plotting data is another skill that is essential in the lab. By the end of this section you should be able to use the `ListPlot` function for plotting data. When using `ListPlot` you need to be sure the data in the correct form. The most common form data is a list of pairs of numbers. For example, `{% raw %}{{x1,y1},{x2,y2},…}{% endraw %}`.

Watch the screencast on [plotting data in Mathematica.](https://tinyurl.com/yr5c297e)

1. Plot the index of refraction data that you already entered into Mathematica.

# Getting Help in Mathematica

We are not born knowing Mathematica, so how can you get help? Mathematica's built-in help is very complete and helpful. Google searches will still sometimes be necessary, but the resources within Mathematica are often the best and fastest way to solve your problems. There are many different ways that Mathematica can provide help. The screencast will go over six:

1. Searching the Documentation Center [Help->Documentation Center]

2. `<F1>`brings up the Documentation Center and searches for any word the cursor is touching.

3. Executing `?FunctionName` in an input cell gives the basic syntax within the Mathematica notebook.

4. Autocomplete: Keyboard shortcut `<ctrl+k>` or [Edit->Complete Selection]

5. Autocomplete function arguments: Keyboard shortcut `<ctrl+shift+k>` or [Edit->Make Template]

6. Color coding

 Watch the [screencast on using Mathematica's built-in help.](https://tinyurl.com/24knrcht)

Use Mathematica's help to do the following tasks and answer the following questions:

1. Make a contour plot of any function of $𝑧 = 𝑓(𝑥, 𝑦)$ of your choice.
2. What is Mathematica's built in function name for inverse sine?
3. What does the `Table` function do? Use `Table` the function and explain how your code explains the result.
4. How do you numerically evaluate a result that still has $\pi$'s and square roots in it?

# Using Mathematica Effectively in Lab

If you use Mathematica notebooks effectively in the lab, they will be a place to have your data, plots, analysis, and results all in one place. This section of the lab skill activity will show you how to add organization like Titles, subtitles, sections, and subsections to your document. It will also show you how to annotate your document with paragraphs of text, well-formatted equations, and additional annotations to plots.

Watch the screencast on [using Mathematica effectively in the lab.](https://tinyurl.com/365b2pu8)

Your Mathematica notebook can be a convenient way to organize a lot of your data, plots, ideas, graphics. Let's apply some of the formatting features learned in this activity to your current Mathematica notebook. You will probably find it helpful to use the "Classroom Assistant Palette" to complete these tasks.

1. Create a Title section for your document, give it a reasonable name.
2. Create a Subtitle section and give your name.
3. Create a new Section for each problem.
4. If you can, take a picture with your cell phone and get it into your document.
5. Create a Text Cell and enter notes about what you took a picture of.
6. Insert a "Display Equation" and input a nicely formatted version of one of your favorite physics equations.
7. Add a hyperlink to some interesting physics website.
