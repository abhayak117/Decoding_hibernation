# FeatureCounts

## Purpose
Feature counts is used to to count reads from RNA-seq or DNA-seq experiments, and it assigns reads to specific genomic features like genes, exons, or promoters based on their alignment to a reference genome, which is crucial for downstream analysis

## Function

FeatureCounts takes SAM or BAM files as an imputs and a reference annotation file including chromosomal coordinates of features. It outputs numbers of reads assigned to meta-features (ex. genes). It also outputs a summary of the results, including number of successfully assigned reads and number of reads that failed to be assigned for various reasons. The output of featureCounts is a matrix of read counts, where each row is a gene and each column is a sample. 

## Usage

FeatureCounts was used to count our feature of exons, with gene_ID for meta-feature level summarization in the bear reference genome GCF_023065955.2

```
featureCounts -p -F 'GTF' -T 8 -t exon -g gene_id -a [path/to/GTF] -o [outfile.txt] [path/to/sorted/bam/files/*.bam]
```
