# bf528-individual-project-sarshiya
### CHIPseq

### Methods

ChIP-seq datasets of Mus musculus consisting of single end experiments were obtained. Initial quality control was performed using FastQC v0.12.1-0 to assess the quality of raw sequencing reads. Adapter trimming and quality filtering were conducted using Trimmomatic v0.39. Reads were aligned to the Mus musculus reference genome (GRCm39) using Bowtie2 v2.5.3. The reference genome sequence used was `GRCm39.primary_assembly.genome.fa.gz`. 

Alignment statistics, including mapping rates and unique mapping rates, were calculated using SAMtools v1.19.2, with quality assessment performed using flagstat. MultiQC v1.20 aggregated QC metrics from multiple samples into a single report. 

BigWig files were generated from sorted BAM files to visualize the distribution of reads across the genome in each sample. Deeptools v3.5.4 created a single matrix of signal values and calculated correlations across samples. Peak calling was performed using HOMER v4.11 with the findPeaks utility, and filtered peaks were annotated to the nearest genomic features using the provided annotations which were derived from `gencode.vM34.primary_assembly.annotation.gtf.gz`.

Reproducible peaks were determined by comparing peaks across replicates using peak intersection strategies. Peaks overlapping blacklisted regions were filtered out to remove potential artifacts. The number of peaks called in each replicate and the number of reproducible peaks across replicates were reported to assess the quality of peak calling. Motif analysis on reproducible peaks was conducted using HOMER to identify enriched DNA motifs.

The proportions of where the factor of interest bound (e.g., promoter, intergenic, intron, exon, TTS) were determined and visualized in figures. Gene enrichment analysis on annotated peaks was performed using well-validated tools such as GREAT or ChIP-Enrich.

### Citations

Include citations for all tools and resources used in the study. Example format for citations:

- Andrews, S. (2010). FastQC: a quality control tool for high throughput sequence data. https://www.bioinformatics.babraham.ac.uk/projects/fastqc/
- Bolger, A. M., Lohse, M., & Usadel, B. (2014). Trimmomatic: a flexible trimmer for Illumina sequence data. Bioinformatics, 30(15), 2114-2120.https://academic.oup.com/bioinformatics/article/30/15/2114/2390096
- Langmead, B., & Salzberg, S. L. (2012). Fast gapped-read alignment with Bowtie 2. Nature methods, 9(4), 357-359.https://bowtie-bio.sourceforge.net/bowtie2/index.shtml
- Li, H., Handsaker, B., Wysoker, A., Fennell, T., Ruan, J., Homer, N., ... & 1000 Genome Project Data Processing Subgroup. (2009). The sequence alignment/map format and SAMtools. bioinformatics, 25(16), 2078-2079.https://academic.oup.com/bioinformatics/article/25/16/2078/204688
- Ewels, P., Magnusson, M., Lundin, S., & Käller, M. (2016). MultiQC: summarize analysis results for multiple tools and samples in a single report. Bioinformatics, 32(19), 3047-3048.https://academic.oup.com/bioinformatics/article/32/19/3047/2196507


Questions to address-
1. Briefly remark on the quality of the sequencing reads and the alignment statistics, make sure to specifically mention the following:
  -Are there any concerning aspects of the quality control of your sequencing reads?
  -Are there any concerning aspects of the quality control related to alignment?
  -Based on all of your quality control, will you exclude any samples from further analysis?

2. After QC, please generate a “fingerprint” plot (see deeptools utility) and a heatmap plot of correlation values between samples (see project 2)
  -Briefly remark on the plots and what tjey indicates to you in terms of the experiment

3.After performing peak calling analysis, generating a set of reproducible peaks and filtering peaks from blacklisted regions, please answer the following:
  -How many peaks are present in each of the replicates?
  -How many peaks are present in your set of reproducible peaks? What strategy did you use to determine “reproducible” peaks?
  -How many peaks remain after filtering out peaks overlapping blacklisted regions?

4.After performing motif analysis and gene enrichment on the peak annotations, please answer the following:
  -Briefly discuss the main results of both of these analyses and what they might imply about the function of the factor we are interested in
  
  
DELIVERIBLES

1.Produce a heatmap of correlation values between samples (see project 2)

2.Generate a “fingerprint” plot using the deeptools plotFingerprint utility

3.Create a figure / table containing the number of peaks called in each replicate, and the number of reproducible peaks

4.A single BED file containing the reproducible peaks you determined from the experiment.

5.Perform motif finding on your reproducible peaks

5.Create a single table / figure with the most interesting results
Perform a gene enrichment analysis on the annotated peaks using a well-validated gene enrichment tool

6.Create a single table / figure with the most interesting results
Produce a figure that displays the proportions of where the factor of interest is binding (Promoter, Intergenic, Intron, Exon, TTS, etc.)
