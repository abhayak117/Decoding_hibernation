# Trimgalore and FastQC

## Purpose
Trimgalore v0.6.10 is a tool used to automate the process of trimming low-quality ends and adapter sequences from raw reads and to produce a quality report through FastQC. 

## Function

Trimgalore clips Illumina adapter sequences, removes low-quality ends, trims the first 12 bp of each read, and discards reads under 50 bp. It also runs FastQC on trimmed outputs and provides a quality score. We then used MultiQC to aggragte QC data to create a report


## Usage

```
trim_galore --paired -q 24 --fastqc --fastqc_args "--noextract --nogroup --outdir 1_trim/fastqc" --stringency 5 --illumina --length 50
-o 1_trim --clip_R1 12 --clip_R2 12 [path/to/read1] [path/to/read2]
```

We used trimgalore to trim our raw reads and run FastQC



