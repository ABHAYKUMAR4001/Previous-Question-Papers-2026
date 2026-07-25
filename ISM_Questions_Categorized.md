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
