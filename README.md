# IBD-Patients-Pericytes-Single-Cell-RNAseq
Single-cell RNA-seq analysis of pericytes from IBD patients and healthy CRC controls (CRC Stage I untreated Patients). Includes QC, Harmony integration, DEG, FGSEA, DCATS, and cell–cell communication to explore biological mechanisms driving inflammation.


Content:

- QC & Filtering: Patient and cell level filtering
- Integration: batch correction using Harmony
- Dimensionality reduction & clustering: PCA, UMAP, MDS
- Differential Expression (DEG): DESeq2-based contrasts between study groups and Pathway Enrichment Analysis (FGSEA)
- DCATS for identifying encriched pericytes subclusters across conditions
- Cell–cell communication: interaction analysis to study inflammatory microenvironment

The objective of this project is to perform a Single Cell RNA seq analysis on pericytes from IBD patients, in order to try to elucidate the rol of this celltype in the complex and intrincated process of Inflammation. 


Data is composed by 44 samples of 32 different patients. These samples are divided in "Inflamed" (Inflammed tissue from IBD patients), "Non Inflamed" (Non Inflamed tissue from IBD patients) and "Healthy". 

## Patient Selection

The dataset had strong batch effect (different sequencing batches, different patients). Also, due to experimental design conditions, it was not possible to include "Patient" or "Sequencing Batch" as a covariate in the DEG pseudobulk analysis, as there were no enough "anchors" (Patient/Sequencing Batch with both conditions present). 

Analysis on Non inflamed samples showed that there were not enough cells from this condition to perform a proper analysis, so samples from this condition were excluded. Interestingly, the harmony integrated MDS plot showed that Non Inflamed samples tend to cluster with healthy samples after the harmony correction. This would give room for a future (using data with more Non Inflamed cells) batch/Patient corrected comparison where the Non Inflamed tissue could be treated as a "Healthy" tissue, and we could attribute the major changes between samples to inflammation. 

To try to deal with batch effects, patients which Non Inflamed and Inflamed tissues clearly clustered together (this means that patient/Sequencing Batch effects were more powerful than the Inflammed/Non inflammed condition) were excluded from the analysis.




