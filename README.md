# Sampling Distribution Explorer

An interactive web app for exploring how sample statistics vary across repeated samples. Compare exact sampling distributions with simulations, investigate estimator bias, and visualize the Central Limit Theorem.

## Features

- **Exact enumeration:** List all possible ordered samples for small populations and sample sizes, then combine their probabilities to construct the sampling distribution.
- **Simulation:** Generate repeated random samples with adjustable sample size, number of repetitions, and random seed.
- **Six sample statistics:** Explore the mean, total, variance, standard deviation, minimum, and maximum.
- **Custom populations:** Enter population values and probabilities, provide a list of population units, or upload CSV or Excel data.
- **Interactive visualizations:** Compare the population, an individual sample, and the sampling distribution.
- **Bias and variability:** Examine expected values, bias, variance, and standard deviation.
- **Normal approximations:** Overlay a CLT normal curve for the sample mean or total and compare approximate probabilities with exact or simulated results.
- **Probability and quantile calculators:** Adjust cutoffs and probability levels to explore the distribution.
- **Generated R code:** Copy R scripts corresponding to the current settings and calculator results.

## Getting Started

1. Download the HTML file from this repository.
2. Open it in a modern web browser.
3. Choose a preset population or enter your own.
4. Select **Enumeration** or **Simulation**.
5. Choose a statistic and adjust the sample size.
6. Explore the graph, tables, and probability calculations.

No installation, build step, or backend server is required. An internet connection is needed to load KaTeX for mathematical notation and SheetJS when importing Excel files.

## Included Populations

| Preset | Description |
| --- | --- |
| Example 5.21 | Values 80, 100, and 120 with probabilities 0.2, 0.3, and 0.5 |
| Fair die | Values 1 through 6, each equally likely |
| Bernoulli | Values 0 and 1 with probabilities 0.7 and 0.3 |
| Right-skewed | Values 1, 2, 3, and 20 with probabilities 0.4, 0.3, 0.2, and 0.1 |

The Bernoulli preset also demonstrates the sampling distribution of a sample proportion, since the mean of a binary sample is its proportion of ones.

## Example Exploration

To investigate the Central Limit Theorem:

1. Select the right-skewed population.
2. Switch to **Simulation** and select **Sample mean**.
3. Begin with a small sample size.
4. Increase the sample size while comparing the sampling distribution with the normal curve.
5. Observe how the distribution becomes more nearly normal and its spread decreases.

To explore bias, compare the sample variance and sample standard deviation with their corresponding population values.

## Statistical Framework

All samples use independent draws **with replacement**.

For the sample mean:

- E(X̄) = μ
- Var(X̄) = σ² / n
- SD(X̄) = σ / √n

The sample variance uses the **n − 1** denominator and is unbiased for the population variance. The sample standard deviation is generally biased for the population standard deviation.

Enumeration produces exact results, subject to numerical precision. Simulation produces estimates that vary with the random seed and number of repetitions.

## Uploading Data

Supported formats include CSV, TXT, TSV, XLSX, and XLS.

Provide either:

- One column of population units, with each row equally likely.
- Two columns containing population values and their probabilities.

Header rows are skipped, and the app reports which cells were read. Populations may contain up to **50 distinct values**.

## Implementation

- HTML and CSS for the interface
- JavaScript for statistical calculations and interaction
- HTML Canvas for visualizations
- KaTeX for mathematical notation
- SheetJS for Excel imports

Calculations and uploaded data are processed in the browser.

## Limits and Reproducibility

- Exact enumeration supports up to **200,000 ordered samples**.
- Simulation supports **100 to 100,000 repetitions**.
- Reusing the same seed and settings reproduces simulations within the app.
- Generated R simulations will differ because R uses a different random number generator.
