# STAR


## Purpose

Spliced Transcripts Alignment to a Reference, (STAR) is an aligner designed to align transcipts to a reference genome. By using a multistep process of seed searching, clustering, stitching, and scoring, STAR accounts for spliced alignment and finds the best alignment of multiple possibilities.


## Function
→ What’s happening with the data when it’s called

First we index the genome, which creates a data structure, called an index, that allows for rapid searching and retrieval of sequence information within a genome. STAR is able to use the indexed genome to map reads to the reference genome more efficently. 


## Usage

Using v2.7.10b of STAR, trimmed reads were mapped to the bear genome brown bear reference genome assembly NCBI GCF_023065955.2, and only uniquely mapped reads were kept and then converted to BAM files, which are compressed of SAM files

```
STAR \
--runThreadN 12 \
--genomeDir ./2_star/indexed_genome/ \
--sjdbGTFfile ./star/ursus_arctos.gtf \
--sjdbOverhang 100 \
--outFilterMultimapNmax 1 \
--readFilesIn 1_trim/read_1_val.fastq 1_trim/read_2_val.fastq \
--twopassMode Basic \
--outFileNamePrefix analysis/2_star/${sra}_
--outSAMtype BAM SortedByCoordinate
```
