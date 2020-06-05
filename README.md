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

## Simulation

The objective of these simulations, is to compare the simulated sampling distribution from a complete dataset, to the sampling distributions from MCAR, MAR, and MNAR datasets, after applying a missing data technique (listwise deletion, mean imputation, regression imputation, multiple imputation, and maximum likelihood).  

Below gives an overview of the simulation:

<p align = "center"> <img src="SimulationOverview.jpg" width = 600> </p>

### Step 1: Create a Complete Dataset

In this step, I create N=40 rows, where income ~ Normal(48, 400) and education ~ 8 + 0.17 * income + e, such that e ~ Normal(0, 4),and education is then discretized.  Below is a visual of what a complete dataset might look like.  It makes sense that there is a linear relationship between income and education, because of the way the data was generated.

<p align = "center"> <img src="SimulationData.jpg" width = 400> </p>

### Step 2:  Apply Missingness Mechanism

Using the complete dataset generated in Step 1, I remove 25% of the data (i.e. n=10 rows) under each of the missingness mechanisms: MCAR, MAR, and MNAR.  For MCAR, n rows are randomly selected, and income is from those rows.  For MAR, the n rows where education is the largest is identified, and income is deleted from those rows.  Finally, for MNAR, the n rows where income is the largest is identified, and income is deleted from those rows.  At the end of this step, I have 4 datasets: Complete, MCAR, MAR, and MNAR.

### Step 3:  Apply Missing Data Technique

For each of the 4 datasets, a missing data technique is applied: listwise deletion, mean imputation, regression imputation, multiple imputation, or maximum likelihood.

### Step 4:  Analyze Data

Now that the data has been "cleaned", the data can be analyzed.  In this simulation, and to evaluate the validity of each technique, I chose to look at the sample mean of income.  Recall that income ~ Normal(48, 400), so the expected value of the sample mean of income is 48.  

### Step 5:  Repeat Steps 1 - 4

Steps 1 - 4 are repeated 1,000 times to generated a simulated sampling distribution.  The complete dataset is the "model" sample distribution.  Theoretically, the sampling distribution of the sample mean is 48 and with variance 10, as shown in the figure above.




