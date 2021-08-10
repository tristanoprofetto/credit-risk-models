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
IRB Approaches: allow banks to establish their own credit ratings, make precise calcullaation about held capital, and allocate resources to cover losses

### Data Preprocessing
Fine-Classing: splitting variables into roughly equal categories according to some internal criterion

Coarse Classing: splitting variables into roughly equal categories according to some external criterion

**Weight of Evidence (WoE)**: shows to what extent an independent variable would predict a dependent variable... indicates how much information a category of an independent variable brings with repect to explaining the dependent variable

**Information Value (IV)**: weighted average of the weights of evidence... shows how much information the original independent variable brings with respect to explaining the dependent variable ... can be used for variable selection of corresponding model predictors, with values ranging between 0-1.
