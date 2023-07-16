# OLS
- Simple linear regression y = beta1*x1+b1, adding feature x2, get bivariate regression y = beta1*x1 + beta2*x2 + b2, how would the variance of beta1 change?
  
- Here is the regression: y=1+x1+x2. If x1 and x2 are correlated, we just want to measure the impact of x2 on y, how should we do?
  - **Solution:** first regress x2 on x1 get the residual, and regress y on x1 and residual
  
- OLS with y ~ x1 + x2, the goodness of fit is very good, but the significance for the regression coefficient of both x1 and x2 are not good. What could be the cause and how to deal with it? (Pont72)
  
- OLS with y ~ x, how does high autocorrelation affect the coefficients for x and how does it affect the t statistics? (Point72)

- 

- If the regression coefficient b of y \~bx equals to 1, what's the range of the regression coefficient c of x\~cy? (Squarepoint)
  
- How to do weighted lasso regression? (2sigma)
  
- x1 and x2 are uncorrelated and having zero mean. We calculate the regression coefficients y-x1 ~ b'2 * x2 and y-x2 ~ b'1 * x1. Also we calculate the regression coefficients using the regular way y ~ b1 * x1 and y ~ b2 * x2. How are the coefficients (b1, b2) related to the coefficients (b'1, b'2)? (2sigma)

- Show OLS estimate is MLE under certain assumptions
  
- OLS is BLUE assumtions
   - Guassian- Markov

-

# Ridge and Lasso
- What are the Bayesian interpretation of Ridge and Lesso regression?
  
- How to use a blackbox that can do vanilla regression to do Ridge regression?
    - Adding a random unit noise with $\sqrt \lambda $
    - (http://madrury.github.io/jekyll/update/statistics/2017/08/12/noisy-regression.html)

- In ridge regression, if m copies of a variable x are included, what will happen to the coefficient?
  
- What is the solution for ridge regression? If we have perfect co-linearity, what will ridge regression return?
  
- What is the difference between ridge and lasso? When should we use ridge and when should we use lasso? Why?
  
- The bias and variance of ridge and lasso.

- Why does the shrinkage method perform better than OLS?
  
- Do we include the intercept term in ridge/lasso regression? Why?


#  F statistics and T-statistics and Chi-Square
- How do you interpret F statistics?
- How do you interpret T statistics?
- How do you interpret Chi-Square?
- What's p-value
