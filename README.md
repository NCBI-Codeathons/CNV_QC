# CNV_QC

Creating an awesome tool to perform CNV QC on WES data independent of callers/platform that focuses on confidence and reportability of CNV calls, particularly in clinical data.
CNV QC creates a unified independent set of metrics for QCing CNV calls to identify false positive calls and enable cross caller comparisons.
We use fastqc to evaluate overall library metrics, focusing on whether or not the overall library passes basecall qualities


# Motivation:
* CNV callers based on WES frequently produce noisy/false positive calls
* Validating these calls involves MPLA/external tools: time + memory 
# Solution: 
* Unified independent set of metrics for QCing CNV calls
* Identify false positive calls 
* Enable cross callers comparison 

# Workflow:
![](https://github.com/NCBI-Codeathons/CNV_QC/raw/master/workflow_new.png)

# Datasets:
1-Simulated CNV 6 samples (males and females) fastq data (truthset: https://docs.google.com/spreadsheets/d/1TcpIsANN-rxTqyr-k5E9MS0ijj_5GxyNBR-4wFGaJUw/edit#gid=0)
2-1000Genomes 10 random samples (males and females) mapped data
# QC metrics:
* Read quality in SV - python to pull from vcf
* P-value? Outlier 
* Read quality (just use a subset: 2nd 10k)
* Sex identification - XYAlign
* Relatedness of samples - PLINK
* Noisiness of read depth - python to pull from vcf
* Distribution of calls - python to pull from vcf
* Mappability
* GC content - DangerTrack
* Stability? - DangerTrack
* SD of read depth across samples? - python to pull from vcf

# Input
# Output
# Dependencies
* Xyalign
* Pysam 
* Pyvcf
