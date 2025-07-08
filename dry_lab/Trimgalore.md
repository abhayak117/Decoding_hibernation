# Trimgalore and FastQC

## Purpose
Trimgalore v0.6.10 was used to trim raw reads and produce a quality report

## Function

Trimgalore clips Illumina adapter sequences, removes low-quality ends, trims the first 12 bp of each read, and discards reads under 50 bp. It also runs FastQC on trimmed outputs and privde a quality score


## Usage

```
trim_galore --paired -q 24 --fastqc --fastqc_args "--noextract --nogroup --outdir 1_trim/fastqc" --stringency 5 --illumina --length 50
-o 1_trim --clip_R1 12 --clip_R2 12 [path/to/read1] [path/to/read2]
```


