# Credit Risk Modeling
Building Base II, Base III compliant credit risk models in Python (PD, LGD, EAD)

### Expected Loss (EL)
Lenders know that there is credit risk associated with EVERY borrower, therefore a key metric when modeling credit risk is to acccount for Expected Loss (EL). 
Factors of EL:
* Borrower Specific Factors
* Economic Enviroment

### Estimating EL
EL can be estimated by calculating the multiplicative product of PD x LGD x EAD 
* PD (probability of default): likelihood the borrower will be unable to repay their debt in time
* LGD (loss given default): the proportion of the total exposure which cannot be recovered by the lender once a default has occured
* EAD (exposure at default): the total value that a lender is exposed to when a borrower defaults


Capital Adequacy: the porpotion of assets a bank must have available in order to secure losses from the possibility of a large number of defaults ... the capital held must be greater than or equal to x% of risk-weighted assets... capital adequacy ratio (CAR)

Basel II Accord: to ensure that the capital allocation carried out by the bank is risk sensitive.. 3 pillars that can be chosen for calculating or modeling the components of EL
* Minimum Capital Requirements
  * Credit Risk: standardized approach (SA), or Internal Ratings Based Approached (IRB)
  * Operational Risk: 
  * Market Risk
* Supervisory Review
* Market Discipline
