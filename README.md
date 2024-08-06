This workflow is my attempt at modernizing, and generalizing existing viral infection detection pipelines. Using snakemake to implement computational scaling and parallelisation of analysis tasks.

## Pre Workflow setup
1. **Fill out the config.yaml**

2. **Fill out the samples.tsv**

3. **Run the snakemake command**

## Workflow Structure
1. **Metagenome Construction:**
    - Constructs a custom metagenome from multiple assemblies.
2. **Quality Control & Trimming:**
    - **fastp:** Trims and assesses quality of reads.
3. **Mapping:**
	1. **STAR First Pass:** Maps reads to the first assembly.
	2. **Extract Unmapped:** Extracts unmapped reads.
	3. **STAR Second Pass:** Maps unmapped reads to a custom metagenome.
4. **Data Processing:**
    - **featureCounts:** Counts features from the aligned BAM files.

## Detailed DAG of the rules
![](assets/dag.png)
