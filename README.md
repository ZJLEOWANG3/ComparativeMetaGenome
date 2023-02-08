# ComparativeMetaGenome
This is the repository for Raman-Sorting Single-Cell Analysis of Minimetagenomics and Comparative Genomics

----
## :microbe: :sweat_drops: Minimetagenomics Ananlysis

Code is stored in ```./minimetagenomics/``` with scripts and Snakemake-enabled workflow to achieve
- **Assembly**
  - trim and QC by ```trimmomatic```
  - contigs assembly by ```SPAdes```
  - statistics of assembled contigs by ```quast```
  - filtration by ```anvio```
  
- **Mapping**
  - mapping trimmed reads to filtered contigs by ```bowtie2```
  - processing mapping results by ```samtools```
  - duplicates removal by ```picard```
  
- **Binning**
  - contigs binning by ```anvio``` and ```CONCOCT```
  - QC for bins by manual refinement and ```checkM```

- **Functional Analysis**
  - metagenome-assembled genome (MAG) recognized by ```gtdb-tk```
  - Gene Calling: ORFs identified by ```metagenemark``` and ```prodigal```
  - Gene Annotation: coding DNA sequences (CDSs) annotated by ```kofamscan```
  - Metabolic Pathway: KEGG

- **Taxonomy for MAG and others**
  - MAG 16S rRNA extracted by ```PROKKA```
  - MAG taxonomy identified by ```BLAST```
  - Other contigs taxnomy analyzed by ```Diamond``` 
  - Phylogenetic tree established by ```NCBI taxonomy tree```
  
-----
## :dna: :microscope: Comparative Genomic Analysis

- ***Genome-scale metabolic modeling (GEMs) establishement and curation***
  - Establish from ```.faa``` file using [CarveMe](https://carveme.readthedocs.io/en/latest/usage.html)
  - Improve and check quality of the GEM models using [MEMOTE](https://github.com/opencobra/memote)
  - Optimize and incorporate the *ppk* and *ppx* reactions into the GEMs if the genes are detected within the genome
using [COBRApy](https://cobrapy.readthedocs.io/en/latest/)

- ***Microbial metabolic & ecological interaction analysis ***
  - Microbial metabolic interaction based on GEMs using [SMETANA](https://github.com/cdanielmachado/smetana)

Code is stored in ```./compgenome/``` with workflow in JupyterNoteBook for comparative analysis, 

with file names labeled by figure number to achieve data mining, analysis, and visualization.

Figure 1 for pipeline and Figure 4 for PAO metabolic models are designed by Microsoft Powerpoint.

-----
## :toolbox: :computer: Operon Analysis

Online web server was applied based on ```Operon Mapper``` published in [Bioinformatics](https://academic.oup.com/bioinformatics/article/34/23/4118/5040321). 

This is applied with the aim to identify operon for *ppk* and *ppx*
