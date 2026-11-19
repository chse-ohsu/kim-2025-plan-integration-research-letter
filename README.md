### Overview  
This repository contains select code used to classify Medicare/Medicaid plan integration status among dual-eligible individuals, as published in  

Kim H, Senders A, Cheekati M, Edelstein S, Lindner SR, Jung J. Medicare and Medicaid Plan Integration Among Dual-Eligible Individuals. JAMA Netw Open. 2025;8(7):e2522774. doi:10.1001/jamanetworkopen.2025.22774  

Integrated plans are defined as Medicare Advantage (MA) and Medicaid managed care plans owned by the same parent organization. Dual-eligible enrollees in MA have one MA plan but may have several Medicaid plans covering medical (MCO), behavioral health (BHO), and/or long-term services and supports (MLTSS), each of which may be owned by a different parent organization. This code provides the broad steps needed to assign integration status at the enrollee level, including how to:  

- Identify each MA plan's parent organization  
- Identify each Medicaid plan's parent organization  
- For each enrollee, flag MA/Medicaid plan pairs that share a parent and assign an integration category based on which Medicaid plan type is owned by the same parent (e.g., "integrated with MCO," "integrated with MCO + MLTSS," "not integrated")  

### Data availability  
This analysis uses CMS Research Identifiable Files (RIFs) obtained under a Data Use Agreement with CMS. The data cannot be redistributed and are not included in this repository. Researchers may [request RIF access through CMS](https://www.cms.gov/data-research/cms-data/data-available-researchers). The following source files were used in this study:  

- 2021 [Medicare Master Beneficiary Summary File Base A/B/C/D](https://resdac.org/cms-data/files/mbsf-base)  
- 2021 [Medicare Plan Characteristics File](https://resdac.org/cms-data/files/plan-characteristics)  
- 2021 [T-MSIS Analytic File Demographic and Eligibility](https://resdac.org/cms-data/files/taf-de)  
- 2021 CHSE Managed Care Organization Crosswalk (see below)  
- 2021 [SMAC D-SNP Integration Status reports](https://www.cms.gov/medicare/medicaid-coordination/about/dsnps)  
  
###  Scope and intended use
This is not a turnkey pipeline. It is excerpted from a larger analytic workflow and omits data acquisition, cohort construction, cleaning, and validation steps. It assumes the user has already built an analytic file at the enrollee-month-Medicaid plan level (including Medicare plan information). Users will need to adapt any file paths, variable names, and data structures to their own environment.  

### CHSE MCO Crosswalk   
This study used an early version of a publicly available managed care crosswalk published by the Center for Health Systems Effectiveness at Oregon Health & Science University. This repo includes the version used to produce the published estimates; later versions reflect subsequent corrections and updates and will not reproduce results exactly. Interested parties are encouraged to [download the most recent version from GitHub](https://github.com/chse-ohsu/taf.functions/tree/main/Managed_Care_Crosswalks).  
  
### Included scripts 
This repo includes the following scripts:  
  
- select_code_to_identify_integrated_plans.Rmd  
  
  
### Included look-up tables  
This repo includes the following supplementary tables:  

- mco_crosswalk_clean_resarch_letter.csv  
 