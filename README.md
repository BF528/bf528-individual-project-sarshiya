# bf528-individual-project-sarshiya
CHIPseq

METHODS 
CHIPseq dataset of Mus Musculus consisting of paired experiments are obtained.Initial quality control was performed using FastQC (v0.12.1-0) to assess the quality of raw sequencing reads.Adapter trimming and quality filtering is done with the help of Trimmomatic v(0.39). Reads were aligned to the reference genome using a suitable aligner Bowtie2 v(2.5.3).Alignment statistics, including mapping rates and unique mapping rates, were calculated using tools like SAMtools v(1.19.2). And quality assesment is run using flagstat.Using MultiQC v(1.20) to aggregate QC metrics from multiple samples into a single report.Samples with poor read quality or low alignment rates were considered for exclusion from further analysis based on quality control metrics. BigWig files were generated from sorted BAM files to visualize the distribution of reads across the genome in each sample, and Deeptools v(3.5.4) created a single matrix of signal values and calculated correlations. HOMER's v(4.11) findPeaks utility was used for peak calling, and filtered peaks were annotated to the nearest genomic features.Reproducible peaks were determined by comparing peaks across replicates using peak intersection. Peaks overlapping blacklisted regions were filtered out to remove potential artifacts.The number of peaks called in each replicate and the number of reproducible peaks across replicates were reported to assess the quality of peak calling. Motif analysis was conducted on reproducible peaks using tools such as HOMER to identify enriched DNA motifs.The proportions of where the factor of interest bound (e.g., promoter, intergenic, intron, exon, TTS) were determined and visualized in a figure.Gene enrichment analysis on annotated peaks was performed using well-validated tools such as GREAT or ChIP-Enrich.

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
