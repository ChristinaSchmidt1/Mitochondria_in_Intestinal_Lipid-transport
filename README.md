# **Mitochondrial dysfunction abrogates dietary lipid processing in enterocytes**
*Chrysanthi Moschandrea[^1][^2], Vangelis Kondylis[^3][^4], Ioannis Evangelakos[^5], Marija Herholz[^2][^6], Farina Schneider[^2][^7] , Christina Schmidt[^2][^7][^8], Ming Yang[^2][^7][^8], Sandra Ehret[^5], Markus Heine[^5], Michelle Y. Jaeckstein[^5], Karolina Szczepanowska[^2][^6], Robin Schwarzer[^1][^2],  Linda Baumann[^2][^6], Theresa Bock[^1][^2], Efterpi Nikitopoulou[^8],Susanne Brodesser[^2], Marcus Krüger[^1][^2],  Christian Frezza[^2][^7][^8], Joerg Heeren[^5], Aleksandra Trifunovic[^2][^3][^6], Manolis Pasparakis[^1][^2][^4]*\

Correspondence: Aleksandra Trifunovic: atrifuno@uni-koeln.de & Manolis Pasparakis: pasparakis@uni-koeln.de

##
**The notebook contains:** 
Compiled source code and the real datasets to run the code. In detail, this includes RNAseq, Proteomics and Metabolomics data of total small intestinal proximal tissue from DARS2tamIEC-KO mice (RNAseq) and DARS2-deficient intestinal epithelial cell (IECs, Proteomics & Metabolomics)

## Reproducibility
Code for the R analysis can be reproduced by following the scripts in `RNAseq.Rmd`, `Proteomics.Rmd`, `Metabolomics.Rmd`. This includes data analysis and all subsequent tables and plots.

Signatures used for pathway analysis where downloaded from [MSigDB](https://www.gsea-msigdb.org/gsea/msigdb) apart from the ATF4 signature `41556_2013_BFncb2738_MOESM48_ESM (1).csv`, which was downloaded directly from the publication of [Han et al.](https://www.nature.com/articles/ncb2738.pdf), and safed in the folder ***"InputData/Signatures_for_GSEA"***.

Metabolic signatures used for pathway analysis where manually assigned based on our a priori knowledge.

List of mouse mitochondria electron transport chain complexes where extracted from [Petros et al.](https://www.cell.com/cell-reports/comments/S2211-1247(17)31412-2)

## Data
### RNAseq
The RNAseq data of the total small intestinal proximal tissue from DARS2tamIEC-KO mice have been deposited in NCBI’s Gene Expression Omnibus and are accessible through GEO Series accession number GSE207803. RNAseq data analysis (Read trimming, mapping, counting and DESeq2) was performed by Ulrike Göbel , CECAD Research Center, Cologne, Germany. Input data are available in the folder ***"InputData\RNAseq"***:

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

## System requirements
Software dependencies and operating systems (including version numbers) can be found in the end of `RNAseq.html`, `Proteomics.html`, `Metabolomics.html`. There are no other non-standard hardware requirements and to run the code one requires only a standard computer with enough RAM to support the in-memory operations.

General information of the system the code was run on:
```
## R version 4.1.3 (2022-03-10)
## Platform: x86_64-w64-mingw32/x64 (64-bit)
## Running under: Windows 10 x64 (build 19044)
## 
## Matrix products: default
## 
## locale:
## [1] LC_COLLATE=English_Germany.1252  LC_CTYPE=English_Germany.1252   
## [3] LC_MONETARY=English_Germany.1252 LC_NUMERIC=C                    
## [5] LC_TIME=English_Germany.1252    
```

Package information and versions:
```
############################# Metabolomics.html
## attached base packages: 
##
## [1] stats     graphics  grDevices utils     datasets  methods   base     
## 
## other attached packages:
##  [1] EnhancedVolcano_1.12.0 ggrepel_0.9.1          gtools_3.9.2          
##  [4] viridis_0.6.2          viridisLite_0.4.0      RColorBrewer_1.1-3    
##  [7] ggfortify_0.4.14       devtools_2.4.3         usethis_2.1.5         
## [10] gplots_3.1.1           kableExtra_1.3.4       rmarkdown_2.13        
## [13] forcats_0.5.1          stringr_1.4.0          dplyr_1.0.8           
## [16] purrr_0.3.4            readr_2.1.2            tidyr_1.2.0           
## [19] tibble_3.1.6           ggplot2_3.3.5          tidyverse_1.3.1       
## 
## loaded via a namespace (and not attached):
##  [1] bitops_1.0-7       fs_1.5.2           lubridate_1.8.0    ash_1.0-15        
##  [5] webshot_0.5.3      httr_1.4.2         rprojroot_2.0.3    tools_4.1.3       
##  [9] backports_1.4.1    bslib_0.3.1        utf8_1.2.2         R6_2.5.1          
## [13] vipor_0.4.5        KernSmooth_2.23-20 DBI_1.1.2          colorspace_2.0-3  
## [17] withr_2.5.0        ggrastr_1.0.1      tidyselect_1.1.2   gridExtra_2.3     
## [21] prettyunits_1.1.1  processx_3.5.3     ggalt_0.4.0        extrafontdb_1.0   
## [25] compiler_4.1.3     textshaping_0.3.6  cli_3.1.0          rvest_1.0.2       
## [29] xml2_1.3.3         desc_1.4.1         labeling_0.4.2     sass_0.4.1        
## [33] caTools_1.18.2     scales_1.2.0       proj4_1.0-11       callr_3.7.0       
## [37] systemfonts_1.0.4  digest_0.6.29      svglite_2.1.0      pkgconfig_2.0.3   
## [41] htmltools_0.5.2    extrafont_0.18     sessioninfo_1.2.2  highr_0.9         
## [45] maps_3.4.0         dbplyr_2.1.1       fastmap_1.1.0      rlang_1.0.2       
## [49] readxl_1.4.0       rstudioapi_0.13    farver_2.1.0       jquerylib_0.1.4   
## [53] generics_0.1.2     jsonlite_1.8.0     magrittr_2.0.3     ggbeeswarm_0.6.0  
## [57] Rcpp_1.0.8         munsell_0.5.0      fansi_1.0.3        lifecycle_1.0.1   
## [61] stringi_1.7.6      yaml_2.3.5         MASS_7.3-55        brio_1.1.3        
## [65] pkgbuild_1.3.1     grid_4.1.3         crayon_1.5.1       haven_2.5.0       
## [69] hms_1.1.1          knitr_1.38         ps_1.6.0           pillar_1.7.0      
## [73] pkgload_1.2.4      reprex_2.0.1       glue_1.6.2         evaluate_0.15     
## [77] remotes_2.4.2      modelr_0.1.8       vctrs_0.3.8        tzdb_0.3.0        
## [81] Rttf2pt1_1.3.10    testthat_3.1.3     cellranger_1.1.0   gtable_0.3.0      
## [85] assertthat_0.2.1   cachem_1.0.6       xfun_0.30          broom_0.8.0       
## [89] ragg_1.2.2         beeswarm_0.4.0     memoise_2.0.1      ellipsis_0.3.2

############################# Proteomics.html
## attached base packages:
## [1] stats4    stats     graphics  grDevices utils     datasets  methods  
## [8] base     
## 
## other attached packages:
##  [1] GSEABase_1.56.0        graph_1.72.0           annotate_1.72.0       
##  [4] XML_3.99-0.9           AnnotationDbi_1.56.2   IRanges_2.28.0        
##  [7] S4Vectors_0.32.3       Biobase_2.54.0         BiocGenerics_0.40.0   
## [10] fgsea_1.20.0           reticulate_1.24        EnhancedVolcano_1.12.0
## [13] ggrepel_0.9.1          ggfortify_0.4.14       devtools_2.4.3        
## [16] usethis_2.1.5          rmarkdown_2.13         forcats_0.5.1         
## [19] stringr_1.4.0          dplyr_1.0.8            purrr_0.3.4           
## [22] readr_2.1.2            tidyr_1.2.0            tibble_3.1.6          
## [25] ggplot2_3.3.5          tidyverse_1.3.1       
## 
## loaded via a namespace (and not attached):
##   [1] readxl_1.4.0           backports_1.4.1        fastmatch_1.1-3       
##   [4] systemfonts_1.0.4      plyr_1.8.6             BiocParallel_1.28.3   
##   [7] GenomeInfoDb_1.30.1    digest_0.6.29          htmltools_0.5.2       
##  [10] fansi_1.0.3            magrittr_2.0.3         memoise_2.0.1         
##  [13] tzdb_0.3.0             remotes_2.4.2          Biostrings_2.62.0     
##  [16] modelr_0.1.8           extrafont_0.18         extrafontdb_1.0       
##  [19] prettyunits_1.1.1      colorspace_2.0-3       blob_1.2.3            
##  [22] rvest_1.0.2            rappdirs_0.3.3         textshaping_0.3.6     
##  [25] haven_2.5.0            xfun_0.30              callr_3.7.0           
##  [28] crayon_1.5.1           RCurl_1.98-1.6         jsonlite_1.8.0        
##  [31] glue_1.6.2             gtable_0.3.0           zlibbioc_1.40.0       
##  [34] XVector_0.34.0         proj4_1.0-11           pkgbuild_1.3.1        
##  [37] Rttf2pt1_1.3.10        maps_3.4.0             scales_1.2.0          
##  [40] DBI_1.1.2              Rcpp_1.0.8             xtable_1.8-4          
##  [43] bit_4.0.4              httr_1.4.2             RColorBrewer_1.1-3    
##  [46] ellipsis_0.3.2         pkgconfig_2.0.3        farver_2.1.0          
##  [49] sass_0.4.1             dbplyr_2.1.1           utf8_1.2.2            
##  [52] here_1.0.1             tidyselect_1.1.2       labeling_0.4.2        
##  [55] rlang_1.0.2            munsell_0.5.0          cellranger_1.1.0      
##  [58] tools_4.1.3            cachem_1.0.6           cli_3.1.0             
##  [61] generics_0.1.2         RSQLite_2.2.10         broom_0.8.0           
##  [64] evaluate_0.15          fastmap_1.1.0          yaml_2.3.5            
##  [67] ragg_1.2.2             processx_3.5.3         knitr_1.38            
##  [70] bit64_4.0.5            fs_1.5.2               KEGGREST_1.34.0       
##  [73] ash_1.0-15             ggrastr_1.0.1          xml2_1.3.3            
##  [76] brio_1.1.3             compiler_4.1.3         rstudioapi_0.13       
##  [79] beeswarm_0.4.0         png_0.1-7              testthat_3.1.3        
##  [82] reprex_2.0.1           bslib_0.3.1            stringi_1.7.6         
##  [85] highr_0.9              ps_1.6.0               desc_1.4.1            
##  [88] ggalt_0.4.0            lattice_0.20-45        Matrix_1.4-0          
##  [91] vctrs_0.3.8            pillar_1.7.0           lifecycle_1.0.1       
##  [94] jquerylib_0.1.4        data.table_1.14.2      bitops_1.0-7          
##  [97] R6_2.5.1               KernSmooth_2.23-20     gridExtra_2.3         
## [100] vipor_0.4.5            sessioninfo_1.2.2      MASS_7.3-55           
## [103] assertthat_0.2.1       pkgload_1.2.4          rprojroot_2.0.3       
## [106] withr_2.5.0            GenomeInfoDbData_1.2.7 parallel_4.1.3        
## [109] hms_1.1.1              grid_4.1.3             lubridate_1.8.0       
## [112] ggbeeswarm_0.6.0

############################# RNAseq.html
## attached base packages:
## [1] stats4    stats     graphics  grDevices utils     datasets  methods  
## [8] base     
## 
## other attached packages:
##  [1] GSEABase_1.56.0        graph_1.72.0           annotate_1.72.0       
##  [4] XML_3.99-0.9           fgsea_1.20.0           enrichplot_1.14.2     
##  [7] clusterProfiler_4.2.2  org.Mm.eg.db_3.14.0    AnnotationDbi_1.56.2  
## [10] IRanges_2.28.0         S4Vectors_0.32.3       Biobase_2.54.0        
## [13] BiocGenerics_0.40.0    reticulate_1.24        EnhancedVolcano_1.12.0
## [16] ggrepel_0.9.1          viridis_0.6.2          viridisLite_0.4.0     
## [19] ggfortify_0.4.14       devtools_2.4.3         usethis_2.1.5         
## [22] rmarkdown_2.13         forcats_0.5.1          stringr_1.4.0         
## [25] dplyr_1.0.8            purrr_0.3.4            readr_2.1.2           
## [28] tidyr_1.2.0            tibble_3.1.6           ggplot2_3.3.5         
## [31] tidyverse_1.3.1       
## 
## loaded via a namespace (and not attached):
##   [1] utf8_1.2.2             tidyselect_1.1.2       RSQLite_2.2.10        
##   [4] grid_4.1.3             BiocParallel_1.28.3    scatterpie_0.1.7      
##   [7] munsell_0.5.0          ragg_1.2.2             withr_2.5.0           
##  [10] colorspace_2.0-3       GOSemSim_2.20.0        ggalt_0.4.0           
##  [13] highr_0.9              knitr_1.39             rstudioapi_0.13       
##  [16] DOSE_3.20.1            Rttf2pt1_1.3.10        labeling_0.4.2        
##  [19] GenomeInfoDbData_1.2.7 polyclip_1.10-0        bit64_4.0.5           
##  [22] farver_2.1.0           rprojroot_2.0.3        downloader_0.4        
##  [25] vctrs_0.3.8            treeio_1.18.1          generics_0.1.2        
##  [28] xfun_0.30              R6_2.5.1               GenomeInfoDb_1.30.1   
##  [31] ggbeeswarm_0.6.0       graphlayouts_0.8.0     bitops_1.0-7          
##  [34] cachem_1.0.6           gridGraphics_0.5-1     assertthat_0.2.1      
##  [37] scales_1.2.0           vroom_1.5.7            ggraph_2.0.5          
##  [40] beeswarm_0.4.0         gtable_0.3.0           ash_1.0-15            
##  [43] processx_3.5.3         tidygraph_1.2.1        rlang_1.0.2           
##  [46] systemfonts_1.0.4      splines_4.1.3          extrafontdb_1.0       
##  [49] lazyeval_0.2.2         broom_0.8.0            yaml_2.3.5            
##  [52] reshape2_1.4.4         modelr_0.1.8           backports_1.4.1       
##  [55] qvalue_2.26.0          extrafont_0.18         tools_4.1.3           
##  [58] ggplotify_0.1.0        ellipsis_0.3.2         jquerylib_0.1.4       
##  [61] RColorBrewer_1.1-3     sessioninfo_1.2.2      Rcpp_1.0.8            
##  [64] plyr_1.8.6             zlibbioc_1.40.0        RCurl_1.98-1.6        
##  [67] ps_1.7.0               prettyunits_1.1.1      haven_2.5.0           
##  [70] fs_1.5.2               here_1.0.1             magrittr_2.0.3        
##  [73] data.table_1.14.2      DO.db_2.9              reprex_2.0.1          
##  [76] ggnewscale_0.4.7       pkgload_1.2.4          xtable_1.8-4          
##  [79] hms_1.1.1              patchwork_1.1.1        evaluate_0.15         
##  [82] readxl_1.4.0           gridExtra_2.3          testthat_3.1.4        
##  [85] compiler_4.1.3         maps_3.4.0             KernSmooth_2.23-20    
##  [88] crayon_1.5.1           shadowtext_0.1.2       htmltools_0.5.2       
##  [91] ggfun_0.0.6            tzdb_0.3.0             snow_0.4-4            
##  [94] aplot_0.1.4            lubridate_1.8.0        DBI_1.1.2             
##  [97] tweenr_1.0.2           dbplyr_2.1.1           proj4_1.0-11          
## [100] MASS_7.3-55            rappdirs_0.3.3         Matrix_1.4-0          
## [103] brio_1.1.3             cli_3.1.0              parallel_4.1.3        
## [106] igraph_1.3.1           pkgconfig_2.0.3        xml2_1.3.3            
## [109] ggtree_3.2.1           vipor_0.4.5            bslib_0.3.1           
## [112] XVector_0.34.0         rvest_1.0.2            yulab.utils_0.0.4     
## [115] callr_3.7.0            digest_0.6.29          Biostrings_2.62.0     
## [118] cellranger_1.1.0       fastmatch_1.1-3        tidytree_0.3.9        
## [121] lifecycle_1.0.1        nlme_3.1-155           jsonlite_1.8.0        
## [124] desc_1.4.1             fansi_1.0.3            pillar_1.7.0          
## [127] lattice_0.20-45        ggrastr_1.0.1          KEGGREST_1.34.0       
## [130] fastmap_1.1.0          httr_1.4.3             pkgbuild_1.3.1        
## [133] GO.db_3.14.0           glue_1.6.2             remotes_2.4.2         
## [136] png_0.1-7              bit_4.0.4              ggforce_0.3.3         
## [139] stringi_1.7.6          sass_0.4.1             blob_1.2.3            
## [142] textshaping_0.3.6      memoise_2.0.1          ape_5.6-2
```
## Installation guide
To install the required packages use `install.packages()` or bioconductor install 
`if (!require("BiocManager", quietly = TRUE)) 
install.packages("BiocManager")
BiocManager::install()`

The installation time should be roughly 20min for all of them. 

## Demo and instructions for use
You can use the code for the R analysis by following the scripts in `RNAseq.Rmd`/`RNAseq.html`, `Proteomics.Rmd`/`Proteomics.html`, `Metabolomics.Rmd`/`Metabolomics.html`, which include the path to the input data. The run time for each script on a normal machine should be roughly 15min.
To run the code on your data you can also follow the mentioned scripts using the package versions mentioned above.

[^1]: Institute for Genetics, University of Cologne, Cologne, Germany.
[^2]: Cologne Excellence Cluster on Cellular Stress Responses in Aging-Associated Diseases (CECAD), University of Cologne, Cologne, Germany.
[^3]: Institute for Pathology, Medical Faculty and University Hospital of Cologne, University of Cologne, Germany.
[^4]: Center for Molecular Medicine (CMMC), University of Cologne, Cologne, Germany.
[^5]: Department of Biochemistry and Molecular Cell Biology, University Medical Center Hamburg-Eppendorf, Hamburg, Germany
[^6]: Institute for Mitochondrial Diseases and Aging, Medical Faculty, University of Cologne, Cologne, Germany
[^7]: Medical Faculty and University Hospital of Cologne, University of Cologne, Germany.
[^8]: MRC Cancer Unit, University of Cambridge, Hutchison/MRC Research Centre, Box 197, Cambridge Biomedical Campus, Cambridge CB2 0XZ, UK
