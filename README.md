### Estimating Heritability and Genetic Correlations from Large Health Datasets in the Absence of Genetic Data

#### please cite: Jia, G., Li, Y., Zhang, H. et al. Estimating heritability and genetic correlations from large health datasets in the absence of genetic data. Nat Commun 10, 5508 (2019) doi:10.1038/s41467-019-13455-0 
https://www.nature.com/articles/s41467-019-13455-0

We have launched a searchable web application for researchers to explore and compare sex-and-country-stratified prevalence curves for over 500 diseases. https://gjia.shinyapps.io/disease_curves/.

#### 1. Training_Data_H2.csv 

This is the training dataset for the imputation of heritability. Column names are listed below and annotated in parentheses:

Disease (disease name), H2 (published heritability value), H2_se (standard error), Data_type (data type used in heritability estimation: “twin study,” “family study,” “family study using EHRs,” “SNP-based study,” and “PRS-based study”), Math_model_in_reference (math model used in heritability estimation:“AE,” “ACE,” “PRS,” “SOLAR,” “GREML,” and “LDSC”), Country_of_cohort, Gender_of_cohort, F0,..., F65 (disease- and female-specific counts at ages between 0 and 65, based on US data), M0,..., M65 (disease- and male-specific counts at ages between 0 and 65, based on US data), cumF0,..., cumF64 (female-specific cumulative counts, a sum of all normalized counts from age 0 till the age N), cumM0,...,cumM64 (male-specific cumulative counts, a sum of all normalized counts from age 0 till the age N), Median (Median age of disease carriers), C1,...,C20 (real-valued elements in the 20-dimensional embedding vector), System (general system that the disease belongs to), Gender (applicable gender), MtoF (male-to-female ratio in carriers), MeanPrev (mean prevalence), F_US_cluster (cluster label of US- and female-specific curve), F_Denmark_cluster (cluster label of Denmark- and female-specific curve), M_Denmark_cluster (cluster label of Denmark- and male-specific curve), M_US_cluster (cluster label of US- and male-specific curve), Onset (disease onset age, computed based on Denmark data)
   
  
#### 2. Training_Data_Corr.csv

This is the training dataset for the imputation of correlation. Column names are listed below and annotated in parentheses:

Disease1, Disease2, corr (published correlation value), corr_SD (standard error), Correlation_type_in_reference (genetic, environmental, or phenotypic correlation), Data_type_in_reference (“twin study,” “family study,” “family study using EHRs,” “SNP-based study,” and “PRS-based study”), Math_model_in_reference (“AE,” “ACE,” “PRS,” “SOLAR,” “GREML,” and “LDSC”), Country_of_cohort, Gender_of_cohort, distMe (euclidean distance between male-specific curves of the disease pair) ,distFe (euclidean distance between female-specific curves of the disease pair),distPCe (euclidean distance between embeding vectors of the disease pair),distMcos (cosine distance between male-specific curves of the disease pair), distFcos (cosine distance between female-specific curves of the disease pair),distPCcos (cosine distance between embeding vectors of the disease pair), MtoF (male-to-female ratio in carriers), MPrev (mean prevalence), Onset_diff (onset age difference), Onset_mean (mean onset age), F_US_cluster_agree (cluster labels of US- and female-specific curves are the same for the disease pair? True or False), F_Denmark_cluster_agree, M_Denmark_cluster_agree, M_US_cluster_agree, Cdiff1, Cmean1,..., Cdiff20, Cmean20 (mean and difference values of embedding elements of the disease pair), Fdiff0, Fmean0, Mdiff0, Mmean0, cumMdiff0, cumFdiff0,..., Fdiff65, Fmean65, Mdiff65, Mmean65, cumMdiff65, cumFdiff65 (gender-specific mean and difference values of the normalized counts and cumulative counts, based on US data),CNS (one of the disease pair is in central nervous system? True or False), Cardiovascular, Digestive, Endocrine, Hematologic, Hepatic, Immune, Integumentary, Metabolic, Musculoskeletal, Neoplastic_Process, Non-Specific, Reproductive, Urinary, SameSystem (the disease pair belong to the same general system? True or False), SexMale (the disease pair are specific to male only? True or False), SexVariablesMatch (the applicable genders of the disease pair are the same? True or False)


#### 3. H2_test_performance.ipynb 

This is the notebook that reads in Training_Data_H2.csv, compares various modeling algorithms for heritability imputation, and thus generates the results shown in Table 1.


#### 4. Corr_test_performance.ipynb 

This is the notebook that reads in Training_Data_Corr.csv, compares various modeling algorithms for correlation imputation, and thus generates the results shown in Table 1.


