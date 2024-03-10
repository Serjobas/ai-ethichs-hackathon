# Harry Potter Influenced Loan Approval Dataset Analysis

## Overview

This project explores biases in machine learning models through a Harry Potter themed dataset on loan approvals. The goal is to identify biases in the dataset, re-evaluate models from technical and socio-technical perspectives, and implement mitigation strategies.

## Technical Approach

### Data Preparation and Exploration

- **Libraries Used**: Pandas, Matplotlib, Seaborn, Scikit-learn, Imblearn
- **Data Cleaning**: Converted target variable [gringotts_approved_loan](file:///Users/sergeybunas/Develop/ai-ethics-hackathon/AI_Ethics_Hackathon_Skeleton.ipynb#26%2C5-26%2C5) to numeric. Identified and imputed missing values, particularly in [hours_per_week](file:///Users/sergeybunas/Develop/ai-ethics-hackathon/AI_Ethics_Hackathon_Skeleton.ipynb#70%2C46-70%2C46).
- **Exploratory Data Analysis (EDA)**: Conducted to understand data distribution, missing values, and potential biases. Utilized descriptive statistics, box plots, and count plots to visualize the data.

### Bias Identification

- **Potentially Harmful Biases**: Identified based on features like [education](file:///Users/sergeybunas/Develop/ai-ethics-hackathon/AI_Ethics_Hackathon_Skeleton.ipynb#32%2C29-32%2C29), [marital_status](file:///Users/sergeybunas/Develop/ai-ethics-hackathon/AI_Ethics_Hackathon_Skeleton.ipynb#32%2C39-32%2C39), [occupation](file:///Users/sergeybunas/Develop/ai-ethics-hackathon/AI_Ethics_Hackathon_Skeleton.ipynb#172%2C5-172%2C5), [bloodline](file:///Users/sergeybunas/Develop/ai-ethics-hackathon/AI_Ethics_Hackathon_Skeleton.ipynb#133%2C18-133%2C18), and [gender](file:///Users/sergeybunas/Develop/ai-ethics-hackathon/AI_Ethics_Hackathon_Skeleton.ipynb#146%2C18-146%2C18). These features could lead to biases in loan approval decisions.
- **Statistical Tests**: Chi-square tests and Cramer's V analysis were performed to statistically confirm the presence of biases.

### Bias Mitigation Strategies

- **Feature Engineering**: Dropped features ([bloodline](file:///Users/sergeybunas/Develop/ai-ethics-hackathon/AI_Ethics_Hackathon_Skeleton.ipynb#133%2C18-133%2C18), [gender](file:///Users/sergeybunas/Develop/ai-ethics-hackathon/AI_Ethics_Hackathon_Skeleton.ipynb#146%2C18-146%2C18)) to mitigate direct biases.
- **SMOTE**: Employed Synthetic Minority Over-sampling Technique to address class imbalance.
- **Random Forest Model**: Trained with a focus on fairness, utilizing an imbalanced-learn pipeline.

## Socio-Technical Reflection

### Reflective Report on Socio-Technical Implications

- **Technical Limitations**: Acknowledged that not all bias problems can be solved technically, emphasizing the need for socio-technical approaches.
- **Decision-Making Systems**: Discussed the appropriateness of AI in various decision-making contexts, advocating for human oversight in sensitive areas.
- **Fairness and Justice**: Highlighted the importance of addressing underlying societal inequalities alongside technical fixes to ensure fairness and justice in AI applications.

### Mitigation Strategy Implementation

- **Fairlearn Analysis**: Utilized Fairlearn to assess model performance across different groups, revealing insights into the model's fairness.
- **Feature Importance Analysis**: Identified and visualized the top 10 features influencing loan approval decisions, providing insights into the model's decision-making process.

## Computational Results

- **Model Performance**: Evaluated using cross-validation and test set accuracy. The Random Forest model showed promising results, with accuracy scores indicating a balance between performance and fairness.
- **Fairness Metrics**: Employed Fairlearn's MetricFrame to analyze model performance across sensitive features, ensuring a comprehensive understanding of the model's fairness.
