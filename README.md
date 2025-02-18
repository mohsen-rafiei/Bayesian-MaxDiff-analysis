# README

This repository contains an example workflow for a Bayesian-enhanced MaxDiff (Best-Worst) analysis in R. The code demonstrates how to:

1. **Generate Synthetic MaxDiff Data**  
   - We simulate user preferences for ten hypothetical designs, with 20 participants each completing 50 trials.  
   - Each trial randomly assigns “best” and “worst” picks based on underlying utilities plus added noise to mimic realistic variation.

2. **Compute Traditional Net Scores**  
   - We calculate how many times each design was chosen as “best” minus how many times it was chosen as “worst.”  
   - This provides a quick, overall snapshot of relative design preferences, visualized with a bar chart.

3. **Fit a Bayesian Model with `brms`**  
   - We use a logistic regression model (`bernoulli` family) to estimate the probability that each design is chosen as “best.”  
   - Random intercepts by participant account for individual differences in overall “best” selection rates.  
   - The model outputs posterior distributions, which let us quantify uncertainty in each design’s probability of being picked as “best.”

4. **Visualize Posterior Estimates**  
   - We plot the marginal effects (predicted probabilities) for each design, with credibility intervals showing how confident we are in those predictions.

## Why This Matters
- **Net Score Bar Chart**: Offers a simple summary of best-minus-worst picks but lacks uncertainty estimates.  
- **Bayesian Model**: Provides richer insights into how certain we are about each design’s relative standing. This is especially useful when dealing with smaller sample sizes or complex, real-world scenarios where individual differences matter.

## Files
- **maxdiff_bayesian_example.R**: The script generating synthetic data, computing net scores, fitting the Bayesian model, and producing two plots.  

## Usage
1. Clone this repository or download the script.  
2. Open the script in R or RStudio.  
3. Install any missing packages (e.g., `tidyverse`, `brms`) by running `install.packages("pkgName")`.  
4. Run the script to generate data, fit the model, and produce the plots.  

## Contributing
Feel free to open issues or submit pull requests if you have suggestions on improving the simulation, modeling approach, or visualizations.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
