# Loan Charge-Off Classification with Linear Programming

We explored how linear programming can separate loans by their recorded charge-off status. We formulated the classification problem as a linear program in PuLP, then used dual multipliers and visualizations to examine observations near regions where the classes overlap.

## Model

- Define a separating hyperplane using six input variables, including loan amount, FICO score, and debt-to-income ratio (DTI).
- Add two nonnegative deviation variables per observation. The objective penalizes deviations on the wrong side of the boundary and rewards separation on the correct side with a smaller weight.
- Normalize the hyperplane coefficients, solve the linear program with PuLP, and inspect the dual multipliers associated with the observation constraints.

## What the analysis shows

The FICO–DTI scatter plots show substantial overlap between loans with and without a recorded charge-off. We highlight observations with positive dual multipliers to examine which constraints are sensitive in the fitted model. The plots visualize two of the six inputs.

The notebook explores the model and its fitted constraints on the supplied data. Out-of-sample classification performance remains unmeasured.

## Run the notebook

Place the course-provided `p2pdata.xlsx` next to the notebook. It should contain the `charged_off` target and the six numeric input columns used in the code. The input workbook is excluded from the repository.

```bash
python -m pip install -r requirements.txt
jupyter notebook "Loan Charge-Off Classification with Linear Programming.ipynb"
```

The [original notebook](Loan%20Charge-Off%20Classification%20with%20Linear%20Programming.ipynb) includes the mathematical formulation, implementation, and saved plots.
