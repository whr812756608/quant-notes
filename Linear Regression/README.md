
----
# Assumptions
1. **Linearity** of the relationship between dependent and independent variables
    - The expected value of dependent variable is a straight-line function of each independent variable, holding the others fixed.
    - The slope of that line does not depend on the values of the other variables.
    - The effects of different independent variables on the expected value of the dependent variable are additive.
3. Random sampling following linear relationship
4. Full Rank or no/little colinearity among x variables
5. Exogeneity of x variables to residuals: Zero condition mean
6. Homoscedasticity residuals
7. Normal distributed residuals

Unbiased use first 4
BLUE use first 5
t-test for beta uses 6th

## Test Assumptions/Violation Effect/Remediation
https://people.duke.edu/~rnau/testing.htm

### Linearity
**Test**
plot
observed vs. predicted
residuals vs. predicted

residuals versus individual independent variables for **multivariate regression**

**Fix**
non-linear transformation to $y$ or $x$ variables


### Multicollinearity
It refers to predictors that are correlated with other predictors in the model.

**Effect**
- increase the variance of the coefficient estimates and make the estimates very sensitive to minor changes in the model.
- the coefficient estimates are unstable and difficult to interpret.
- even can cause the coefficients to switch signs.
- Multicollinearity affects [the coefficients and p-values](https://statisticsbyjim.com/regression/interpret-coefficients-p-values-regression/), but it does not influence the predictions, precision of the predictions, and the goodness-of-fit [statistics](https://statisticsbyjim.com/glossary/statistics/).

1. 原来coefficient代表另外的variables不变，单个variable对y的影响，现在有了correlation，单个variable变，其他variable也变，那单个variable对y影响很难measure
2. 几何理解，构成x空间的variable之间不independent，x平面不唯一，y在x平面投影unstable
3. linear algebra, $X^T X$ maybe singular

**Test**
Variance Inflation Factor (VIF): taking a variable and regressing it against every other variable to get $R^2$ and VIF = $\frac{1}{1- R^2}$

correlation matrix (Pearson correlation)
check eigenvalues

**Fix**
Fix when
1. you care more about how much each individual feature rather than a group of features affects the target variable
2. features/variables you are interested in

Dropping variables should be an iterative process starting with the variable having the largest VIF

### Autocorrelation/Serial Correlation
**Effect**
residual not iid distributed

- OLS estimators of the $\hat{β}$ are still unbiased and consistent but the optimist property (minimum [variance](https://itfeature.com/glossary/variance) property) is not satisfied.
- The OLS estimators will be inefficient and therefore, no longer BLUE.
- The estimated [variance](https://itfeature.com/glossary/variance) of the regression coefficients will be greater than the variances of estimate calculated by other methods. Therefore, hypothesis testing is no longer valid. In most of the cases, $R^2$ will be overestimated (indicating a better fit than the one that truly exists). The **t-** and **F-** statistics will tend to be higher.
- The variance of random term may be under-estimated. (MSE may underestimated compared with true residual variance).

**Test**
Durbin Watson/Breusch-Godfrey test
Ljung-Box Q test
ADF test (time series MA)
residuals vs. independent variables
GLS

**Fix**
include explanatory variables in the model
ARIMA
[Autocorrelation in Regression, an Example from Business](https://rstudio-pubs-static.s3.amazonaws.com/615815_d1ac2dafd5e448a88781ac0ed8d94ad1.html)

[计量经济学精华笔记（二）：异方差和自相关](https://zhuanlan.zhihu.com/p/242140022)

### Heteroscedasticity

**Effect**

-   The OLS estimators and regression predictions based on them remains **unbiased** and consistent, but less precise (variance increase and smaller p-values)
-   The OLS estimators are no longer the BLUE (Best Linear Unbiased Estimators) because they are no longer efficient, so the regression predictions will be inefficient too.
- give too much weight to a small subset of the data (namely the subset where the error variance was largest) when estimating coefficients
-   Because of the inconsistency of the covariance matrix of the estimated regression coefficients, the tests of hypotheses, (t-test, F-test) are no longer valid. OLS calculates the t-values and F-values using an underestimated amount of variance. This problem can lead you to conclude that a model term is statistically significant when it is actually not significant.

**Test**
residuals vs. predicted $\hat{y}$ values
Breusch-Pagan test

**Fix**
1. redefine variables 
2. weighted regression
3. transform variable (standardize, log diff)
4. GLS(General Least Square): **加权最小二乘法**WLS, FGLS
5. **OLS+稳健标准误**：OLS+异方差稳健的标准误

### Normality

**Effect**
Calculation of confidence intervals and various significance tests for coefficients are all based on the assumptions of normally distributed errors. If the error distribution is significantly non-normal, confidence intervals may be too wide or too narrow.

**Test**
Q-Q plot
[Kolmogorov-Smirnov](http://en.wikipedia.org/wiki/Kolmogorov%E2%80%93Smirnov_test) test, the [Shapiro-Wilk](http://en.wikipedia.org/wiki/Shapiro%E2%80%93Wilk_test) test, the [Jarque-Bera](http://en.wikipedia.org/wiki/Jarque%E2%80%93Bera_test) test, and the [Anderson-Darling](http://en.wikipedia.org/wiki/Anderson%E2%80%93Darling_test) test

**Fix**
non-linear transform of variables
check outliers/extreme values (are they valid)

----
# Coefficient Estimation

**Solve for** $X\beta = Y$
- Inverse Matrix $\hat{\beta} = (X^TX)^{-1}X^T Y$
	- variance-covariance $\hat{\beta}=\frac{\sum x y}{\sum x^2}$ using parallel computation
- LU Decomposition: $X\beta = LU\beta = Y \Rightarrow Ux = A, LA = Y$
- SVD Decomposition $X = U \Sigma V^T$  and  $(X^TX)^{-1}X^T = V\Sigma^{-1}U^T$

**Iterative**
Use loss/cost function
Why choose OLS as cost function and why it's optimal (https://www.zhihu.com/question/24095027)

==Newton method to get updated ==

**MLE**
Assume noise is following certain distribution (normal distribution), maximize likelihood function by get first derivative = 0

Residual **heteroskedasticity**  and **autocorrelation** Effect
[计量经济学精华笔记（二）：异方差和自相关](https://zhuanlan.zhihu.com/p/242140022)

[relation between 𝑅2 of simple regression and multiple regression](https://stats.stackexchange.com/questions/155968/relation-between-r2-of-simple-regression-and-multiple-regression)

[回字的四种写法——从线性回归到贝叶斯线性回归](https://zhuanlan.zhihu.com/p/86009986)

[Lasso—原理及最优解](https://zhuanlan.zhihu.com/p/116869931)

----
# R-square
https://statisticsbyjim.com/regression/interpret-r-squared-regression/
https://statisticsbyjim.com/regression/interpret-adjusted-r-squared-predicted-r-squared-regression/

R-squared CANNOT determine whether the coefficient estimates and predictions are biased (use residual plot).

Negative $R^2$
https://stats.stackexchange.com/questions/12900/when-is-r-squared-negative
