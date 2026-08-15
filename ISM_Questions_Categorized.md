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

Manufacturer of product 'A' claims average life = 120 months, variance = 25 months. Sample of 10: mean=125, SD=4. Validate at 1% significance.

### Q2 [2022-23 EC3 Makeup, Q1b - 5M]

Player A vs Player B in IPL. Both played 18 matches. A: avg=85, SD=9. B: avg=75, SD=2. Validate claim "A is better" at 1% significance.

### Q3 [2022-23 EC3 Regular, Q1a - 5M]

Product 'A' average life follows normal distribution. Claim: average >= 120 months, variance=25. Sample of 10: mean=125, SD=4. Validate at 5% significance.

### Q4 [2023-24 EC3 Makeup, Q2 - 7M]

Product A vs Product B. Sample of 20 each. A: mean=12 months, SD=15 days. B: mean=10 months, SD=10 days. Use p-value.

Pooled SD: $s = \sqrt{\frac{(n_1-1)S_1^2 + (n_2-1)S_2^2}{n_1+n_2-2}} = \sqrt{\frac{19 \times 15^2 + 19 \times 10^2}{38}} = 12.74$

$t = \frac{\bar{x_1} - \bar{x_2}}{s\sqrt{\frac{1}{n_1} + \frac{1}{n_2}}} = \frac{12-10}{12.74\sqrt{\frac{1}{20}+\frac{1}{20}}} = 0.496$

$P = P(t_{38df} > 0.496) = 0.3113 > 0.05$ → Fail to reject $H_0$

### Q5 [2023-24 EC3 Regular, Q3 - 7M]

30 milk cartons: sample mean=505ml, population SD=10ml, population mean=500ml. Test at 0.05 significance.

$H_0: \mu = 500$ vs $H_a: \mu \neq 500$

$z = \frac{505 - 500}{10/\sqrt{30}} = 2.74$

Critical value $z_{\alpha/2} = 1.96$. Since $2.74 > 1.96$ → Reject $H_0$

p-value = $2 \times P(z > 2.74) = 2 \times 0.0031 = 0.0062 < 0.05$ → Reject

### Q6 [Sept 2024 EC3R, Q2b - 5M]

Machine A vs Machine B:

| Machine | Sample size | Mean | SD |
|---------|-------------|------|-----|
| A | 15 | 5.5 | 0.5 |
| B | 15 | 5.1 | 0.2 |

Conclude if Machine A is superior to B.

### Q7 [Oct 2024 EC3M, Q1 - 5M]

Food delivery claims avg time <= 10 min. Sample of 8: 12, 9, 11, 10, 8, 14, 7, 13 minutes. Test at 5% significance.

### Q8 [Compre Makeup 2025, Q1a - 4M]

Two moulding processes:

| Process-1 (Hrs) | Process-2 (Hrs) |
|-----------------|-----------------|
| 2 | 3 |
| 4 | 7 |
| 9 | 5 |
| 3 | 8 |
| 2 | 4 |
| --- | 3 |

Test with 0.05 significance for significant difference.

---

## 2. Chi-Square Test (Goodness of Fit & Independence)

### Q1 [2023-24 EC3 Regular, Q2 - 7M]

NHAI quality check automation:

| | Correctly identified | Incorrectly identified |
|---|---|---|
| Manual check | 200 | 220 |
| Automated check | 300 | 280 |
| **Total** | **500** | **500** |

Formulate hypothesis, validate at 1% significance.

$E = \frac{\text{Row total} \times \text{Column total}}{N}$, $\chi^2 = \sum\frac{(O-E)^2}{E}$

Calculated $\chi^2 = 1.642$. Critical at 1%, df=1: 6.635. Since $1.642 < 6.635$ → Fail to reject.

### Q2 [2022-23 EC3 Makeup, Q2a - 4M]

Before pandemic: 200/750 online. After: 350/800 online. Validate at 5% significance.

### Q3 [Sept 2024 EC3R, Q2a - 5M]

Student preferences:

| Program | Students |
|---------|----------|
| B.E(CSE) | 320 |
| B.E(AIML) | 240 |
| B.E(DSE) | 350 |
| B.E(Cyber Security) | 200 |
| B.E(IoT) | 90 |
| **Total** | **1200** |

No preference among programs? ($\alpha = 0.05$, df=4)

### Q4 [Compre Makeup 2025, Q3b - 4M]

Faculty claims equal distribution: Sports(55), Music(45), Art(60), Drama(40), Total=200.

Expected each = 50. df = 3. Test at 5%.

$\chi^2 = \frac{(55-50)^2}{50} + \frac{(45-50)^2}{50} + \frac{(60-50)^2}{50} + \frac{(40-50)^2}{50} = 5.0$

Critical $\chi^2_{0.05, 3} = 7.815$. Since $5.0 < 7.815$ → Fail to reject.

### Q5 [Oct 2024 EC3M, Q2b - 5M]

Players' performance (One Day vs IPL):

| Player | One Day | IPL |
|--------|---------|-----|
| A | 1000 | 200 |
| B | 800 | 700 |
| C | 600 | 500 |
| D | 900 | 400 |
| E | 200 | 600 |

Check association at 1% significance.

---

## 3. Proportion Tests

### Q1 [2022-23 EC3 Regular, Q2a - 3M]

Drug claimed 75% effective. 380/500 found effective. Validate at 1%.

### Q2 [2023-24 EC3 Makeup, Q3a - 3M]

$P = 0.4$, $n = 200$. Find $P(0.40 \leq \hat{p} \leq 0.45)$.

$\sigma_{\hat{p}} = \sqrt{\frac{0.4 \times 0.6}{200}} = 0.03464$

$P(0 \leq Z \leq 1.44) = 0.4251$

---

## 4. Confidence Intervals

### Q1 [2023-24 EC3 Makeup, Q3b - 3M]

11 circuits: mean=2.00 ohms, population SD=0.35. Find 99% CI.

$$2 \pm 2.58\left(\frac{0.35}{\sqrt{11}}\right) = 2 \pm 0.2723$$
$$\boxed{1.7277 < \mu < 2.2723}$$

### Q2 [2023-24 EC3 Regular, Q6a - 3M]

11 circuits: mean=2.20 ohms, population SD=0.35. Find 95% CI.

### Q3 [Compre Makeup 2025, Q3a - 4M]

15 students, project times (hours): 76, 85, 90, 78, 83, 88, 91, 75, 84, 79, 87, 92, 80, 86, 89.

Population SD unknown → use t-distribution. 98% CI.

$\bar{x} = 84.2$, $s = 5.52$, $t_{0.01, 14} = 2.624$

CI: $84.2 \pm 2.624 \times \frac{5.52}{\sqrt{15}} = (80.46, 87.94)$

---

## 5. Probability & Joint Distributions

### Q1 [2023-24 EC3 Makeup, Q1 - 7M]

$f(x, y) = \frac{c(x+y)}{2}$, $0 < x < 2$, $0 < y < 3$

i) Find c   ii) Marginal PDFs of X, Y   iii) $P(X<1, Y<2)$   iv) Independent?

### Q2 [2023-24 EC3 Regular, Q1 - 7M]

Joint probability table:

| X \ Y | -1 | -2 | 3 |
|--------|-----|-----|-----|
| 0 | k | 2k | 2k |
| 1 | 2k | k | k |
| 2 | k | 2k | k |
| 3 | 3k | 3k | k |

i) k value   ii) Marginals   iii) $P(X<2, Y<-3)$   iv) $P(X<2|Y<-3)$   v) Independent?

### Q3 [Sept 2024 EC3R, Q1c - 5M]

$f(x,y) = \frac{x+y}{3}$, $0<x<2$, $0<y<1$

i) $P(X>Y)$   ii) Marginal of X   iii) Marginal of Y   iv) Independent?

### Q4 [Sept 2024 EC3R, Q1a - 3M]

50% retirement plan, 60% health insurance, 49% both.
(a) $P(\text{health}|\text{retirement})$?   (b) $P(\text{retirement}|\text{health})$?   (c) $P(\text{no health}|\text{retirement})$?

### Q5 [Sept 2024 EC3R, Q1b - 2M]

Bus on schedule prob=0.75, 10 services: (i) exactly one late (ii) at least one late.

$P(X=k) = \binom{n}{k}p^k(1-p)^{n-k}$

---

## 6. Time Series - Moving Averages

### Q1 [2023-24 EC3 Regular, Q4 - 7M]

Wheat production (tons):

| Year | 2011 | 2012 | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 |
|------|------|------|------|------|------|------|------|------|------|------|
| Production | 86 | 63 | 45 | 58 | 43 | 57 | 98 | 100 | 120 | 150 |

Calculate 3-year MA. Find MSE and MAD.

### Q2 [Sept 2024 EC3R, Q3b - 5M]

Sales (crores):

| Year | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 | 2022 |
|------|------|------|------|------|------|------|------|------|------|
| Sales | 12 | 16 | 20 | 15 | 16 | 17 | 21 | 18 | 19 |

Fit 3-year and 5-year MA. Compare using error function.

### Q3 [Compre Makeup 2025, Q2a - 4M]

Production (tons): 76, 83, 89, 96, 103, 117, 126, 137, 141, 150 (2011-2020).

Calculate 4-year **centered** moving average. Find MSE and MAD.

### Q4 [Oct 2024 EC3M, Q3b - 10M]

Same sales data (2014-2022): 12, 16, 20, 15, 16, 17, 21, 18, 19.
i) Fit exponential smoothing (if possible, else state reasons)
ii) Fit suitable moving average
iii) Compare and conclude

---

## 7. Time Series - Exponential Smoothing

### Q1 [2023-24 EC3 Makeup, Q4 - 7M]

Monthly deflection data (12 months):

| Month | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|-------|-----|------|-----|-----|-----|-----|------|------|-----|------|------|-----|
| Deflection | -213 | -564 | -35 | -15 | 141 | 115 | -420 | -360 | 203 | -338 | -431 | 194 |

Find exponential smoothing for $\alpha=0.4$ and $\alpha=0.6$. Which gives better smoothing?

$F_{t+1} = \alpha Y_t + (1-\alpha)F_t$

Compare MSE: $\alpha=0.4$ gives MSE=106487.90, $\alpha=0.6$ gives MSE=122501.90.

**Better: $\alpha=0.4$** (lower MSE)

### Q2 [2023-24 EC3 Regular, Q5 - 6M]

Traffic fatalities (hundreds):

| Month | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|-------|---|---|---|---|---|---|---|---|---|----|----|-----|
| Fatalities | 28 | 30 | 28 | 28 | 27 | 24 | 23 | 26 | 21 | 27 | 22 | 35 |

Smoothing factor=0.6. Forecast for 13th month.

### Q3 [Sept 2024 EC3R, Q3a - 5M]

Monthly sales (Lakhs):

| Month | Jan | Feb | Mar | Apr | May |
|-------|-----|-----|-----|-----|-----|
| Sales | 50 | 52 | 54 | 55 | 57 |

Forecast Jan=50. Fit with $\alpha=0.10$ and $\alpha=0.70$. Choose best. Forecast June.

---

## 8. Autocorrelation

### Q1 [2023-24 EC3 Makeup, Q5 - 6M]

Cargo exports ($Y_t$):

| Year | 2011 | 2012 | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 |
|------|------|------|------|------|------|------|------|------|------|------|
| Exports | 1230 | 1345 | 1382 | 1416 | 1593 | 1802 | 1817 | 1995 | 2212 | 2607 |

Find autocorrelation at lag 1. Mean=1739.9, Variance=1720145.

$r_1 = \frac{\text{Autocovariance}(1)}{\text{Variance}} = \frac{116813.69}{1720145} = 0.0679$

### Q2 [Compre Makeup 2025, Q4a - 4M]

Monthly sales ('000s): 50, 55, 53, 60, 58. Compute autocorrelation at lag 2. Interpret.

Mean $\bar{X} = 55.2$

---

## 9. Linear Regression & Correlation

### Q1 [2023-24 EC3 Makeup, Q6a - 7M]

Sales data - fit linear trend by least squares. Forecast 2025.

| Year | 1995 | 2000 | 2005 | 2010 | 2015 | 2020 |
|------|------|------|------|------|------|------|
| Sales ('000) | 16 | 20 | 18 | 15 | 18 | 21 |

$Y = a + bX$, $b = \frac{n\sum XY - \sum X \sum Y}{n\sum X^2 - (\sum X)^2}$

### Q2 [Sept 2024 EC3R, Q4a - 7M]

| X | 10 | 12 | 15 | 13 | 11 | 19 |
|---|----|----|----|----|----|----|
| Y | 20 | 22 | 25 | 18 | 17 | 22 |

i) Covariance interpretation   ii) Correlation coefficient   iii) Inference

### Q3 [Oct 2024 EC3M, Q4 - 10M]

| X | 12 | 10 | 13 | 10 | 9 | 14 |
|---|----|----|----|----|---|-----|
| Y | 15 | 20 | 22 | 13 | 12 | 18 |

i) Check linear relation statistically   ii) Find linear relation using SSE   iii) Predict y at x=20

### Q4 [Compre Makeup 2025, Q1b - 4M]

Working hours vs productivity:

| X | 5 | 6 | 4 | 7 | 8 | 5.5 |
|---|---|---|---|---|---|-----|
| Y | 15 | 18 | 12 | 20 | 23 | 16 |

i) Pearson correlation coefficient   ii) Does increasing hours improve productivity?

### Q5 [Compre Makeup 2025, Q4b - 4M]

Height(x) vs Weight(y) for 10 students:

| x | 85 | 94 | 101 | 50 | 88 | 88 | 61 | 68 | 94 | 74 |
|---|----|----|-----|----|----|----|----|----|----|-----|
| y | 61 | 75 | 97 | 85 | 68 | 44 | 79 | 59 | 98 | 73 |

i) Fit linear regression   ii) Comment on fit, suggest best model

### Q6 [2023-24 EC3 Regular, Q6b - 3M]

Correlations: $r(Y,X_1)=0.85$, $r(Y,X_2)=0.60$, $r(Y,X_3)=0.10$, $r(X_1,X_2)=0.95$, $r(X_1,X_3)=0.30$

i) Conclusion if correlation = 0?   ii) Pre-processing before linear regression? (Drop $X_2$ due to multicollinearity with $X_1$)

---

## 10. ANOVA

### Q1 [Oct 2024 EC3M, Q2a - 5M]

Mileage comparison of 3 bike brands:

| Brand | Mileage (Km/L) |
|-------|----------------|
| Hero | 60, 65, 65, 63, 62 |
| TVS | 70, 75, 78, 56, 52 |
| Bajaj | 85, 77, 65, 53, 82 |

a) Null hypothesis   b) Alternate hypothesis   c) Which test?   d) Parametric or non-parametric?   e) Critical region at 0.05

---

## 11. Maximum Likelihood Estimation

### Q1 [Compre Makeup 2025, Q2b - 4M]

Factory: each component defective with probability $p$. Sample of 10, 3 defective.

i) MLE of $p$: $\hat{p} = \frac{k}{n} = \frac{3}{10} = 0.3$

ii) $P(X=2)$ in next batch of 5: $\binom{5}{2}(0.3)^2(0.7)^3 = 10 \times 0.09 \times 0.343 = 0.3087$

---

## 12. Binomial Distribution

### Q1 [2022-23 EC3 Makeup, Q4a - 5M]

$X \sim \text{Binomial}(n=1000, p=0.001)$. Find: i) $P(X>700)$   ii) $P(X<300)$   iii) $P(300<X<700)$

### Q2 [Sept 2024 EC3R, Q1b - 2M]

Bus schedule prob=0.75, 10 services: (i) exactly one late (ii) at least one late

---

## 13. Conditional Probability & Bayes (Applied)

### Q1 [2022-23 EC3 Regular, Q4a - 5M]

$y = f(x_1, x_2)$ with probability table. Find $P(y=1 | x_1=1, x_2=0)$.

### Q2 [2022-23 EC3 Regular, Q4b - 5M]

Hospital naming based on patient data. Suggest specialization using statistical tool.

---

## 14. Model Comparison

### Q1 [Sept 2024 EC3R, Q4b - 3M]

| Team | Model | Accuracy |
|------|-------|----------|
| A | Multiple linear regression (SSE) | 80% |
| B | Polynomial regression (SSE) | 90% |
| C | Multiple regression (gradient descent) | 85% |

Select best model. Consider overfitting risk, validation performance, computational cost.

---



---

**Additional Papers Covered (from ISM Final Part 1.1.pdf & Part 2.pdf):**
- S1 2025-26 EC3 Makeup - March 2026 (40 marks)
- S1 2025-26 EC3 Makeup - Sept 2025 (40 marks)
- S1 2025-26 EC3 Regular (40 marks)


> **Note:** Questions involving diagrams/figures are marked with [DIAGRAM IN ORIGINAL].

---

## 1. Hypothesis Testing (t-test, Z-test)

### Q9 [S1 2025-26 EC3 Makeup March, Q1a - 3M]

An organization evaluates two training programs for improving employee productivity:
- Program A: 20 employees, mean productivity score = 81, standard deviation = 9
- Program B: 25 employees, mean productivity score = 77, standard deviation = 8

At the 5% level of significance, test whether Program A leads to significantly higher productivity.

### Q10 [S1 2025-26 EC3 Makeup March, Q5 - 5M]

A manufacturing company states that the average weight of packets filled by an automated machine is 500 grams. A random sample of 81 packets drawn from a large production lot has a mean weight of 496 grams. From past quality-control records, the population standard deviation of packet weights is known to be 18 grams. At the 5% level of significance, test whether the machine is underfilling the packets.

### Q11 [S1 2025-26 EC3 Makeup Sept, Q2a - 4M]

A school introduces a new teaching method. The average score of 30 students taught with this method is 72, while the average score of 20 students taught with the traditional method is 68. Standard deviations are 8 and 7 respectively. Test at 5% level if the new method is significantly better.

### Q12 [S1 2025-26 EC3 Regular, Q1b - 3M]

A pharmaceutical company claims that their new drug reduces blood pressure by an average of 15 mmHg. A sample of 25 patients shows an average reduction of 13 mmHg with a standard deviation of 5 mmHg. Test the claim at 5% significance level.

### Q13 [S1 2025-26 EC3 Regular, Q5a - 5M]

A manufacturing company produces precision shafts. Two machining methods are used:
- Method A: sample of 10 shafts, sample standard deviation = 0.032 mm
- Method B: sample of 14 shafts, sample standard deviation = 0.028 mm

At the 5% level of significance, is there sufficient evidence to conclude that Method A has greater variability than Method B? (F-test)

---

## 2. Chi-Square Test (Goodness of Fit & Independence)

### Q6 [S1 2025-26 EC3 Makeup March, Q2 - 5M]

A company wants to know whether device type influences purchase decision:

| Device | Purchased | Not Purchased | Total |
|--------|-----------|---------------|-------|
| Mobile | 80 | 120 | 200 |
| Laptop | 70 | 50 | 120 |
| Tablet | 50 | 30 | 80 |
| **Total** | **200** | **200** | **400** |

Use a chi-square test to determine whether device type and purchase decision are independent ($\alpha = 0.05$).

### Q7 [S1 2025-26 EC3 Makeup Sept, Q3a - 4M]

A set of 300 single-digit numbers (0 through 9) is drawn from a random number table. The observed frequencies of each digit are recorded as follows:

| Digit | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|-------|---|---|---|---|---|---|---|---|---|---|
| Frequency | 28 | 29 | 33 | 31 | 26 | 35 | 32 | 30 | 31 | 25 |

Use a Chi-Square goodness-of-fit test at the 5% level of significance to test the hypothesis that the digits are uniformly distributed.

---

## 4. Confidence Intervals

### Q4 [S1 2025-26 EC3 Makeup March, Q1b - 2M]

A company produces light bulbs with an average lifespan of 1000 hrs and a standard deviation of 50 hrs. A random sample of 40 bulbs is selected and their average lifespan is found to be 990 hrs. Calculate a 99% Confidence interval for the population mean lifespan.

### Q5 [S1 2025-26 EC3 Makeup Sept, Q4a - 4M]

A university wants to estimate the proportion of students who own a laptop. Out of a random sample of 300 students, 240 report owning a laptop.

i) Construct a 99% confidence interval for the population proportion.
ii) Interpret the result in terms of the student population.

---

## 6. Time Series - Moving Averages

### Q5 [S1 2025-26 EC3 Makeup March, Q3 - 5M]

The annual production (in thousand units) of a factory from 2017 to 2024 is given below:

| Year | 2017 | 2018 | 2019 | 2020 | 2021 | 2022 | 2023 | 2024 |
|------|------|------|------|------|------|------|------|------|
| Production | 42 | 46 | 39 | 35 | 37 | 44 | 51 | 58 |

Compute a 3-year moving average and use it to forecast production for 2025.

### Q6 [S1 2025-26 EC3 Makeup Sept, Q3b - 4M]

The sale (in hundreds quintal) of products in a regulated agricultural market from 2016-2023:

| Year | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 | 2022 | 2023 |
|------|------|------|------|------|------|------|------|------|
| Sale | 23 | 26 | 19 | 16 | 14 | 28 | 34 | 45 |

Find three-year moving average to forecast the sale for the year 2024.

---

## 7. Time Series - Exponential Smoothing

### Q4 [S1 2025-26 EC3 Regular, Q2 - 8M]

The following data relates to the export of rice (in thousands of quintals) to USA from 2015 to 2021:

| Year | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 |
|------|------|------|------|------|------|------|------|
| Export | 146 | 159 | 161 | 170 | 174 | 140 | 145 |

Using Simple Exponential Smoothing:
i) Forecast the export for 2022 using $\alpha = 0.3$, assuming initial forecast for 2015 equals actual value. [3M]
ii) Forecast the export for 2022 using $\alpha = 0.6$, with same initial condition. [3M]
iii) Determine which smoothing constant provides better forecast based on MSE. [2M]

---

## 8. Autocorrelation

### Q3 [S1 2025-26 EC3 Makeup March, Q4 - 5M]

An IoT system records the daily average temperature (°C) of a server room over 10 days:

| Day | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|-----|------|------|------|------|------|------|------|------|------|------|
| Temp | 22.5 | 22.8 | 22.6 | 22.9 | 23.1 | 23.4 | 23.7 | 23.9 | 24.1 | 24.3 |

a) Compute the lag-1 autocorrelation coefficient.
b) Comment on whether the temperature series exhibits persistence.

### Q4 [S1 2025-26 EC3 Makeup Sept, Q4b - 4M]

A mobile app's analytics team is analyzing average session duration per user (in minutes) over 12 consecutive days to detect persistence in user engagement:

| Day | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|-----|------|------|------|------|------|------|------|------|------|------|------|------|
| Duration | 12.5 | 13.0 | 12.8 | 13.4 | 13.7 | 13.5 | 14.1 | 14.4 | 14.2 | 14.8 | 15.0 | 14.9 |

Compute the lag-1 autocorrelation coefficient for the dataset.

---

## 9. Linear Regression & Correlation

### Q7 [S1 2025-26 EC3 Makeup March, Q7 - 5M]

A dataset measures daily screen time and productivity score:

| Screen Time (hrs) | 1 | 2 | 3 | 4 | 5 | 6 |
|-------------------|---|---|---|---|---|---|
| Productivity | 90 | 85 | 78 | 72 | 65 | 60 |

a) Fit a simple regression model.
b) Interpret direction of relationship.
c) Predict productivity when screen time = 3.5 hrs.

### Q8 [S1 2025-26 EC3 Makeup Sept, Q1 - 8M]

The cost of manufacturing a lot of a certain product depends on the lot size, as shown by the following sample data:

| Lot Size | 5 | 10 | 25 | 50 | 100 | 250 | 500 | 1000 |
|----------|---|----|----|----|----|-----|-----|------|
| Cost ($) | 30 | 70 | 140 | 270 | 530 | 1010 | 2500 | 5020 |

i) Find the Covariance
ii) Find the sample correlation coefficient
iii) Interpret the results

### Q9 [S1 2025-26 EC3 Makeup Sept, Q2b - 4M]

The following data pertain to the growth of a colony of bacteria in a culture medium:

| Days since inoculation (x) | 3 | 6 | 9 | 12 | 15 | 18 |
|----------------------------|---|---|---|----|----|-----|
| Count (y) | 45,000 | 147,000 | 239,000 | 356,000 | 579,000 | 864,000 |

i) Fit a suitable regression equation (exponential: $y = ae^{bx}$) for the given data.
ii) Use the result to estimate the bacteria count at the end of 20 days.

### Q10 [S1 2025-26 EC3 Regular, Q1a - 5M]

The following sample data shows scores (out of 20) of 5 students in Mathematics (X) and Statistics (Y). Calculate Karl Pearson's coefficient of correlation and interpret your result.

| Student | Mathematics | Statistics |
|---------|-------------|------------|
| Ram | 12 | 15 |
| Sham | 8 | 10 |
| Rupa | 16 | 18 |
| Anil | 6 | 9 |
| Sunil | 14 | 16 |

### Q11 [S1 2025-26 EC3 Regular, Q3 - 8M]

A Chemical company studies the effect of extraction time on extraction efficiency:

| Extraction time (min) X | 27 | 45 | 41 | 19 | 35 | 39 | 19 | 49 | 15 | 31 |
|--------------------------|----|----|----|----|----|----|----|----|----|----|
| Extraction efficiency (%) Y | 57 | 64 | 80 | 46 | 62 | 72 | 52 | 77 | 57 | 68 |

i) Fit a straight line by the method of least squares. [5M]
ii) Predict the extraction efficiency when extraction time is 35 minutes. [1M]
iii) Draw a scatter plot for the given data. [2M]

---

## 10. ANOVA

### Q2 [S1 2025-26 EC3 Makeup March, Q8 - 5M]

A researcher wants to test whether three different teaching methods lead to different average test scores:

| Method 1 | Method 2 | Method 3 |
|----------|----------|----------|
| 15 | 18 | 22 |
| 17 | 16 | 24 |
| 16 | 20 | 23 |
| 14 | 19 | 21 |

At the 5% level of significance, test using one-way ANOVA whether there is any significant difference in the mean scores of the three teaching methods.

### Q3 [S1 2025-26 EC3 Makeup Sept, Q5 - 8M]

A company wants to compare the productivity levels of employees under three different work schedules: morning shift, evening shift, and flexible hours. The data collected:

| Morning Shift | Evening Shift | Flexible Hours |
|---------------|---------------|----------------|
| 5 | 5 | 5.6 |
| 3 | 5 | 5.8 |
| 5 | 5.7 | 5.5 |
| 5 | 5.9 | — |
| — | — | — |

Conduct a one-way ANOVA test to determine whether there is a significant difference in the average productivity levels. State null and alternate hypotheses. Verify at 5% level.

---

## 11. Maximum Likelihood Estimation

### Q2 [S1 2025-26 EC3 Regular, Q5b - 3M]

In a particular city, the number of car accidents per day follows a Poisson distribution. On five randomly chosen days, the number of accidents recorded was 4, 2, 5, 3, and 6.

i) Find the maximum likelihood estimate (MLE) of the average number of accidents per day.
ii) Estimate the probability that there will be no accidents on a randomly chosen day.

---

## 15. Holt's Double Exponential Smoothing

### Q1 [S1 2025-26 EC3 Makeup March, Q6 - 5M]

A small online grocery store tracks the weekly demand (in units) for a popular product. The demand shows a steady upward trend, but no seasonal pattern:

| Week | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|------|---|---|---|---|---|---|---|
| Demand | 20 | 22 | 24 | 26 | 28 | 30 | 32 |

Parameters: Level smoothing constant $\alpha = 0.4$, Trend smoothing constant $\beta = 0.3$, Initial level $L_1 = 20$, Initial trend $T_1 = 2$.

a) Compute the smoothed level ($L_t$) and smoothed trend ($T_t$) for weeks 2 to 7.
b) Using the values obtained at week 7, compute the forecast for week 8.
c) Briefly explain why Holt's method is more suitable than simple exponential smoothing for this data.

### Q2 [S1 2025-26 EC3 Regular, Q4 - 8M]

A start-up offers streaming service and is experiencing steady growth in monthly paid subscriptions. The last six months' data:

| Month | Jan | Feb | Mar | Apr | May | Jun |
|-------|-----|-----|-----|-----|-----|-----|
| Subscriptions ('000) | 15 | 18 | 22 | 25 | 29 | 33 |

The company wants to forecast July subscriptions using Holt's method. Parameters: $\alpha = 0.5$, $\beta = 0.3$, Initial level $L_0 = 15$, Initial trend $T_0 = 3$.

a) Apply Holt's smoothing step-by-step to forecast for July. [6M]
b) Briefly explain why trend smoothing ($\beta$) is critical for subscription growth forecasting. [2M]

---
