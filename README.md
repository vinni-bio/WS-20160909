09/09/2016

# UH Bioinformatics Core Workshop: <br/> "An Introduction to Molecular Phylogenetic Inference"

## Lab 1

### A. Check the number of GenBank entrees for our group of interest (Bears)
1. Go to http://www.ncbi.nlm.nih.gov
2. Find and click [All Resources](http://www.ncbi.nlm.nih.gov/guide/all/) button in the left side bar
3. In the list of all databases, find and click **Nucleotide Database**
4. In the search line, enter:
`all[filter]`
5. On the left side bar, find **_Species_** filter and click **customize** button
6. Add and select:
`Ursidae`

### B. Download the dataset for the case study
1. Go to **Nucleotide database**
2. In the search line, enter:
`"Yu L"[AUTH] AND "Ursidae"[ORGN] AND "irbp"[TITL]`
3. Save sequences into 'fasta' file : 
`ursidae-irbp.fasta`
4. In the search line, enter:
```“mitochondrion”[filter] AND "Ursidae"[ORGN] AND "Talbot SL"[Author] AND 1140[SLEN]```
5. Save sequences into 'fasta' file: 
`ursidae-cytb.fasta`

### C. Select the outgroup
1. Open 'Resources' top menu
2. Go to 'Sequence Analysis' and select 'BLAST (Basic Local Alignment Search Tool)'
3. Select 'Nucleotide BLAST'
4. Enter the NCBI accession number for Ursus maritimus:
`AY303843.1`
5. For search set, select 'Nucleotide collection' and exclude "Ursidae" from the search
6. Press "BLAST"
7. Scroll down through the BLAST results and select the appropriate outgroup sequence(s) with 100% query cover. For example, I chose:
`Panthera pardus AY525041.1` (Leopard)
8. Save the outgroup sequence into the 'fasta' file:




