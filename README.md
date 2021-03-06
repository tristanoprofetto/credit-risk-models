# Credit Risk Modeling
Building Base II, Base III compliant credit risk models in Python (PD, LGD, EAD)

### Data
Consumer loans
All variables are converted to dummy variables

### Expected Loss (EL)
Lenders know that there is credit risk associated with EVERY borrower, therefore a key metric when modeling credit risk is to acccount for Expected Loss (EL). 
Factors of EL:
* Borrower Specific Factors
* Economic Enviroment


### Estimating EL
EL can be estimated by calculating the multiplicative product of PD x LGD x EAD 
* **PD** (probability of default): likelihood the borrower will be unable to repay their debt in time ... modeled by **Logistic Regression**
* **LGD** (loss given default): the proportion of the total exposure which cannot be recovered by the lender once a default has occured ... modeled by **Beta regression**
* **EAD** (exposure at default): the total value that a lender is exposed to when a borrower defaults ... modeled by **Beta regression**


Capital Adequacy: the porpotion of assets a bank must have available in order to secure losses from the possibility of a large number of defaults ... the capital held must be greater than or equal to x% of risk-weighted assets... capital adequacy ratio (CAR)

Basel II Accord: to ensure that the capital allocation carried out by the bank is risk sensitive.. 3 pillars that can be chosen for calculating or modeling the components of EL
* Minimum Capital Requirements
  * Credit Risk: standardized approach (SA), or Internal Ratings Based Approached (IRB)
  * Operational Risk: 
  * Market Risk
* Supervisory Review
* Market Discipline


### Calculating Capital Requirements
Calculations differ by product types, and borrower entities (retail, corporate)
Under SA, the amount that should be held as capital for every retail exposure as apercentage of the total exposure is 75%
* Motgages: 35%
IRB Approaches: allow banks to establish their own credit ratings, make precise calculations about held capital, and allocate resources to cover losses

### Data Preprocessing
Fine-Classing: splitting variables into roughly equal categories according to some internal criterion

Coarse Classing: splitting variables into roughly equal categories according to some external criterion

**Weight of Evidence (WoE)**: shows to what extent an independent variable would predict a dependent variable... indicates how much information a category of an independent variable brings with repect to explaining the dependent variable

**Information Value (IV)**: weighted average of the weights of evidence... shows how much information the original independent variable brings with respect to explaining the dependent variable ... can be used for variable selection of corresponding model predictors, with values ranging between 0-1.



### Model Evaluation

Gini Coefficient: measures the inequality between good and bad borrowers for loans ... measured by plotting the proportion of defaulted borrowers against all borrowers

Kolmogorov-Smirnov: the max difference between the cumulative distribution functions of 'good' and 'bad borrowers with respect to predicted probabilities ... shows to what extent the model truly seperated good borrowers from bad borrowers


### Model Applications

Scorecards: provides credit worthiness assesment based on the probability of default model

Cut-Off Rate: predetermines the total number of borrowers that will be approved and rejected ... impacts the quality of the loans


### Model Maitenance

Assesing population stability: using PSI to determine whether there is a significant change in our data which can cause a drift in our models performance.

PSI: values between 0-1:
* PSI = 0: no difference
* PSI < 0.1: little difference
* 0.1 < PSI < 0.25: different
* PSI > 0.25: big difference
* PSI = 1: absolute difference


When building LGD, EAD models, it is good practice to build models with data from borrowers who have had time to repay part of the remaining debt

Dependant variables in LGD, EAD models:
* Recovery Rate = recoveries / funded amount
* Credit Conversion Factor: proportion of the total exposure at the moment of default
