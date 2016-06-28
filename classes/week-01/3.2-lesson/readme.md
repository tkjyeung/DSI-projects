---
title: iPython Notebooks, Data Values, CSV Library
duration: "1:5"
creator:
    name: Lucy Williams
    city: DC
modified:
    name: Wee Kiang Yeo
    city: HK
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) iPython Notebooks, Data Values, CSV Library
Week 1 | Lesson 3.2

### LEARNING OBJECTIVES
*After this lesson, you will be able to:*
- Demonstrate how to use the notebook, code vs Markdown mode
- Show how to save and share the notebook via Jupyter
- Intro to csv library

### STUDENT PRE-WORK
*Before this lesson, you should already be able to:*
- Install Anaconda
- Install Jupyter


### LESSON GUIDE
| TIMING  | TYPE  | TOPIC  |
|:-:|---|---|
| 5 min  | [Introduction](#introduction)   |  Anaconda, Jupyter, Code vs. Markdown, and csv library |
| 5 min  | [Demo / Guided Practice ](#demo)  | Jupyter  |
| 5 min  | [Demo / Guided Practice ](#demo)  | Code vs. Markdown  |
| 10 min  | [Demo / Guided Practice ](#demo)  | csv library  |
| 5 min  | [Conclusion](#conclusion)  |   |



<a name="Anaconda, iPython notebook, Code vs. Markdown, and csv library"></a>
## Introduction: (5 mins)

Anaconda is a completely free Python distribution. It includes more than 400
of the most popular Python packages for science, math, engineering, and data analysis.
[Anaconda](https://www.continuum.io/downloads)

The Jupyter Notebook is a web application that allows you to create and share
documents that contain live code, equations, visualizations and explanatory text.
Uses include: data cleaning and transformation, numerical simulation,
statistical modeling, machine learning and much more.
[Jupyter](http://jupyter.org/)

Lastly, we will take a peek at the csv library.


<a name="Code vs. Markdown"></a>
## Demo: Code vs. Markdown (10 mins)

Let's play around with Jupyter first to get a feel for it. Let's create a new notebook by clicking on the "New" dropdown and selecting under "Notebooks", "Python 2". Let's change the title right away to something like "Practice", so we can easily ID it later.

The notebook starts off in the "Code" mode, which means that the cell is ready to accept
any code we write. Let's toggle it to "Markdown" mode. Practice writing a cell of code and then a cell of Markdown and run it.

Next, click through the dropdown menus: File, Edit, View, Insert, Cell, Kernel, and Help, just to get a look at what's available. Don't worry, you'll become more familiar with these through usage.

## Python File Modes

The difference of the file modes lies in how the end-of-line (EOL) is handled. Different operating systems use different characters to mark EOL - \n in Unix, \r in Mac versions prior to OS X, \r\n in Windows. If the file mode is 'r', 'w', or 'a', then text-mode is assumed and Python replaces the OS specific EOL character read from the file with just \n. Python also has a Universal newline mode. When a file is opened in this rU mode, Python maps all of the characters \r, \n and \r\n to \n.

| MODE  | DESCRIPTION |
|:-:|---|
| r | Read-only text mode |
| rU | Read using Universal newline mode |
| rb | Read-only binary mode |
| w | Write-only text mode. Note: overwrites any file with the same name |
| wb | Write binary mode |
| a | Append to existing text file (create it if it does not exist) |


<a name="csv module"></a>
## Demo: csv module (10 mins)

Let's take a look at the Python csv module. The csv module’s reader and
writer objects read and write sequences. 


We'll be using a small Sales data set to practice. Let's read a csv file first, using the following [demo code](./code/w1-3.2-demo.ipynb).

In jupyter notebook type:

```python
import csv
print 'Opening File. Data: '
print ''
with open('sales.csv', 'rU') as f:
    reader = csv.reader(f)
    for row in reader:
        print row
f.close()
print ''
print 'file closed'   # Always remember to close the file after writing to it!
```

The output will be the contents of sales.csv file. Now, let's write to a csv file.

In jupyter notebook type:

```python
print 'Adding the following record: '
data = ['123456', 'cosmos', 'neil', 'lucy', 'universe', '1', '1,000,000', 'presented']
print ''
print data
with open('sales.csv', 'a') as fp:
    out_name = csv.writer(fp, delimiter=',')
    fp.write('\n')
    out_name.writerows([data])

fp.close()
print ''
print 'file closed'    # Always remember to close the file after writing to it!
```

Now, let's see the file again, with the data you just added:

```python
print 'The new data that was just added, can be seen on the last line: '
with open('sales.csv', 'rU') as f:
    reader = csv.reader(f)
    for row in reader:
        print row

f.close()
print ''
print 'file closed'
```

<a name="conclusion"></a>
## Conclusion (5 mins)
Today we were introduced to Anaconda, Jupyter, and how to read and write csv files.
Nice. Next we'll be introduced to NumPy. Sounds like fun!
