# Evaluating Missing Data Techniques through Simulation

## Description
Missing data is a common issue in many datasets. If not handled properly, missing data can result in biased estimations and/or loss of power. I explore the different missingness mechanisms and several different techniques to deal with missing data including ad hoc methods, multiple imputation, and maximum likelihood. I use a simulation approach to uncover how each of these techniques compare to analysis with a complete dataset as well as their limitations. 

## Motivation
We are surrounded by data, and the insights that can be drawn from data using statistical and machine learning techniques are powerful.  An initial step in data analysis is to clean the data to ensure the it is of good quality so that sound conclusions can be drawn from the analysis.  A Forbes article reported that 60% of a Data Scientist's time is spent cleaning and organizing data.  Part of the cleaning stage includes addressing missing data.  Without propery handling missing data, results may be unreliable and biased.

The topic of missing data and techniques to address it is widely studied.  To dive deep in the understanding of the effectiveness of these missing data using a simulation approach.

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

