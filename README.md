# NFL Analytics 2025: Predictive Modeling & Feature Engineering

Developed a robust predictive framework to estimate Offensive Performance (Points Per Game - PPG) for the 2024-2025 NFL season. 

The project successfully transitioned from raw data ingestion (XLS/CSV) to a refined machine learning pipeline, achieving higher interpretability by mitigating multicollinearity and implementing advanced feature selection.

# Why This Model Matters Beyond the Numbers

The real value of this framework isn't the R-squared , it's the decision framework it enables. By confirming that OSRS and MoV explain scoring variance better than defensive metrics, we're saying something specific to a front office: investing in offensive talent acquisition has a measurably higher expected return than investing in defensive depth, given the current NFL meta. 

That's not an opinion, it's a testable, data-backed hypothesis that can be updated each season as new data comes in. The SVR component adds value for teams with high game-to-game variance (e.g., pass-heavy offenses sensitive to weather or opponent coverage schemes) where OLS assumptions break down.
