# RESPECTEx
Reconstituting Specific Cell-type Expression

Written by Joseph Ng, October 2018

RESPECTEx takes as input:
1. tumour bulk gene expression data, 
2. estimates of tumour purity of the tumour samples(obtained from e.g. tumour purity estimation algorithms, or IHC-based pathological assessments), and
3. estimates of immune cell populations in the tumour samples (obtained from e.g. the CIBERSORT algorithm)

and <b>infer for the given cohort, the mean gene expression levels for specific cell types</b>. 

This code is a pipeline which integrates the three input, and performs a non-negative least-square regression taking the bulk expression data as the response and the cell-type proportion estimates as covariates. The mean expression levels per cell type are the coefficients from the regression model.

## Content
1. `RESPECTEx.R`: The main RESPECTEx pipeline.
2. `GSE75688_ESTIMATEpurity.txt`: Tumour purity estimates for the GSE75688 breast cancer cohort generated using the ESTIMATE algorithm, extrapolated by comparing to TCGA tumours.
3. `GSE75688_pooledOrTumor_TPM_normalized_CIBERSORT.txt`: Immune cell subpopulation proportion estimates for the GSE75688 breast cancer cohort generated using the CIBERSORT algorithm.
4. `GSE75688_pooledOrTumor_TPM_normalized.txt`: Transcript per million (TPM) expression data from pooled cells/bulk tumour samples of the GSE75688 breast cancer cohort. This is a test input to the RESPECTEx pipeline.
5. `GSE75688_RESPECTEx.txt`: Expected output from RESPECTEx analysis of the GSE75688 breast cancer cohort.

Please see `RESPECTEx.R` for instructions on how to run the analysis.

## License
RESPECTEx is distributed and licensed under GNU General Public License v3.0. Please see file "LICENSE" for details.

## To use, please cite:
Ng JCF, Quist J, Grigoriadis A, Malim MH & Fraternali F. Pan-cancer transcriptomic analysis dissects immune and proliferative functions of APOBEC3 cytidine deaminases. <em>Manuscript in preparation</em>, 2018.
