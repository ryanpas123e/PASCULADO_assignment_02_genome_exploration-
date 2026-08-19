# PASCULADO_assignment_02_genome_exploration-
# Name: Pasculado, Mark Ryan T.
# Activity Title: Basic Genome Structure and Sequence Exploration Using Galaxy
# BIO 300 –B Cell and Molecular Biology Laboratory
# Species: Mus musculus ( house mouse) genome assembly (GCF_000001635.27)
# Objectives
- To describe the structure of a genome assembly using basic statistics, sequence-length filtering, and a small-scale open reading frame (ORF) exploration and learning to inspect and interpret an assembled genome.
# Tools used in Galaxy
# Part 1 — Genome Download
- Source: NCBI RefSeq
- Species: Mus musculus
- Assembly accession: GCF_000001635.27
- Assembly level: Chromosome
- File: Mus_musculus_genomic.fna
- Approximate file size: 2.8 GB
# Part 2 — Assembly Statistics
- Tool: gfastats
- Tool mode: Summary statistics generation
- Report mode: Genome assembly statistics (--nstar-report)
- Input file: Mus_musculus_genomic.fna
# Part 3 — Sequence-Length Structure
- Tool: Compute sequence length
- Input file: Mus_musculus_genomic.fna
- Purpose: To determine the length of each assembled sequence
- The resulting sequences were sorted by length in descending order using Galaxy's Sort tool to identify the top 5 longest sequences.
# Part 4 — Length-Filtering Experiment
- Step 1: Tool: Filter sequences by length
- Input file: Mus_musculus_genomic.fna
- Parameter: minimum length = 10,000 bp (10 kb)
- Output renamed to: Filtered_Genome_ge10kb_M.musculus
- Step 2
- Re-ran gfastats (same settings as Part 2) using input file: 5:Filtered_Genome_ge10kb_M.musculus
- Output renamed to: gfastats_on_M.musculus_filtered_genome
# Part 5 — Small ORF Exploration
- Step 1: Selected sequence/region
- Selected sequence: NC_000067.7
- Sequence length analyzed: 100,000 bp
- Step 2: Tool: getorf
- Input: NC_000067.7 selected 100,000-bp region
- Minimum nucleotide size of ORF to report: 300 bp
- Number of ORFs returned: 103
- Length of longest ORF: 1,494 bp
# Short Interpretation
- The Mus musculus assembly has a total length of approximately 2.73 Gb distributed across 61 scaffolds, with a high N50 of 130.53 Mb and an L50 of 9, indicating that much of the genome is contained in large chromosome-scale sequences. The 41.67% GC content represents the overall proportion of G and C bases in the assembly. Applying a 10 kb length filter removed only two short sequences and reduced the assembly by just 10,388 bp, while the N50 and GC content remained unchanged, showing that the short sequences contributed very little to the overall assembly. The small ORF exploration of the 100,000-bp NC_000067.7 region identified 103 potential ORFs, with the longest measuring 1,494 bp. These ORFs are only candidate coding regions and cannot be considered confirmed genes without additional supporting evidence.
