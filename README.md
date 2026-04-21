# 748-Report
Bioinformatics Research Skills - Assessment 2

Question 1 Code 

Part 1 Code 

File path:
/mnt/c/Users/Kirsten/OneDrive/Desktop/MSc_Bioinformatics/LIFE748_-_Bioinformatics_Research_Skills/ASSESSMENT2

# FastQC
Fastqc on GN9
fastqc GN9_hifix30.fastq -o fastqc_results_assembly 

# Flye 
Flye 
E.coli ref genome - https://cgr.liv.ac.uk/454/acdarby/LIFE748/EcoliK12/EcoliK12_GCA_000005845.2_ASM584v2_genomic.fna

conda –version # conda 26.1.1
conda activate genomics_env
cd into folder where fastq is saved to 
flye --pacbio-hifi GN9_hifix30.fastq --out-dir GN9_long2

[2026-04-02 09:36:25] INFO: Starting Flye 2.9.6-b1802
[2026-04-02 09:36:25] INFO: >>>STAGE: configure
[2026-04-02 09:36:25] INFO: Configuring run
[2026-04-02 09:40:03] INFO: Total read length: 150012235
[2026-04-02 09:40:03] INFO: Reads N50/N90: 18032 / 16517
[2026-04-02 09:40:03] INFO: Minimum overlap set to 10000
[2026-04-02 09:40:03] INFO: >>>STAGE: assembly
[2026-04-02 09:40:03] INFO: Assembling disjointigs
[2026-04-02 09:40:03] INFO: Reading sequences
[2026-04-02 09:40:15] INFO: Building minimizer index
[2026-04-02 09:40:15] INFO: Pre-calculating index storage
0% 10% 20% 30% 40% 50% 60% 70% 80% 90% 100%
[2026-04-02 09:40:30] INFO: Filling index
0% 10% 20% 30% 40% 50% 60% 70% 80% 90% 100%
[2026-04-02 09:41:45] INFO: Extending reads
[2026-04-02 09:42:39] INFO: Overlap-based coverage: 16
[2026-04-02 09:42:39] INFO: Median overlap divergence: 0.0013238
0% 70% 100%
[2026-04-02 09:46:29] INFO: Assembled 6 disjointigs
[2026-04-02 09:46:29] INFO: Generating sequence
0% 10% 20% 30% 40% 50% 60% 70% 80% 90% 100%
[2026-04-02 09:46:34] INFO: Filtering contained disjointigs
0% 10% 30% 50% 60% 80% 100%
[2026-04-02 09:46:36] INFO: Contained seqs: 2
[2026-04-02 09:46:40] INFO: >>>STAGE: consensus
[2026-04-02 09:46:40] INFO: Running Minimap2
[2026-04-02 09:47:54] INFO: Computing consensus
[2026-04-02 09:49:28] INFO: Alignment error rate: 0.005674
[2026-04-02 09:49:28] INFO: >>>STAGE: repeat
[2026-04-02 09:49:28] INFO: Building and resolving repeat graph
[2026-04-02 09:49:28] INFO: Parsing disjointigs
[2026-04-02 09:49:29] INFO: Building repeat graph
0% 20% 50% 70% 100%
[2026-04-02 09:49:33] INFO: Median overlap divergence: 0.000598325
[2026-04-02 09:49:33] INFO: Parsing reads
[2026-04-02 09:49:47] INFO: Aligning reads to the graph
0% 10% 20% 30% 40% 50% 60% 70% 80% 90% 100%
[2026-04-02 09:51:03] INFO: Aligned read sequence: 149641518 / 150012235 (0.997529)
[2026-04-02 09:51:03] INFO: Median overlap divergence: 0.000329077
[2026-04-02 09:51:03] INFO: Mean edge coverage: 27
[2026-04-02 09:51:03] INFO: Simplifying the graph
[2026-04-02 09:51:08] INFO: >>>STAGE: contigger
[2026-04-02 09:51:08] INFO: Generating contigs
[2026-04-02 09:51:08] INFO: Reading sequences
[2026-04-02 09:51:16] INFO: Generated 4 contigs
[2026-04-02 09:51:16] INFO: Added 0 scaffold connections
[2026-04-02 09:51:20] INFO: >>>STAGE: polishing
[2026-04-02 09:51:20] INFO: Polishing genome (1/1)
[2026-04-02 09:51:20] INFO: Running minimap2
[2026-04-02 09:52:21] INFO: Separating alignment into bubbles
[2026-04-02 09:54:52] INFO: Alignment error rate: 0.003622
[2026-04-02 09:54:52] INFO: Correcting bubbles
0% 10% 20% 30% 40% 50% 60% 70% 80% 90% 100%
[2026-04-02 10:00:40] INFO: >>>STAGE: finalize
[2026-04-02 10:00:43] INFO: Assembly statistics:

Total length:   5320437
        Fragments:      4
        Fragments N50:  5028452
        Largest frg:    5028452
        Scaffolds:      0
        Mean coverage:  28

# Minimap2
Minimap2 for assembly.fasta and reference genome 
cd GN9_long2
minimap2 -ax asm5 ../EcoliK12_GCA_000005845.2_ASM584v2_genomic.fna.txt assembly.fasta > aln.sam

(genomics_env) kirstenleighnutter@LAPTOP-NSDH6EUR:/mnt/c/Users/Kirsten/OneDrive/Desktop/MSc_Bioinformatics/LIFE748_-_Bioinformatics_Research_Skills/ASSESSMENT2$ cd GN9_long2
(genomics_env) kirstenleighnutter@LAPTOP-NSDH6EUR:/mnt/c/Users/Kirsten/OneDrive/Desktop/MSc_Bioinformatics/LIFE748_-_Bioinformatics_Research_Skills/ASSESSMENT2/GN9_long2$ minimap2 -ax asm5 ../EcoliK12_GCA_000005845.2_ASM584v2_genomic.fna.txt a
ssembly.fasta > aln.sam
[M::mm_idx_gen::0.180*0.69] collected minimizers
[M::mm_idx_gen::0.194*0.84] sorted minimizers
[M::main::0.194*0.83] loaded/built the index for 1 target sequence(s)
[M::mm_mapopt_update::0.200*0.84] mid_occ = 50
[M::mm_idx_stat] kmer size: 19; skip: 19; is_hpc: 0; #seq: 1
[M::mm_idx_stat::0.207*0.85] distinct minimizers: 454545 (99.24% are singletons); average occurrences: 1.021; average spacing: 9.997; total length: 4641652
[M::worker_pipeline::4.339*0.94] mapped 4 sequences
[M::main] Version: 2.30-r1287
[M::main] CMD: minimap2 -ax asm5 ../EcoliK12_GCA_000005845.2_ASM584v2_genomic.fna.txt assembly.fasta
[M::main] Real time: 4.485 sec; CPU: 4.218 sec; Peak RSS: 0.514 GB

samtools flagstat aln.sam
416 + 0 in total (QC-passed reads + QC-failed reads)
4 + 0 primary
5 + 0 secondary
407 + 0 supplementary
0 + 0 duplicates
0 + 0 primary duplicates
414 + 0 mapped (99.52% : N/A)
2 + 0 primary mapped (50.00% : N/A)
0 + 0 paired in sequencing
0 + 0 read1
0 + 0 read2
0 + 0 properly paired (N/A : N/A)
0 + 0 with itself and mate mapped
0 + 0 singletons (N/A : N/A)
0 + 0 with mate mapped to a different chr
0 + 0 with mate mapped to a different chr (mapQ>=5)

# QUAST
Quast for assembly.fasta and reference genome 
quast assembly.fasta \
      -r ../EcoliK12_GCA_000005845.2_ASM584v2_genomic.fna.txt \
      -o quast_out


# Bakta
Bakta 

conda create -n bakta
conda activate bakta 
conda install -c conda-forge -c bioconda bakta
bakta_db download --output ~/tmp_data/ --type light

bakta --db db-light assembly.fasta --output bakta/GN3_hifix30_flye_assembly
conda deactivate

# Prokka
Prokka
conda create -n prokka
conda activate prokka 
conda install -c bioconda prokka

conda activate prokka
prokka --outdir prokka_out \
       --prefix GN9 \
       --genus Escherichia \
       --species coli \
       --strain K12 \
       --cpus 8 \
       assembly.fasta

conda activate prokka   # or your Prokka env name
which prokka
nano /path/to/miniconda3/envs/prokka/bin/prokka # edit minver version number to 2.12 for blastp and makeblastdb 

blastp -version
makeblastdb -version
prokka –depends

less GN9.txt
grep -E 'CDS:|rRNA:|tRNA:' GN9.txt

parse in r 
library(stringr)

# Read file
lines <- readLines("GN9.txt")

# Extract feature lines
features <- lines[str_detect(lines, "CDS:|rRNA:|tRNA:")]

# Split at ':' and make data frame
feature_table <- str_split_fixed(features, ":", 2)
df <- data.frame(
  Feature = feature_table[,1],
  Count = as.numeric(feature_table[,2])
)

# View results
print(df)
  Feature Count
1    tRNA    95
2    rRNA    22
3     CDS  5029

plot:
library(ggplot2)
ggplot(df, aes(x = Feature, y = Count, fill = Feature)) +
  geom_bar(stat = "identity") +
  theme_minimal() +
  ggtitle("Feature counts from Prokka annotation")

# Run time
log_lines <- readLines("GN9.log")
last_line <- log_lines[length(log_lines)]
