# LIFESIGHT-Assessment


Marketing Mix Model for Revenue Analysis
This project presents a single-stage Marketing Mix Model (MMM) built to explain and predict revenue based on various marketing and business drivers.

#1. Data Preparation
Data was prepared to handle key time-series challenges:

Adstock Transformation: A decay rate of 0.5 was applied to paid media spend to capture the long-term impact of advertising.

Diminishing Returns: A logarithmic transformation was applied to adstock features to reflect that initial marketing spend has a greater impact than subsequent spend.

Seasonality & Trend: Sine and cosine features were created for weekly seasonality, and a linear trend feature was added for long-term growth.

Scaling: All features were standardized to ensure they contribute equally to the model.

2. Modeling Approach
Model Choice: Ridge Regression was chosen for its effectiveness in handling correlated features and preventing overfitting. The L2 regularization in Ridge Regression helps to stabilize the model's coefficients.

Validation: Time-Series Cross-Validation with 5 folds was used to provide a robust performance estimate and avoid look-ahead bias.

3. Causal Framing & Diagnostics
Initial analysis of the Google spend as a mediator hypothesis revealed a negative out-of-sample R 
2
 , suggesting this assumption was not supported by the data. As a result, the final model was built as a single-stage regression to directly model the relationship between all channels and revenue, demonstrating a strategic and data-driven approach.

The final model's diagnostics confirm its reliability:

Performance: The model achieved an average out-of-sample R-squared (R 
2
 ) of 0.88, and the residual plot showed a random distribution, indicating a strong fit.

Risks: The model acknowledges the risk of collinearity between marketing channels, which is mitigated by Ridge Regression.

4. Key Insights
High Impact Drivers: Google Ads spend and overall trend were the most significant positive drivers of revenue.

Price Sensitivity: The negative coefficient for average_price indicates that as price increases, revenue tends to decrease, confirming price elasticity.

