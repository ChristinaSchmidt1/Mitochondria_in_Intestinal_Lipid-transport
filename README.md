# **Mitochondria regulate dietary lipid processing in enterocytes**
*Chrysanthi Moschandrea[^1][^2] , Vangelis Kondylis[^1][^2][^3], Marija Herholz[^2][^4], Karolina Szczepanowska[^2][^4], Robin Schwarzer[^1][^2], Ioannis Evangelakos[^5], Markus Heine[^5], Michelle Y. Jaeckstein[^5], Christina Schmidt[^6], Ming Yang[^6], Efterpi Nikitopoulou[^6], Theresa Bock[^1][^2], Marcus Krüger[^1][^2], Susanne Brodesser[^2], Christian Frezza[^6], Joerg Heeren[^5], Aleksandra Trifunovic[^2][^3][^4], Manolis Pasparakis[^1][^2][^3]*

##
**The notebook contains:** 
RNAseq, Proteomics and Metabolomics data of total small intestinal proximal tissue from DARS2tamIEC-KO mice (RNAseq) and DARS2-deficient intestinal epithelial cell (IECs, Proteomics & Metabolomics)

## Reproducibility
Code for the R analysis can be reproduced by following the scripts in `RNAseq.Rmd`, `Proteomics.Rmd`, `Metabolomics.Rmd`. This includes data analysis and all subsequent tables and plots.

Signatures used for pathway analysis where downloaded from [MSigDB](https://www.gsea-msigdb.org/gsea/msigdb) apart from the ATF4 signature `41556_2013_BFncb2738_MOESM48_ESM (1).csv`, which was downloaded directly from the publication of [Han et al.](https://www.nature.com/articles/ncb2738.pdf), and safed in the folder ***"InputData/Signatures_for_GSEA"***.

Metabolic signatures used for pathway analysis where manually assigned based on our a priori knowledge.

List of mouse mitochondria electron transport chain complexes where extracted from [Petros et al.](https://www.cell.com/cell-reports/comments/S2211-1247(17)31412-2)

## Data
### RNAseq
The RNAseq data of the total small intestinal proximal tissue from DARS2tamIEC-KO mice will be deposited with the manuscript (under revision). RNAseq data analysis (Read trimming, mapping, counting and DESeq2) was performed by Ulrike Göbel , CECAD Research Center, Cologne, Germany. Input data are available in the folder ***"InputData\RNAseq"***:

- `RawCounts.csv` Raw count matrix (Provided by Ulrike Göbel)
- `SP_3Days_differential_expression_DESeq2_tg_VS_wt_Read2_plus_A18.csv` DESeq results comparing TG versus WT on Day 3 (Provided by Ulrike Göbel)
- `SP_7Days_differential_expression_DESeq2_tg_VS_wt_Read2_plus_A18.csv` DESeq results comparing TG versus WT on Day 7 (Provided by Ulrike Göbel)

Gene Set Enrichment Analysis (GSEA) and Over Representation Analysis (ORA) were performed and results are available in the folder ***"OutputData\RNAseq"***:

- `GSEA_result_GO-terms_Day3-TGvWT_.csv`
- `GSEA_result_GO-terms_Day7-TGvWT_.csv`
- `GSEA_result_KEGG-Hallmark-Reactome-Biocarta-ATF4_Day3-TGvWT_.csv`
- `GSEA_result_KEGG-Hallmark-Reactome-Biocarta-ATF4_Day7-TGvWT_.csv`

- `ORA_Log2FCbg1_padj0.05_3Days-TGvWT.csv`
- `ORA_Log2FCsm-1_padj0.05_3Days-TGvWT.csv`
- `ORA_Log2FCbg1_padj0.05_7Days-TGvWT.csv`
- `ORA_Log2FCsm-1_padj0.05_7Days-TGvWT.csv`

### Proteomics
The Proteomics data of the IECs have been deposited to the ProteomeXchange Consortium via the PRIDE43 partner repository with the dataset identifier PXD026934. MS-based proteome data acquisition and analysis has been performed by the Krüger Lab, CECAD Research Center, Faculty of Medicine, University Hospital Cologne, Germany. Input data are available in the folder ***"InputData\Proteomics"***:

- `20210328_proteinGroups_TB.csv` (LFQ values and the results of  the differential expression analysis was provided by Theresa Bock, Krüger Lab)
- `Petros et al_Mouse-ETC-Complexes.csv` (Mitochondria electron transport chain complexes from [Petros et al.](https://www.cell.com/cell-reports/comments/S2211-1247(17)31412-2))

GSEA and ORA were performed and results are available in the folder ***"OutputData\Proteomics"***:

- `ORA_Log2FCbg0.5_padj0.05_TGvWT.csv`
- `ORA_Log2FCsm-0.5_padj0.05_TGvWT.csv`
- `GSEA_result_KEGG-Hallmark-Reactome-Biocarta-ATF4_TGvWT_.csv`
- `GSEA_result_GO-terms_TGvWT_.csv`

### Metabolomics
The Metabolomics data of the IECs haven been deposited at Metabolomics Workbench under the study_id ST002184. LC-MS data aquistion has been performed by Ming Yang, [Frezza Laboratory](https://www.cecad.uni-koeln.de/research/principal-investigators/prof-dr-christian-frezza), CECAD Research Center, Faculty of Medicine, University Hospital Cologne, Germany. Input data are available in the folder ***"InputData\Metabolomics"***:

- `IECs_RawData.csv` (Metabolomics results)
- `Template_MetabolicPathways.csv` (Metabolite names and associated pathways)

After performing data filtering and normalisation (80%-filtering rule, missing value imputation, total/ion count normalisation) and outlier detection based on quality control (muma analysis), the results are saved in the folder ***"OutputData\Metabolomics"***:

- `Sheet2_IECs_MVI-TIC-normalised_OutliersMarked.csv`

Using the normalised data Sheet2_IECs_MVI-TIC-normalised_OutliersMarked.csv, we removed the outliers and calculated the mean of the analytical replicates. The results are saved in the folder ***"OutputData\Metabolomics"***:

- `Sheet3_IECs_MVI-TIC-normalised_Means.csv`

Differential metabolite analysis comparing KO versus WT. Here we performed the t-Test and p-value adjustment using Benjamini Hochberg. The results are saved in the folder ***"OutputData\Metabolomics"***:

- `Sheet4_DMA_TGvWT_IECs_Pathways.csv`

## Figures
Generated figures can be found in the ***html files*** or in the folder ***"Figures"***.

[^1]: Institute for Genetics, University of Cologne, Cologne, Germany.
[^2]: Cologne Excellence Cluster on Cellular Stress Responses in Aging-Associated Diseases (CECAD), University of Cologne, Cologne, Germany.
[^3]: Center for Molecular Medicine (CMMC), University of Cologne, Cologne, Germany.
[^4]: Institute for Mitochondrial Diseases and Aging, Medical Faculty, University of Cologne, Cologne, Germany
[^5]: Department of Biochemistry and Molecular Cell Biology, University Medical Center Hamburg-Eppendorf, Hamburg, Germany
[^6]: MRC Cancer Unit, University of Cambridge, Hutchison/MRC Research Centre, Box 197, Cambridge Biomedical Campus, Cambridge CB2 0XZ, UK
