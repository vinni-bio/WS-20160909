09/09/2016

# Workshop: Introduction to Molecular Phylogenetic Inference 

## Lab 1

### A. Check the number of entrees for our group of interest
1. Go to http://www.ncbi.nlm.nih.gov
2. Click "All Resources" button in the left side bar
3. In the list of all databases, find and click "Nucleotide Database"
4. In the search line, enter:
`all[filter]`
5. On the left side bar, find 'Species' filter and click "customize"
6. Add and select:
`Ursidae`

### B. Download the dataset for the case study
1. Go to "Nucleotide database"
2. In the search line, enter:
`"Yu L"[AUTH] AND "Ursidae"[ORGN] AND "irbp"[TITL]`
3. Save sequences into: 
`ursidae-irbp.fasta`
4. In the search line, enter:
`“mitochondrion”[filter] AND "Ursidae"[ORGN] AND "Talbot SL"[Author] AND 1140[SLEN]`
5. Save sequences into: 
`ursidae-cytb.fasta`

### C.Selection of the outgroup:
1. Open 'Resources' top menu
2. Go to 'Sequence Analysis' and select 'BLAST (Basic Local Alignment Search Tool)'
3. Select 'Nucleotide BLAST'
4. Enter the NCBI accession number for Ursus maritimus:
`AY303843.1`
5. For search set, select 'Nucleotide collection' and exclude "Ursidae" from the search
6. Press "BLAST"
7. Scroll down through results and select the appropriate outgroup sequence(s) with 100% query cover. For example, I chose:
`Panthera pardus AY525041.1` (Leopard)
8. Click on the accession number to see the GenBank sequence record
9. If option is available, click the popset to see all other sequences from the same study.



