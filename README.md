# Andrena_molecular_ecology_genomics
Different paths, similar pressures: divergent drivers of genetic diversity despite convergent genomic signatures of selection in response to urban intensity in two oligolectic bee species
# Population Genomic Analysis Pipeline

This repository contains all scripts used for genome assembly, SNP calling,
population genomics, genotype–environment association, and selective sweep
analyses.

## Overview of workflow
1. Genome assembly
2. Read filtering and adapter trimming
3. Read mapping and SNP calling
4. SNP filtering and QC
5. Population genetic analyses
6. Genotype–environment association
7. Selective sweep detection
8. Visualization (Manhattan plots)
9. Functional convergence
All scripts are provided exactly as executed for the analyses.

---

## Script descriptions

### 1. Genome assembly
**Commands:**
- `wengan.pl`
- `spades.py`

**Inputs:**
- Illumina paired-end reads
- PacBio HiFi reads

**Outputs:**
- Draft genome assembly

---

### 2. Quality filtering and adapter trimming
**Script:** bbduk loop  
**Software:** BBMap / BBDuk  
**Outputs:** cleaned paired-end FASTQ files

---

### 3. Mapping and SNP calling
**Software:**
- bwa-mem2
- samtools
- GATK MarkDuplicates
- BBMap callvariants

**Outputs:**
- Deduplicated BAM files
- Raw multisample VCF

---

### 4. SNP filtering
**Software:**
- vcftools
- bcftools
- custom Python scripts (`SnpsHE.py`, `merge_afreq.py`)

Filtering steps include:
- Missingness
- Minor allele count
- Depth
- Heterozygosity
- Linkage disequilibrium pruning

---

### 5. Population genetics
**Software:**
- dartR
- adegenet
- StAMPP

Analyses include:
- Genetic diversity
- FST
- PCA

---

### 6. Genotype–environment association
**Software:**
- LFMM
- GradientForest

Permutation-based significance thresholds were used.

---

### 7. Selective sweeps
**Statistics:**
- nSL

Outlier regions were merged and intersected with GEA SNPs.

---

### 8. Visualization
**Plots:**
- Manhattan plots
