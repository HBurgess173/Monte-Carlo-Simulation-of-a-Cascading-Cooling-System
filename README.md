# Probabilistic Reliability Assessment of a Cascaded Cooling System Using Monte Carlo Simulation

## Project Overview

This repository contains the code, analysis, and supporting documentation for an MSc Data Science final project investigating the probabilistic reliability of a cascaded cooling system. The project uses a cooling-load dataset representing a three-stage cooling chain with two defined operating states. The three systems considered in the cooling chain are System H, System C, and System F.

Traditional engineering assessment of cooling systems is often based on deterministic heat-load estimates. Under this approach, predicted loads are treated as fixed values and compared directly against available system capacity. Although this provides a clear pass/fail assessment, it does not account for uncertainty in predicted consumer loads, operational variability, modelling assumptions, or incomplete knowledge of system behaviour. This can lead to over-confidence in available cooling margins, particularly in cascaded systems where uncertainty may propagate downstream.

The aim of this project is to develop a reproducible probabilistic reliability assessment framework that uses Monte Carlo simulation to propagate heat-load uncertainty through a cascaded cooling architecture. The framework estimates the probability of subsystem overload and consumer-level margin exceedance under two operating states. Alternative uncertainty distributions and dependency assumptions are compared to assess how modelling choices influence estimated overload risk.

The final output is a structured data science workflow that supports risk-based assessment of cooling-system adequacy, moving beyond a binary deterministic pass/fail calculation.

---

## Research Aim

The aim of this project is to develop and evaluate a Monte Carlo simulation framework for assessing the reliability of a cascaded cooling system under uncertain consumer heat loads.

The project reframes cooling-load assessment as a probabilistic reliability problem by estimating:

* the probability of subsystem cooling capacity exceedance;
* the probability of individual consumers exceeding permissible load margins;
* the effect of uncertainty propagation through the cooling chain;
* the sensitivity of overload risk to distributional and dependency assumptions.

---

## System Description

The cooling system is represented as a cascaded architecture consisting of three interconnected systems:

```text
System H → System C → System F
```

Each system serves a set of local consumers. Downstream systems are affected by both their own local consumer loads and the propagated load from upstream systems. As a result, uncertainty in upstream heat loads can influence downstream system reliability.

The dataset contains two operating states. These operating states allow the reliability of the cooling chain to be assessed under different loading conditions. System capacities and consumer loads are compared separately for each operating state.

---

## Methodology Summary

The project follows a structured data science workflow.

### 1. Data Ingestion and Exploratory Data Analysis

The provided cooling-load dataset is loaded, inspected, and assessed for quality. Exploratory Data Analysis is used to understand the dataset structure, consumer load characteristics, uncertainty values, margin values, and subsystem capacity constraints.

The EDA stage includes checks for:

* dataset shape and column structure;
* missing values;
* duplicate records;
* consumer counts by subsystem;
* load distributions by subsystem;
* comparison between operating states;
* uncertainty and margin characteristics;
* nominal load versus available capacity.

### 2. Deterministic Baseline Assessment

A deterministic baseline is calculated to represent the conventional engineering assessment method. In this stage, nominal consumer loads are summed and propagated through the cooling chain. The resulting subsystem loads are compared against available cooling capacity to determine deterministic pass/fail outcomes.

This baseline provides a reference point for interpreting the probabilistic Monte Carlo results.

### 3. Uncertainty Modelling

Uncertainty in predicted consumer heat loads is represented using parametric probability distributions. Two uncertainty models are compared:

* triangular distribution;
* truncated normal distribution.

These distributions are used to model uncertainty around nominal consumer load values while enforcing physically meaningful load bounds.

### 4. Monte Carlo Simulation

Monte Carlo simulation is used to repeatedly sample uncertain consumer loads and propagate them through the cascaded system. For each simulation iteration, the framework calculates subsystem loads for System H, System C, and System F, then records whether each subsystem exceeds its available capacity.

Consumer-level exceedance events are also recorded by comparing sampled consumer loads against permissible maximum loads.

### 5. Dependency Modelling

Alternative dependency assumptions are compared to assess the influence of correlated consumer demand. The project considers independent sampling as a baseline and compares this against correlated demand assumptions.

Dependency modelling is included because real engineering loads are unlikely to vary fully independently. Consumers may increase or decrease together depending on operating conditions, subsystem behaviour, or common demand drivers.

### 6. Sensitivity Analysis

Sensitivity analysis is used to identify which consumers and modelling assumptions have the greatest influence on overload risk. This provides interpretability and supports the data science contribution of the project.

Planned sensitivity methods include:

* consumer risk ranking;
* Spearman rank correlation;
* logistic regression for overload classification;
* scenario comparison across uncertainty and dependency assumptions;
* optional screening analysis for dominant load contributors.

### 7. Verification and Convergence Testing

Because the project does not use measured operational outcomes for validation, model evaluation focuses on internal verification, convergence, and robustness testing.

Verification checks are used to confirm that:

* load propagation through the cascade is implemented correctly;
* failure logic is applied consistently;
* sampled loads remain physically meaningful;
* zero-uncertainty cases reproduce deterministic results;
* overload probabilities behave sensibly under high-capacity and low-capacity test cases.

Monte Carlo convergence testing is used to assess the stability of estimated overload probabilities as the number of simulation iterations increases.

---

## Repository Structure

```text
msc-cooling-monte-carlo/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── example/
│
├── notebooks/
│   ├── 01_project_overview.ipynb
│   ├── 02_data_ingestion_and_eda.ipynb
│   ├── 03_deterministic_baseline.ipynb
│   ├── 04_uncertainty_modelling.ipynb
│   ├── 05_monte_carlo_simulation.ipynb
│   ├── 06_dependency_modelling.ipynb
│   ├── 07_sensitivity_analysis.ipynb
│   ├── 08_verification_and_convergence.ipynb
│   └── 09_results_and_discussion.ipynb
│
├── src/
│   └── cooling_mc/
│       ├── data_loader.py
│       ├── data_validation.py
│       ├── eda.py
│       ├── distributions.py
│       ├── copula.py
│       ├── cascade_model.py
│       ├── simulation.py
│       ├── metrics.py
│       ├── sensitivity.py
│       └── visualisation.py
│
├── outputs/
│   ├── figures/
│   ├── tables/
│   └── logs/
│
└── report/
    ├── methodology_notes.md
    ├── results_summary.md
    └── limitations.md
```

---

## Notebook Guide

The project analysis is organised into a sequence of notebooks.

| Notebook                                                                                 | Description                                                                           |
| ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| [01_project_overview.ipynb](notebooks/01_project_overview.ipynb)                         | Introduces the project aim, system architecture, research questions, and methodology. |
| [02_data_ingestion_and_eda.ipynb](notebooks/02_data_ingestion_and_eda.ipynb)             | Loads the cooling-load dataset and performs exploratory data analysis.                |
| [03_deterministic_baseline.ipynb](notebooks/03_deterministic_baseline.ipynb)             | Calculates nominal subsystem loads and deterministic pass/fail results.               |
| [04_uncertainty_modelling.ipynb](notebooks/04_uncertainty_modelling.ipynb)               | Defines triangular and truncated normal uncertainty models.                           |
| [05_monte_carlo_simulation.ipynb](notebooks/05_monte_carlo_simulation.ipynb)             | Runs the core Monte Carlo simulation and calculates reliability metrics.              |
| [06_dependency_modelling.ipynb](notebooks/06_dependency_modelling.ipynb)                 | Compares independent and correlated consumer demand assumptions.                      |
| [07_sensitivity_analysis.ipynb](notebooks/07_sensitivity_analysis.ipynb)                 | Identifies consumers and assumptions that most influence overload risk.               |
| [08_verification_and_convergence.ipynb](notebooks/08_verification_and_convergence.ipynb) | Performs model verification, robustness checks, and convergence testing.              |
| [09_results_and_discussion.ipynb](notebooks/09_results_and_discussion.ipynb)             | Summarises key findings, limitations, and interpretation of results.                  |

---

## Key Outputs

The project produces the following outputs:

* deterministic subsystem load and capacity comparison tables;
* Monte Carlo overload probability estimates;
* consumer-level margin exceedance probabilities;
* load percentile summaries;
* scenario comparison tables;
* sensitivity rankings;
* convergence plots;
* verification test results;
* final visualisations for academic reporting.
