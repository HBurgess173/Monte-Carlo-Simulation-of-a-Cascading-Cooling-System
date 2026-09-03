# Annotated Literature Review

## Background and Engineering Context

**Ahmad, T. (2026) Cascading Risk and Systemic Decision Failure: How Local Problems Become Systemic Crises - Sustainable. Sustainable Catalyst | Ethical Systems for Sustainable Strategy [online]. Available from: https://sustainablecatalyst.com/cascading-risk-and-systemic-decision-failure/ [Accessed 25 April 2026].**

This source was used to support the background explanation of cascading risk. Although it is not specific to cooling systems, it helped explain the wider principle that a local issue in one part of a connected system can propagate downstream and create a larger system-level problem. This was relevant to the project because HVAC load is passed to CW, and total CW load is passed to FW, meaning uncertainty in upstream loads can affect downstream subsystem risk.

---

**Stephanie (2016) Deterministic: Definition and Examples. Statistics How To [online]. Available from: https://www.statisticshowto.com/deterministic/ [Accessed 25 April 2026].**

This source was used as a simple background reference for defining deterministic assessment. It supported the explanation that a deterministic calculation produces a fixed result rather than a range of possible outcomes. This was useful for introducing the limitation of a pass/fail cooling load assessment before explaining why a probabilistic simulation approach was required.

---

**United Nations (2024) United Nations sustainable development goals (SDGs). United Nations Western Europe [online]. Available from: https://unric.org/en/united-nations-sustainable-development-goals/ [Accessed 30 August 2026].**

This source was used to support the ethical and sustainability discussion in the report. It was particularly relevant to UN SDG 6.4, which relates to water-use efficiency, and SDG 12.5, which relates to reducing waste through prevention and reduction. This helped connect the engineering problem to the wider sustainability issue of avoiding unnecessary system overcapacity while still managing overload risk.

---

## Monte Carlo Simulation and Cooling-System Risk

**Cheng, Q., Wang, S. and Yan, C. (2017) Sequential Monte Carlo simulation for robust optimal design of cooling water system with quantified uncertainty and reliability. Energy [online]. 118, pp. 489–501. [Accessed 20 August 2026].**

This was one of the most relevant sources for the project. The paper uses Monte Carlo simulation in the context of cooling-water-system design and considers uncertainty, reliability and unmet cooling load. It was useful because it showed that probabilistic methods can provide information beyond deterministic sizing, particularly where cooling demand and available capacity are uncertain. The paper did not provide a directly comparable overload probability to the 9.225% result in this project, but it supported the principle of using Monte Carlo simulation to assess cooling-system adequacy.

---

**Fan, C., Liao, Y., Zhou, G., Zhou, X. and Ding, Y. (2020) Improving cooling load prediction reliability for HVAC system using Monte-Carlo simulation to deal with uncertainties in input variables. Energy and Buildings [online]. 226, p. 110372.**

This paper was useful because it applies Monte Carlo simulation to HVAC cooling-load prediction uncertainty. It supported the argument that predicted cooling loads should not be treated as exact values, because uncertainty in input variables can affect the reliability of the final cooling-load estimate. This aligned closely with the project aim of moving from a fixed deterministic calculation to a simulation-based assessment of possible load outcomes.

---

**Gang, W., Wang, S. and Shan, K. (2015) Article Impacts of Cooling Load Calculation Uncertainties on the Design Optimization of Building Cooling Systems. ResearchGate [online]. [Accessed 25 April 2026].**

This source was used to support the discussion that uncertainty in cooling-load calculation can affect design decisions. It was relevant because the project investigated whether deterministic cooling loads could hide risk once uncertainty margins were applied. The paper also supported the wider engineering motivation that cooling-system sizing should account for uncertainty, rather than relying only on nominal load values.

---

**Kim, Y.-J., Ahn, K.-U. and Park, C.-S. (2014) Decision making of HVAC system using Bayesian Markov chain Monte Carlo method. Energy and Buildings [online]. 72, pp. 112–121. [Accessed 20 August 2026].**

This paper was useful as an example of probabilistic decision-making in HVAC systems. Although the method used in the paper was Bayesian Markov chain Monte Carlo rather than the direct Monte Carlo framework used in this project, it supported the idea that uncertainty should be included in HVAC system assessment. It also helped justify why probabilistic outputs can provide more useful decision support than a single deterministic result.

---

**Li, C.-Z., Shi, Y.-M., Liu, S., Zheng, Z. and Liu, Y. (2010) Uncertain programming of building cooling heating and power (BCHP) system based on Monte-Carlo method. Energy and Buildings [online]. 42 (9), pp. 1369–1375. [Accessed 20 August 2026].**

This paper was useful because it treats energy demands as uncertain rather than fixed. It supported the project’s use of Monte Carlo simulation to generate possible demand values and assess system behaviour under uncertainty. The paper was also relevant to the dependency modelling discussion because it recognises that cooling, heating and power demands may be uncertain and related, although it was not used as the main reference for Gaussian copula modelling.

---

**Huang, P., Wang, Y., Huang, G. and Augenbroe, G. (2015) Investigation of the ageing effect on chiller plant maximum cooling capacity using Bayesian Markov Chain Monte Carlo method. Journal of Building Performance Simulation [online]. 9 (5), pp. 529–541. [Accessed 20 August 2026].**

This paper was relevant because it considers uncertainty in chiller plant cooling capacity rather than only uncertainty in cooling load. It was useful for understanding that both demand and capacity can vary in real systems. In this project, subsystem capacities were treated as fixed, so this source helped identify a limitation and possible future work: extending the framework to consider uncertain or reduced cooling capacities.

---

**A contamination analysis of the primary coolant system with Monte Carlo simulations.**

This source was reviewed as an example of Monte Carlo simulation being used in a coolant-system context. It was less directly applicable to the project because it focused on contamination analysis rather than cooling-load exceedance or subsystem capacity risk. However, it provided background evidence that Monte Carlo simulation is used in engineering systems where uncertainty and repeated sampling are important.

---

## Uncertainty Modelling and Simulation Size

**Burkardt, J. (2014) The truncated normal distribution. Department of scientific computing website, Florida State University, 1(35), pp.58. [online]. [Accessed 16 February 2026].**

This source was used to support the truncated normal distribution used in the uncertainty model. It was useful because it explains how a normal distribution can be bounded so that sampled values remain within a defined range. This was directly relevant to the project because load values needed to remain physically meaningful and within the uncertainty bounds defined by the workbook margins.

---

**Roy, T. and Gupta, H. (2021) How certain are our uncertainty bounds? Accounting for sample variability in Monte Carlo-based uncertainty estimates. Environmental Modelling & Software [online]. 136, p. 104931. [Accessed 20 August 2026].**

This paper was used to support the importance of sample size and uncertainty around Monte Carlo estimates. It was relevant to the verification and convergence stage of the project, where the most constrained case was rerun with increasing simulation sizes. The paper helped justify why convergence checking is important when using Monte Carlo outputs such as high-percentile estimates.

---

**Cassettari, L., Mosca, R. and Revetria, R. (2012) Monte Carlo Simulation Models Evolving in Replicated Runs: A Methodology to Choose the Optimal Experimental Sample Size. Mathematical Problems in Engineering [online]. 2012 (1). [Accessed 21 August 2026].**

This paper was useful for understanding the relationship between Monte Carlo sample size, repeated runs and stability of simulation outputs. It supported the choice to assess convergence rather than simply assume that 100,000 simulations was sufficient. This was relevant to the verification stage, where the stability of overload probability and P99 load-to-capacity ratio was checked.

---

**Kissell, R. and Poserina, J. (2017) Advanced Math and Statistics. Optimal Sports Math, Statistics, and Fantasy [online]. pp. 103–135. [Accessed 16 February 2026].**

This source was used for general statistical background. It was less central to the cooling-system engineering argument, but it helped support the use of statistical measures and interpretation of probability-based outputs. It was mainly relevant as a supporting reference rather than a core methodological source.

---

## Dependency Modelling

**Joe, H. (2015) Dependence modeling with copulas. 2015.**

This was an important source for the dependency modelling section. It provided background on copulas as a method for modelling dependency between variables while preserving their individual marginal distributions. This was directly relevant because the project used Gaussian copula dependency modelling to allow sampled loads to vary together while retaining the truncated normal distribution for each load item.

---

**Masarotto, G. and Varin, C. (2017) Gaussian Copula Regression in R. Journal of Statistical Software [online]. 77 (8). [Accessed 21 August 2026].**

This paper was used as a direct reference for Gaussian copula modelling. It was useful because it explains how Gaussian copulas can model dependency separately from marginal distributions. This supported the project’s approach of using truncated normal distributions for individual load items while introducing dependency through a latent Gaussian structure. The source was also useful for acknowledging that Gaussian copulas are transparent and practical, but do not represent tail dependence as strongly as alternatives such as t-copulas.

---

**Slater, D. (2013) Dependency Modelling for Dummies? Research Gate.**

This source was used as a supporting reference for understanding dependency modelling in practical terms. It helped frame why independent sampling may be too simple where loads are affected by shared operating conditions. It was not used as the main mathematical reference for Gaussian copulas, but it supported the wider explanation that dependency assumptions can influence risk results.

---

**Bayesian model.**

This paper was reviewed because it discussed Bayesian model updating and the use of Gaussian copula methods in an engineering uncertainty context. It was useful as supporting literature for the idea that copulas can be used to model dependency structures in engineering systems. However, it was not used as the main project reference because the project did not perform Bayesian updating or estimate dependency from measured data.

---

## Sensitivity Analysis and Design of Experiments

**Derrick, B. (2020) Statistical inference with paired observations and independent observations in two samples. Applied Statistics Group, Engineering Design and Mathematics, Faculty of Environment and Technology, University of the West of England, Bristol. [Accessed 13 June 2026].**

This source was reviewed because it provided examples of clear statistical notation and simulation parameter tables. It was particularly useful for deciding how to present simulation methodology in the report, including notation and parameter summaries. Although the statistical problem in the paper was different from this project, the structure helped inform how the Monte Carlo parameters were documented.

---

**Gunst, R.F. and Mason, R.L. (2009) Fractional factorial design. Wiley Interdisciplinary Reviews: Computational Statistics [online]. 1 (2), pp. 234–244. [Accessed 16 February 2026].**

This source was used to support the fractional factorial Design of Experiments screen used in the sensitivity analysis. It was relevant because the project did not use DoE to estimate overload probabilities directly, but to compare the influence of modelling assumptions and interactions. The source helped justify using a reduced factorial structure to screen key factors without testing every possible full-factorial combination.

---

**James, G., Witten, D., Hastie, T. and Tibshirani, R. (2013) An Introduction to Statistical Learning: with Applications in R. Springer.**

This textbook was used to support the statistical learning methods applied in the sensitivity analysis. It was relevant for explaining regression-based interpretation and the role of model inputs in predicting an outcome. In this project, logistic regression was used only where overload and non-overload examples were both available, while correlation-based methods were used where overload events were not present.

---

**Rumsey, D.J. (2007) Intermediate statistics for dummies. Hoboken, N.J.: Wiley.**

This source was used as a basic statistical reference for correlation and interpretation of statistical measures. It was less academically strong than the main journal papers and textbooks, but it was useful for supporting simple explanations of statistical concepts. Where possible, stronger academic references should be preferred in the main report.

---

## Data, Ethics and Governance

**Anonymization_Techniques_for_Privacy_Preserving_Data_Publishing_A_Comprehensive_Survey.**

This paper was reviewed to support consideration of data privacy and anonymisation. It was less directly relevant because the project did not use personal data and the cooling-load values were simulated. However, it helped confirm that data sensitivity and disclosure risk should still be considered when publishing project artefacts.

---

**HBurgess173 (2026) GitHub - HBurgess173/Monte-Carlo-Simulation-of-a-Cascading-Cooling-System: This repository serves as the portfolio for my MSc Data Science final project, “Monte Carlo Simulation of a Cascading Cooling System.” GitHub [online]. Available from: https://github.com/HBurgess173/Monte-Carlo-Simulation-of-a-Cascading-Cooling-System/tree/main [Accessed 21 August 2026].**

The GitHub repository was used as the project artefact and source of reproducible analysis. It contains the notebooks, input data, generated outputs, figures and documentation. This was relevant to project governance because it allowed the analysis to be organised by stage and provided evidence of how each project aim was addressed.

---

## Software and Implementation References

**Python (2019) Python v3.12.4. Python.org [online]. Available from: https://www.python.org/downloads/ [Accessed 1 September 2026].**

Python was the main programming language used to develop the simulation artefact. It supported data processing, uncertainty modelling, Monte Carlo simulation, dependency modelling, sensitivity analysis and verification. This reference was included to document the software environment used to produce the results.

---

**jupyter (2019) Project Jupyter. Jupyter.org [online]. Available from: https://jupyter.org/ [Accessed 2 September 2026].**

Jupyter was used to organise the artefact into notebooks. This was useful because each notebook could combine code, outputs, figures and explanatory text in one place. It also helped present the project as a staged workflow from data ingestion through to results and verification.

---

**Pandas (2018) Python Data Analysis Library. Pydata.org [online]. Available from: https://pandas.pydata.org/ [Accessed 2 September 2026].**

Pandas was used for data loading, cleaning, transformation and tabular output. It was particularly important for reading the workbook data, preparing scenario-specific load tables and exporting intermediate results. This supported the reproducibility of the artefact.

---

**Numpy (2024) NumPy. Numpy.org [online]. Available from: https://numpy.org/ [Accessed 2 September 2026].**

NumPy was used for numerical calculations, array handling and efficient simulation operations. It was particularly relevant to the Monte Carlo stages, where large numbers of sampled values were generated and processed.

---

**SciPy (2020) SciPy.org. Scipy.org [online]. Available from: https://scipy.org/ [Accessed 2 September 2026].**

SciPy was used for statistical functions, including truncated normal sampling. It was directly relevant to the uncertainty modelling stage because the project required bounded random sampling around nominal load values.

---

**Scikit-learn (2026) scikit-learn: machine learning in Python — scikit-learn 1.9.0 documentation - sklearn. Sklearn.org [online]. Available from: https://sklearn.org/stable/index.html [Accessed 2 September 2026].**

Scikit-learn was used for the logistic regression element of the sensitivity analysis. It supported the identification of influential consumers in cases where both overload and non-overload simulation outcomes were available.

---

**Matplotlib (2024) Matplotlib: Python Plotting — Matplotlib 3.1.1 Documentation. Matplotlib.org [online]. Available from: https://matplotlib.org/ [Accessed 2 September 2026].**

Matplotlib was used to generate figures for the notebooks and report. It supported visual communication of deterministic results, Monte Carlo outputs, dependency effects, sensitivity analysis and convergence checks.

---

**seaborn (2012) seaborn: statistical data visualization — seaborn 0.9.0 documentation. Pydata.org [online]. Available from: https://seaborn.pydata.org/ [Accessed 2 September 2026].**

Seaborn was used to improve the clarity and consistency of statistical figures. It helped create readable plots for comparing subsystem loads, uncertainty cases and dependency modelling results.

---

**Clark, C. (2024) openpyxl - A Python library to read/write Excel 2010 xlsx/xlsm files — openpyxl 3.0.3 documentation. openpyxl.readthedocs.io [online]. Available from: https://openpyxl.readthedocs.io/en/stable/ [Accessed 2 September 2026].**

Openpyxl was used as part of the Excel reading and writing workflow through Python. This was relevant because the original dataset was provided as an Excel workbook and several project outputs were also exported in spreadsheet format.

---

**OpenAI (2026). ChatGPT. ChatGPT response to [see AI usage list] (Personal Communication, 31 August).**

Generative AI was used as a support tool during the project. It assisted with code debugging, limited code development, report structure, writing clarity and checking the artefact against the marking criteria. Final decisions, analysis, interpretation of results and submitted work remained the responsibility of the author.

---
