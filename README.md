# Evaluating Missing Data Techniques through Simulation

## Description
Missing data is a common issue in many datasets. If not handled properly, missing data can result in biased estimations and/or loss of power. I explore the different missingness mechanisms and several different techniques to deal with missing data including ad hoc methods, multiple imputation, and maximum likelihood. I use a simulation approach to uncover how each of these techniques compare to analysis with a complete dataset as well as their limitations. 

## Motivation

## Background

### Missing Data Patterns
There are many missing data patterns.  Below illustrates a few patterns that may appear in a dataset.

<p align = "center"> <img src="MDPattern.jpg" width = 500> </p>

### Missing Mechanisms
The missing data may occur in one of three ways: Missing Completely at Random (MCAR), Missing at Random (MAR), or Missing Not at Random (MNAR).  It is important to consider which missingness mechanism is at play, prior to applying a missing data technique.

Consider the below dataset where Education and Income was collected.  Education is the fully observed in the dataset (X), Income has some missing values in the dataset (Y), and R is a missing data indicator.

<p align = "center"> <img src="MMdata.jpg" width = 300> </p>

The missigness mechanism is based on the way X, Y, and R are related, as illustrated in the figure below (the blue line indicates a relationship).  For example, if people with higher incomes tend to not report their income, MNAR would apply because the missigness (R) is dependent on unobserved part of the data (Y).  If people with more education tend not to report their income, MAR would apply because the missigness (R) is dependent on the observed part of the data (X).

<p align = "center"> <img src="MM.jpg" width = 500> </p>

### Missing Data Techniques

Below summarizes some missing data techniques, although this is not an exhaustive list.  The effectiveness of some of these techniques are explored in the simulation.

<p align = "center"> <img src="MDTechniques.jpg" width = 500> </p>

