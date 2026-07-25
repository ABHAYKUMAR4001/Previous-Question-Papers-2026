# ISM (Introduction to Statistical Methods) - Comprehensive Exam Questions (Full Verbatim)

**Papers Covered:**
- 2022-23 EC3 Regular - April 2023 (40 marks)
- 2022-23 EC3 Makeup - April 2023 (40 marks)
- 2023-24 EC3 Regular - April 2024 (40 marks)
- 2023-24 EC3 Makeup - April 2024 (40 marks)
- S2 2023-24 EC3 Regular - Sept 2024 (40 marks)
- S2 2023-24 EC3 Makeup - Oct 2024 (40 marks)
- ISM AIML Compre Regular - 2025 (40 marks)
- ISM AIML Compre Makeup - April 2025 (40 marks)

> **Note:** Questions involving diagrams/figures are marked with [DIAGRAM IN ORIGINAL]. Refer to the original PDF for visual content.

---

## 1. Hypothesis Testing (t-test, Z-test)


### Q1 [2022-23 EC3 Makeup, Q1a - 5M]

Manufacturer of product 'A' claims that average life of the product is 120 months with variance 25 months. A random sample of 10 of these is with mean 125 months and standard deviation 4 months. Validate the claim of the manufacturer at 1% level of significance.

---

### Q2 [2022-23 EC3 Makeup, Q1b - 5M]

It is claimed that player A is better than Player B in IPL matches during IPL bidding for players. During previous IPL season both played 18 matches with average runs scored 85 and 75 with standard deviations 9 and 2 respectively. Validate the claim using appropriate statistical procedure at 1% level of significance.

---

### Q3 [2022-23 EC3 Regular, Q1a - 5M]

It is observed that average life of product 'A' follows normal distribution. Manufacturer of product 'A' claims that average life of the product is at least 120 months with variance 25 months. A random sample of 10 of these is with mean 125 months and standard deviation 4 months. Validate the claim of the manufacturer at 5% level of significance.

---

### Q4 [2023-24 EC3 Makeup, Q2 - 7M]

Validate the hypothesis that product A is superior to product B in terms of performance. A sample of 20 items of product A is having mean life of 12 months with standard deviation 15 days where as product B is having mean life of 10 months with standard deviation 10 days. Use p-value and validate the hypothesis.

**Solution requires:**
- $H_0$: product A is not significantly superior to product B
- $H_1$: product A is significantly superior to product B (one tailed)
- Pooled SD: $s = \sqrt{\frac{(n_1-1)S_1^2 + (n_2-1)S_2^2}{n_1+n_2-2}}$
- Test statistic: $t = \frac{\bar{x_1} - \bar{x_2}}{s\sqrt{\frac{1}{n_1} + \frac{1}{n_2}}}$

---

### Q5 [2023-24 EC3 Regular, Q3 - 7M]

A sample of 30 milk cartons provides a sample mean of 505 ml. The population standard deviation is believed to be 10 ml. Perform a hypothesis test, at the 0.05 level of significance, population mean 500 ml and to help determine whether the filling process should continue operating or be stopped and corrected. Use p-value also to validate the hypothesis.

Given:
- Sample size = 30
- Sample mean = 505 ml
- Population mean = 500 ml
- Population SD = 10 ml
- Significance level = 0.05

$H_0: \mu = 500$ vs $H_a: \mu \neq 500$

$z = \frac{\bar{x} - \mu}{\sigma/\sqrt{n}} = \frac{505 - 500}{10/\sqrt{30}}$

---

### Q6 [Sept 2024 EC3R, Q2b - 5M]

A company manufactured a product on two machines i.e. Machine A and Machine B. Consider the following information related to sampling of these to test and compare them. Based on this information, can we conclude that the product manufactured by Machine A is superior to Machine B.

| Machine | Sample size | Mean | Standard Deviation |
|---------|-------------|------|-------------------|
| Machine A | 15 | 5.5 | 0.5 |
| Machine B | 15 | 5.1 | 0.2 |

---

### Q7 [Oct 2024 EC3M, Q1 - 5M]

A food delivery service claims that their average delivery time is 10 minutes or less. A random sample of 8 deliveries shows the following delivery times (in minutes): 12, 9, 11, 10, 8, 14, 7, 13.

At a 5% significance level, test whether there is sufficient evidence to reject the service's claim. Use an appropriate hypothesis test and clearly state:
- The null and alternative hypotheses
- The test statistic used
- The critical value or p-value
- Your conclusion about whether the goal of 10 minutes or less is being achieved.

---

### Q8 [Compre Makeup 2025, Q1a - 4M]

A mould is mounted on a moulding machine by using two different techniques and the mounting time is a crucial period in production management. Hence the manager needs to determine whether there is any significant difference in the two moulding procedures. A sample is collected for both processes and is listed in the following table. State the hypothesis and test with 0.05 level of significance.

| Process-1 (in Hrs) | Process-2 (in Hrs) |
|--------------------|-------------------|
| 2 | 3 |
| 4 | 7 |
| 9 | 5 |
| 3 | 8 |
| 2 | 4 |
| --- | 3 |

---

## 2. Chi-Square Test (Goodness of Fit & Independence)


### Q1 [2023-24 EC3 Regular, Q2 - 7M]

National Highway Authorities of India (NHAI) proposes to automate the process of quality check in place of existing manual random check before the financial clearance of the bills for the work done by the agencies. NHAI wants to use Deep learning methods in the automated process. The following data gives the number of instances the methods correctly/incorrectly identified the quality of the work as proposed during bidding in DPR (Detailed project report).

Formulate a suitable hypothesis and validate it at 1% Level of significance.

| | Correctly identified | Incorrectly identified |
|---|---|---|
| Manual check | 200 | 220 |
| Automated check | 300 | 280 |
| **Total** | **500** | **500** |

Formula: $\chi^2 = \sum \frac{(O-E)^2}{E}$

Expected frequency: $E = \frac{\text{Row total} \times \text{Column total}}{N}$

Degrees of freedom: $(r-1)(c-1)$

---

### Q2 [2022-23 EC3 Makeup, Q2a - 4M]

Formulate a suitable hypothesis and validate it by using appropriate statistical procedure based on the following data. (At 5% level of significance)

"Before pandemic 200 out of 750 students are attending online classes whereas after pandemic 350 out of 800 are doing the same".

---

### Q3 [Sept 2024 EC3R, Q2a - 5M]

An agency conducted a survey to understand the trend related to student's preferences in taking admissions:

| Program | Number of Students |
|---------|-------------------|
| B.E(CSE) | 320 |
| B.E(AIML) | 240 |
| B.E(DSE) | 350 |
| B.E(Cyber Security) | 200 |
| B.E(IoT) | 90 |
| **Total** | **1200** |

Is it reasonable to conclude that there is no preference among the five B.E programs offered as mentioned above? (Level of significance = 0.05)

---

### Q4 [Compre Makeup 2025, Q3b - 4M]

A WILP faculty believes that the distribution of students across different extracurricular activities (Sports, Music, Art, and Drama) is equal. A random sample of 200 students is surveyed, and the observed number of students in each category is recorded as follows:

| Activity | Sports | Music | Art | Drama | Total |
|----------|--------|-------|-----|-------|-------|
| Observed (O) | 55 | 45 | 60 | 40 | 200 |

Test the principal's claim at a 5% significance level using the Chi-square goodness-of-fit test.

Expected (E) for each = 200/4 = 50

$\chi^2 = \sum \frac{(O_i - E_i)^2}{E_i}$

df = (Number of categories - 1) = 3

---

### Q5 [Oct 2024 EC3M, Q2b - 5M]

Following data is related to players' performance in one day series and IPL leagues. Using a suitable test, check whether there is any association between a player's performance in one day series and IPL league at 1% Level of significance. (Use and state assumptions if required)

| | Runs scored - One day series | Runs scored - IPL Series |
|---|---|---|
| Player A | 1000 | 200 |
| Player B | 800 | 700 |
| Player C | 600 | 500 |
| Player D | 900 | 400 |
| Player E | 200 | 600 |

---

## 3. Proportion Tests (Z-test for Proportions)

### Q1 [2022-23 EC3 Regular, Q2a - 3M]

Manufacturer of a drug claims that one of their patented drugs is effective in curing pulmonary diseases with 75% efficiency. It is observed that 380 out of 500 patients used this drug found that it is effective in curing pulmonary diseases. Validate the claim at 1% level of significance by using an appropriate test.

---

### Q2 [2023-24 EC3 Makeup, Q3a - 3M]

If the true proportion of voters who support Proposition A is $P = 0.4$, what is the probability that a sample of size 200 yields a sample proportion between 0.40 and 0.45?

$\sigma_{\hat{p}} = \sqrt{\frac{P(1-P)}{n}} = \sqrt{\frac{0.4(1-0.4)}{200}} = 0.03464$

$P(0.40 \leq \hat{p} \leq 0.45) = P\left(\frac{0.40-0.40}{0.03464} \leq Z \leq \frac{0.45-0.40}{0.03464}\right) = P(0 \leq Z \leq 1.44)$

---

## 4. Confidence Intervals

### Q1 [2023-24 EC3 Makeup, Q3b - 3M]

A sample of 11 circuits from a population has a mean resistance of 2.00 ohms. We know from past testing that the population standard deviation is 0.35 ohms. Determine a 99% confidence interval for the true mean resistance of the population.

$$\bar{x} \pm z_{\alpha/2} \frac{\sigma}{\sqrt{n}} = 2 \pm 2.58\left(\frac{0.35}{\sqrt{11}}\right) = 2 \pm 0.2723$$

$$1.7277 < \mu < 2.2723$$

---

### Q2 [2023-24 EC3 Regular, Q6a - 3M]

A sample of 11 circuits from a large normal population has a mean resistance of 2.20 ohms. We know from past testing that the population standard deviation is 0.35 ohms. Determine a 95% confidence interval for the true mean resistance of the population.

---

### Q3 [Compre Makeup 2025, Q3a - 4M]

Find the 98% confidence interval for the average time students spend on a deep learning project. A sample of 15 students was taken, and their recorded project completion times (in hours) were:

76, 85, 90, 78, 83, 88, 91, 75, 84, 79, 87, 92, 80, 86, 89

Assume the time spent follows a normal distribution, but the population standard deviation is unknown.

Sample Mean $(\bar{x})$ = ?, Sample SD $(s)$ = ?

$\alpha = 0.02$, critical t-value for $t_{0.01, 14}$ = ?

CI: $\bar{x} \pm t_{\alpha/2, n-1} \cdot \frac{s}{\sqrt{n}}$

---

## 5. Probability & Joint Distributions


### Q1 [2023-24 EC3 Makeup, Q1 - 7M]

Consider the following joint probability density function:

$$f(x, y) = \frac{c(x + y)}{2}, \quad 0 < x < 2, \quad 0 < y < 3$$

Then find:
i) c value
ii) Marginal probability distributions of X, Y
iii) $P(X < 1, Y < 2)$
iv) Are X and Y independent? Validate.

---

### Q2 [2023-24 EC3 Regular, Q1 - 7M]

Consider the following joint probability distribution:

| X \ Y | -1 | -2 | 3 |
|--------|-----|-----|-----|
| 0 | k | 2k | 2k |
| 1 | 2k | k | k |
| 2 | k | 2k | k |
| 3 | 3k | 3k | k |

Then find:
i) k value
ii) Marginal probability distributions of X, Y
iii) $P(X < 2, Y < -3)$
iv) $P(X < 2 \mid Y < -3)$
v) Are X and Y independent? Validate.

---

### Q3 [Sept 2024 EC3R, Q1c - 5M]

Let the joint probability density function for (X, Y) be:

$$f(x, y) = \begin{cases} \frac{x+y}{3}, & 0 < x < 2, \quad 0 < y < 1 \\ 0, & \text{otherwise} \end{cases}$$

i) Find the probability $P(X > Y)$
ii) Find the marginal probability density function of X.
iii) Find the marginal probability density function of Y.
iv) Are X and Y independent?

---

### Q4 [Sept 2024 EC3R, Q1a - 3M]

A survey shows 50% of all American workers are having workplace retirement plan, 60% have health insurance, and 49% have both benefits. We select a worker at random.

(a) What is the probability he has health insurance, if he has a retirement plan?
(b) What is the probability he has retirement plan, if he has health insurance?
(c) What is the probability he is not having health insurance given that he has a retirement plan?

---

### Q5 [Sept 2024 EC3R, Q1b - 2M]

If the chance of running a bus service according to schedule is 0.75, calculate the probability on a day schedule with 10 services:
(i) exactly one is late
(ii) at least one is late

---

## 6. Time Series - Moving Averages

### Q1 [2023-24 EC3 Regular, Q4 - 7M]

For the following data production of wheat in tons, calculate the 3 year moving average. Also find the mean square error (MSE) and mean absolute deviation (MAD).

| Year | 2011 | 2012 | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 |
|------|------|------|------|------|------|------|------|------|------|------|
| Production (tons) | 86 | 63 | 45 | 58 | 43 | 57 | 98 | 100 | 120 | 150 |

---

### Q2 [2022-23 EC3 Makeup, Q3 - 10M]

Try to model the following time series data by using two models mentioned. Suggest the better of these two to be used for forecast.

a) Model 1: Simple moving averages model with k = 3
b) Model 2: Weighted moving averages with weights 0.3, 0.2 and 0.1 (i.e. latest will be given more weightage and so on)

[DATA TABLE IN ORIGINAL]

---

### Q3 [Sept 2024 EC3R, Q3b - 5M]

Fit 3-year moving average and 5-year moving average models to the following data. Use a suitable error function and suggest the optimal model.

| Year | Sales (in crores) |
|------|-------------------|
| 2014 | 12 |
| 2015 | 16 |
| 2016 | 20 |
| 2017 | 15 |
| 2018 | 16 |
| 2019 | 17 |
| 2020 | 21 |
| 2021 | 18 |
| 2022 | 19 |

---

### Q4 [Oct 2024 EC3M, Q3b - 10M]

Consider the following time series data:

| Year | Sales (in crores) |
|------|-------------------|
| 2014 | 12 |
| 2015 | 16 |
| 2016 | 20 |
| 2017 | 15 |
| 2018 | 16 |
| 2019 | 17 |
| 2020 | 21 |
| 2021 | 18 |
| 2022 | 19 |

i) Fit an exponential smoothing model, if possible. If not, state the reasons.
ii) Fit a suitable moving average of your choice.
iii) Compare the above models and conclude.

---

### Q5 [Compre Makeup 2025, Q2a - 4M]

For the following data: production of wheat in tons, calculate the 4-year centered moving average. Also find the mean square error (MSE) and mean absolute deviation (MAD).

| Year | 2011 | 2012 | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 |
|------|------|------|------|------|------|------|------|------|------|------|
| Production (tons) | 76 | 83 | 89 | 96 | 103 | 117 | 126 | 137 | 141 | 150 |

4-year MA formula: Average of 4 consecutive values
Centered MA: Average of two consecutive 4-year MAs

$MSE = \frac{\sum(Y_t - F_t)^2}{n}$

$MAD = \frac{\sum|Y_t - F_t|}{n}$

---

## 7. Time Series - Exponential Smoothing


### Q1 [2023-24 EC3 Makeup, Q4 - 7M]

Find the exponential smoothing for $\alpha = 0.4$ and $\alpha = 0.6$ for the following data and also find out which weighting factor gives better smoothing.

| Month/Year | 1.2001 | 2.2001 | 3.2001 | 4.2001 | 5.2001 | 6.2001 | 7.2001 | 8.2001 | 9.2001 | 10.2001 | 11.2001 | 12.2001 |
|-----------|--------|--------|--------|--------|--------|--------|--------|--------|--------|---------|---------|---------|
| Deflection | -213 | -564 | -35 | -15 | 141 | 115 | -420 | -360 | 203 | -338 | -431 | 194 |

Formula: $F_{t+1} = \alpha Y_t + (1-\alpha)F_t$

Compare using MSE: $MSE = \frac{\sum(Y_t - F_t)^2}{n}$

---

### Q2 [2023-24 EC3 Regular, Q5 - 6M]

A state government is studying the number of traffic fatalities (in hundreds) in the state resulting from drunken driving in the last months of 2023. Using simple exponential smoothing, with the smoothing factor 0.6, forecast the traffic fatalities for the 13th month (i.e. first month of 2024).

| Month | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|-------|---|---|---|---|---|---|---|---|---|----|----|-----|
| Traffic fatalities | 28 | 30 | 28 | 28 | 27 | 24 | 23 | 26 | 21 | 27 | 22 | 35 |

---

### Q3 [Sept 2024 EC3R, Q3a - 5M]

Consider the following time series data:

| Month | January | February | March | April | May |
|-------|---------|----------|-------|-------|-----|
| Sales (in Lakhs) | 50 | 52 | 54 | 55 | 57 |

Assuming the forecast for the month of January as 50, fit exponential smoothing models to the above data with a smoothing parameter $\alpha = 0.10$ and $\alpha = 0.70$. Choose the best model between these two and forecast the sales for the month of June.

---

### Q4 [2022-23 EC3 Regular, Q3a - 5M]

For the month of March 2023, actual demand for a product is 250 units whereas the forecast is 280 units. Is it possible to forecast the demand for the month of April 2023? If possible, forecast for April 2023 using an appropriate time series model.

---

## 8. Autocorrelation

### Q1 [2023-24 EC3 Makeup, Q5 - 6M]

The following data gives the frequency of Cargo exports in years $Y_t$ in a state of a country. Find the autocorrelation at the lag 1.

| Year (t) | 2011 | 2012 | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 |
|---------|------|------|------|------|------|------|------|------|------|------|
| Cargo exports ($Y_t$) | 1230 | 1345 | 1382 | 1416 | 1593 | 1802 | 1817 | 1995 | 2212 | 2607 |

Formula:
- $\text{Autocovariance}(k) = \frac{\sum_{t=k+1}^{n}(Y_t - \bar{Y})(Y_{t-k} - \bar{Y})}{n-k}$
- $\text{Autocorrelation}(k) = \frac{\text{Autocovariance}(k)}{\text{Variance}}$

---

### Q2 [Compre Makeup 2025, Q4a - 4M]

Consider the following time series data representing the monthly sales (in thousands) for a company over 5 months:

| Month | Sales (in '000s) |
|-------|-----------------|
| 1 | 50 |
| 2 | 55 |
| 3 | 53 |
| 4 | 60 |
| 5 | 58 |

Compute the autocorrelation at lag 2 for the given time series data. Interpret your conclusion.

Mean $\bar{X} = 55.2$

---

## 9. Linear Regression & Correlation


### Q1 [2022-23 EC3 Regular, Q2b - 7M]

Discuss the Significance of Correlation and Regression in understanding the data. And find correlation coefficient & linear regression $(y = f(x))$ of the following data.

[DATA TABLE IN ORIGINAL]

---

### Q2 [2022-23 EC3 Makeup, Q2b - 6M]

Consider the following data. Use an appropriate statistical understanding (numerical) to take the decision to proceed further or not to build a simple linear regression $(y = f(x))$ model for prediction. If yes, use it to predict y when x = 10.

[DATA TABLE IN ORIGINAL]

---

### Q3 [2023-24 EC3 Regular, Q6b - 3M]

i) What is the conclusion if the coefficient of correlation is zero?

ii) Let $X_1$, $X_2$, $X_3$ are features and Y is the target variable. Coefficient of Correlation between them are:
- $(Y, X_1) = 0.85$
- $(Y, X_2) = 0.60$
- $(Y, X_3) = 0.10$
- $(X_1, X_2) = 0.95$
- $(X_1, X_3) = 0.30$

Then how can you proceed further as a part of pre-processing before fitting linear Regression model. Discuss and validate your actions in this regard.

---

### Q4 [2023-24 EC3 Makeup, Q6a - 7M]

For the following data on sales, fit a linear trend by the method of least squares. Forecast the sales for the year 2025.

| Year | 1995 | 2000 | 2005 | 2010 | 2015 | 2020 |
|------|------|------|------|------|------|------|
| Sales ('000) | 16 | 20 | 18 | 15 | 18 | 21 |

---

### Q5 [Sept 2024 EC3R, Q4a - 7M]

Consider the following data:

| X | 10 | 12 | 15 | 13 | 11 | 19 |
|---|----|----|----|----|----|----|
| Y | 20 | 22 | 25 | 18 | 17 | 22 |

i) Comment on the relation between X and Y using co-variance.
ii) Comment on the relation between X and Y using coefficient of correlation.
iii) Write your inference based on the above.

---

### Q6 [Sept 2024 EC3R, Q4b - 3M]

A project related to prediction is given to two teams A, B and C.
- Team A proposed multiple linear regression model (with SSE as loss function) with accuracy of 80%
- Team B proposed polynomial regression model (with SSE) with accuracy of 90%
- Team C proposed multiple regression model using gradient descent approach with accuracy of 85%

Write your observations on each model if you are asked to select the best model to be used for prediction among A, B and C.

---

### Q7 [Oct 2024 EC3M, Q4 - 10M]

Consider the following data. $(Y = f(X))$

| X | 12 | 10 | 13 | 10 | 9 | 14 |
|---|----|----|----|----|---|-----|
| Y | 15 | 20 | 22 | 13 | 12 | 18 |

i) Check whether x and y are having any linear relation using a suitable statistical approach.
ii) Find a suitable linear relation using "Sum of Squared Errors" (SSE) as the loss/cost function.
iii) Use this relation to predict y when x = 20.

---

### Q8 [Compre Makeup 2025, Q1b - 4M]

A company wants to study the relationship between daily working hours (X) and employee productivity (Y) in terms of completed tasks. The data is as follows:

| X | 5 | 6 | 4 | 7 | 8 | 5.5 |
|---|---|---|---|---|---|-----|
| Y | 15 | 18 | 12 | 20 | 23 | 16 |

Using this data, answer the following:
i) Compute the Pearson correlation coefficient (r).
ii) Does increasing working hours significantly improve employee productivity?

---

### Q9 [Compre Makeup 2025, Q4b - 4M]

A professor wants to develop a model to predict the weight of students (y) based on their height (x). The professor has collected the following data on the height and weight of 10 students:

| x | 85 | 94 | 101 | 50 | 88 | 88 | 61 | 68 | 94 | 74 |
|---|----|----|-----|----|----|----|----|----|----|-----|
| y | 61 | 75 | 97 | 85 | 68 | 44 | 79 | 59 | 98 | 73 |

i) Fit a linear regression line of weight (y) on height (x).
ii) Write your observations and comments about the fit of the model. Suggest the best model that fits the data.

Formulas:
- $b_1 = \frac{n\sum XY - \sum X \sum Y}{n\sum X^2 - (\sum X)^2}$
- $b_0 = \bar{Y} - b_1\bar{X}$

---

## 10. ANOVA (Analysis of Variance)

### Q1 [Oct 2024 EC3M, Q2a - 5M]

Analyze the following data for testing the significant difference between the mileages of 3 branded 2-wheeler motor bikes. And answer the following with justification:

a) State the null hypothesis
b) State the alternate hypothesis
c) Which test can be used in the validation?
d) Is it a parametric or non-parametric test?
e) What is the critical region or criteria with 0.05 level of significance

| Bike Brand | Mileage (in Kms) per liter petrol |
|-----------|----------------------------------|
| Hero | 60, 65, 65, 63, 62 |
| TVS | 70, 75, 78, 56, 52 |
| Bajaj | 85, 77, 65, 53, 82 |

---

## 11. Maximum Likelihood Estimation (MLE)

### Q1 [2022-23 EC3 Regular, Q3b - 5M]

An unfair coin is tossed 50 times and following are the outcomes noted. Is it possible to find Maximum Likelihood estimates? If possible find ML Estimates. If not state the reason and validate.

[DATA IN ORIGINAL]

---

### Q2 [Compre Makeup 2025, Q2b - 4M]

A factory produces electronic components, and each component is independently defective with probability $p$. In a random sample of 10 components, 3 were found to be defective.

(i) Find the maximum likelihood estimate (MLE) of $p$.
(ii) Using the estimated $p$, determine the probability that in the next batch of 5 components, exactly 2 will be defective.

Binomial likelihood: $L(p) = \binom{n}{k} p^k (1-p)^{n-k}$

MLE: $\hat{p} = \frac{k}{n}$

---

## 12. Binomial & Normal Distribution

### Q1 [2022-23 EC3 Makeup, Q4a - 5M]

A random variable X follows binomial distribution with $n = 1000$ and $p = 0.001$. Then find:
i) $P(X > 700)$
ii) $P(X < 300)$
iii) $P(300 < X < 700)$

---

### Q2 [Sept 2024 EC3R, Q1b - 2M]

If the chance of running a bus service according to schedule is 0.75, calculate the probability on a day schedule with 10 services:
(i) exactly one is late
(ii) at least one is late

Binomial: $P(X=k) = \binom{n}{k} p^k (1-p)^{n-k}$

---

## 13. Conditional Probability & Bayes Theorem (Applied)


### Q1 [2022-23 EC3 Regular, Q4a - 5M]

Consider $y = f(x_1, x_2)$ with corresponding probabilities given below and find $P(y = 1 \mid x_1 = 1, x_2 = 0)$.

[PROBABILITY TABLE IN ORIGINAL]

---

### Q2 [2022-23 EC3 Makeup, Q4b - 5M]

Consider the following probabilities. If possible find the following. If not, validate your decision.

| $P(x_1)$ | $P(x_2)$ | $P((x_1, x_2) \mid y=0)$ | $P((x_1, x_2) \mid y=1)$ | $P(x_1=0 \mid x_2=1)$ |
|-----------|-----------|---------------------------|---------------------------|------------------------|

[VALUES IN ORIGINAL]

---

### Q3 [2022-23 EC3 Regular, Q4b - 5M]

A corporate Hospital wants to name their hospital with specialization like XYZ Centre for cancer care / XYZ Centre for Cardiac care / XYZ Centre for Orthocare by considering the following data. Suggest a suitable name by using a relevant statistical tool/procedure. Justify it.

[DATA TABLE IN ORIGINAL]

---

## 14. Linear Trend & Least Squares

### Q1 [2023-24 EC3 Makeup, Q6a - 7M]

For the following data on sales, fit a linear trend by the method of least squares. Forecast the sales for the year 2025.

| Year | 1995 | 2000 | 2005 | 2010 | 2015 | 2020 |
|------|------|------|------|------|------|------|
| Sales ('000) | 16 | 20 | 18 | 15 | 18 | 21 |

Method of least squares:
- $Y = a + bX$
- $b = \frac{n\sum XY - \sum X \sum Y}{n\sum X^2 - (\sum X)^2}$
- $a = \bar{Y} - b\bar{X}$

---

## 15. Correlation Coefficient Interpretation & Pre-processing

### Q1 [2023-24 EC3 Regular, Q6b - 3M]

i) What is the conclusion if the coefficient of correlation is zero?

ii) Given correlations:
- $r(Y, X_1) = 0.85$ (strong positive)
- $r(Y, X_2) = 0.60$ (moderate positive)
- $r(Y, X_3) = 0.10$ (weak)
- $r(X_1, X_2) = 0.95$ (very high - multicollinearity!)
- $r(X_1, X_3) = 0.30$ (low)

How to proceed with pre-processing before fitting linear regression model? Discuss and validate actions.

**Key insight:** $X_1$ and $X_2$ are highly correlated (0.95) indicating multicollinearity. One of them should be dropped. Since $r(Y, X_1) > r(Y, X_2)$, retain $X_1$ and drop $X_2$. Also $X_3$ has very low correlation with Y (0.10), so it may be dropped.

---

## 16. Model Comparison (Regression Models)

### Q1 [Sept 2024 EC3R, Q4b - 3M]

Three teams propose prediction models:

| Team | Model | Accuracy |
|------|-------|----------|
| A | Multiple linear regression (SSE loss) | 80% |
| B | Polynomial regression (SSE) | 90% |
| C | Multiple regression using gradient descent | 85% |

Write observations on each model. Select best model for prediction. Justify.

**Considerations:**
- Team B (90%) highest accuracy but check for overfitting
- Polynomial may overfit if degree too high
- Gradient descent vs closed-form solution tradeoffs
- Need to check validation performance, not just training

---
