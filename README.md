# Assembly-to-Taxonomy-Pipeline
This pipeline automates the process of assembling bacterial genomes from raw sequencing reads, classifying them taxonomically, assessing quality, and uploading results to a container for downstream analysis. 

It consists of four main steps:

## Genome Assembly

Uses fastp for read preprocessing and Unicycler for hybrid assembly.
Controlled via Assembly_pip.py, which processes metadata and manages assembly tasks.

## Taxonomic Classification (GTDB-Tk)

Classifies assembled genomes using the GTDB-Tk classify_wf workflow.
Outputs a summary file with GTDB taxonomy assignments.

## Quality Assessment (CheckM)

Runs CheckM lineage_wf to evaluate genome completeness and contamination.
Generates a tabular QA report for all assemblies.

## Result Upload

Executes Upload_AssemblyRun_to_Container.py to store outputs in a designated container for further use.

### Key Features:

* Modular design using separate Conda environments for each tool.
* Metadata-driven execution for reproducibility.
* Automated renaming and organization of output files.
* Scalable with configurable thread usage.
