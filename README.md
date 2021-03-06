### This code is associated with the paper from Saito et al., "Translational initiation in E. coli occurs at the correct sites genome-wide in the absence of mRNA-rRNA base-pairing". eLife, 2020. http://dx.doi.org/10.7554/eLife.55002
# 2019_SDASD

The codes to process and analyze FASTQ files obtained from the MS2 pulldown ribosome profiling, standard ribosome profiling, and RNAseq in “A Genome-Wide Analysis of the Role of Shine-Dalgarno Sequences in Promoting Translation in E. coli”. First run codes for data processing, then run codes for data analyses.

### Dependencies
* Tally
* skewer-0.2.2
* seqtk-1.0-r31
* bowtie-1.1.2
* free_align
* python 2.7
* Anaconda2-5.0.1
* Jupyter notebook
* pickle
* numpy
* scipy
* pandas
* matplotlib
* seaborn
* kpLogo-1.1
* R
* xtail

### Data processing
Each notebook contains codes which performe UMI screening and trimming, linker trimming, chromsome mapping, and calculation of RPM and RPKM. For a library sequenced multiple times, merge fastq files before mapping by bowtie. 
* SDASD_Genes_TranscriptionUnits.ipynb - creates a dictionary "Ecoli_Gene_TU.pickle", requied for calculation of RPKM during data processing, based on "coli.gff" and "mbo004141900st4_TranscriptionUnits.csv"
* Skewer_Bowtie_Density_RPKM.ipynb - for ribosome profiling libraries without UMI 
* Tally_Skewer_Seqtk_Bowtie_Density_RPKM.ipynb - for ribosome profiling libraries with UMI
* Truseq_Bowtie_Density_RPKM.ipynb - for RNA-seq libraries

### Data analyses
* SDfigure.csv - contains RPKM, RPC (read per codon), read counts from each library calculated in data processing; also contains SD-ASD affinity, GINI index, SHAPE reactivity
* SDASD_freealign.ipynb - calculates SD-ASD affinity of each gene
* SDASD_ShapeReactivity.ipynb - calculates SHAPE reactivity of each gene 
* SDASD_Correlation.ipynb - calculates linear correlation and creates scatter plots
* SDASD_DensityPlot.ipynb - creates density plots 
* SDASD_Stresses_Xtail.ipynb - run xtail to compare effect of SD motifs between optimal and stress conditions
* SDASD_Stresses_VolcanoPlot.ipynb - creates volcano plots based on the results of xtail
* SDASD_coupling_optimal.ipynb - analyzes distribution of RNA features between top and bottom 20% of SD effect in optimal condition 
* SDASD_coupling_cold.ipynb - analyzes distribution of RNA features between top and bottom 20% of SD effect in cold shock 
* SDASD_RET_DensityPlot.ipynb - creates density plots of retapamulin-treated ribosome profilnig
* SDASD_RET_AGP.ipynb - creates average gene plot of retapamulin-treated ribosome profilnig on annotated and non-annoated AUGs
* SDASD_RET_ViolinPlot.ipynb - calculates initiation scores and creates violin plots
* SDASD_kpLogo.ipynb - makes fasta files of specified AUGs then creates various Logo plots including probability logo plots 
* SDASD_ShapeReactivity_StartVSNonstart.ipynb - compares median and IQR of SHAPE reactivity between annotated and non-annotated AUGs
