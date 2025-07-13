# Bioinformatics Processing

## Trimming with Trimgalore

Raw FASTQ files were trimmed and a quality report was produced with FastQC through Trimgalore v0.6.10

```
trim_galore --paired -q 24 --fastqc --fastqc_args "--noextract --nogroup --outdir 1_trim/fastqc" --stringency 5 --illumina --length 50
-o 1_trim --clip_R1 12 --clip_R2 12 [path/to/read1] [path/to/read2]
```

## Mapping with STAR

Using v2.7.10b of STAR, trimmed reads were mapped to the bear genome brown bear reference genome assembly NCBI GCF_023065955.2, and only uniquely mapped reads were kept and then converted to BAM files,

```
STAR \
--runThreadN 12 \
--genomeDir path/to/directory \
--sjdbGTFfile ./star/ursus_arctos.gtf \
--sjdbOverhang 100 \
--outFilterMultimapNmax 1 \
--readFilesIn path/to/fastq path/to/fastq \
--twopassMode Basic \
--outFileNamePrefix path/to/directory
--outSAMtype BAM SortedByCoordinate
```
## Quantifying Gene Level Counts with featureCounts

FeatureCounts was used to count our feature of exons, with gene_ID for meta-feature level summarization in the bear reference genome GCF_023065955.2

```
featureCounts -p -F 'GTF' -T 8 -t exon -g gene_id -a [path/to/GTF] -o [outfile.txt] [path/to/sorted/bam/files/*.bam]
```



