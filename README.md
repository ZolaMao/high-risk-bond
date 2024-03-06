# high-risk-bond
import numpy as np

# Define parameters
initial_investment = 1000  # Initial investment amount
interest_rate = 0.1  # Annual interest rate
years = 5  # Number of years to simulate
num_simulations = 1000  # Number of simulations

# Simulate high-risk bonds
results = []
for _ in range(num_simulations):
    investment = initial_investment
    for _ in range(years):
        # Generate a random return rate (normally distributed)
        return_rate = np.random.normal(interest_rate, 0.05)
        investment *= (1 + return_rate)
    results.append(investment)

# Calculate statistics
mean_investment = np.mean(results)
median_investment = np.median(results)
std_dev_investment = np.std(results)
min_investment = np.min(results)
max_investment = np.max(results)

# Print results
print("Simulation Results for High-Risk Bonds:")
print("Mean Investment after {} years: {:.2f}".format(years, mean_investment))
print("Median Investment after {} years: {:.2f}".format(years, median_investment))
print("Standard Deviation of Investment after {} years: {:.2f}".format(years, std_dev_investment))
print("Minimum Investment after {} years: {:.2f}".format(years, min_investment))
print("Maximum Investment after {} years: {:.2f}".format(years, max_investment))
