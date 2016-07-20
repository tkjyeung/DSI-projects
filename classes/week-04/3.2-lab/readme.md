---
title: Plotting Classification Lab
type: lab
duration: "1:25"
creator:
    name: Faith / Jon
    city: DC / ATL
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Plotting Classification Lab

## Introduction

In this lab, you will need to build upon the codes of [Lesson 1.1](https://github.com/ga-students/DSI-HK-1/tree/master/classes/week-04/1.1-lesson/code/solution-code) and [Lesson 2.1](https://github.com/ga-students/DSI-HK-1/tree/master/classes/week-04/2.2-lab) to generate appropriate CSV files in order to:
* Use Tableau to make plots of kNN using varying values of k: k vs. accuracy, k vs. precision, k vs. recall
* Use Tableau to make plots of logistic regression using varying values of C: C vs. accuracy, C vs. precision, C vs. recall
* Use Tableau to put best kNN and best logistic on the same plot

### Useful references:
* [sklearn.metrics.precision_score](http://scikit-learn.org/stable/modules/generated/sklearn.metrics.precision_score.html)
* [sklearn.metrics.recall_score](http://scikit-learn.org/stable/modules/generated/sklearn.metrics.recall_score.html)

### Steps:
- Compile your comparison data in CSV.
- Open Tableau and create a new data source pointing to your data.
- Create a new Tableau Worksheet and produce a scatter plot of the measure pairs.

## Hint:
A scatter plot requires two measures and one dimension. Drop one measure on the ‘Rows’ bar and one measure on the ‘Columns’ bar. To plot individual points on the scatter plot, drop the dimension representing unique tests on the ‘Color’ mark button.

#### Requirements

- Pull and connect only relevant data.
- Use your data to produce scatter plots of the measure pairs.

#### Deliverables

- Use Tableau to make plots of kNN: k vs. accuracy, k vs. precision, k vs. recall
- Use Tableau to make plots of logistic: C vs. accuracy, C vs. precision, C vs. recall
- Use Tableau to put best kNN and best logistic on the same plot

## Additional Resources
- [Plotting Classification](http://www.mathworks.com/help/stats/examples/classification.html?requestedDomain=www.mathworks.com)
- [How to choose the right chart or graph](http://www.tableau.com/learn/whitepapers/which-chart-or-graph-is-right-for-you)
