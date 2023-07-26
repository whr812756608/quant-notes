- linear regression, Y = beta1*X, X = beta2*Y , what is the relationship between beta1, beta2 if X, Y are centered? what is the relationship between beta1, beta2 if X, Y are not centered?
- How to sample from a normal distribution with a correlation of rho with a given random variable X

def generate_correlated_normal(X, rho):
    Z = np.random.normal(0, 1, len(X))
    Y = rho * X + np.sqrt(1 - rho**2) * Z
    return Y
