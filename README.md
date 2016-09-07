09/09/2016

# UH Bioinformatics Core Workshop Series:
!["An Introduction to Molecular Phylogenetic Inference"](http://uh-bioinformatics.github.io/img/workshops/phylogeny_logo.png)

## Lab 1

### Software required for the lab:
* Text editor [TextWrangler](http://www.barebones.com/products/textwrangler/download.html) (Mac Os X) or [Notepad++](https://notepad-plus-plus.org/download/v6.9.2.html) (Windows)
* [MEGA 7.0](http://www.megasoftware.net/)
* [Sequence Matrix](http://gaurav.github.io/taxondna/) 

### A. Check the number of GenBank entrees for the group of interest (Bears)
1. Go to http://www.ncbi.nlm.nih.gov
2. Find and click **All Resources** button in the left side bar
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
3. Save sequences into 'fasta' file :<br/>
[ursidae-irbp.fasta](../blob/master/LAB1/irbp-ursidae.fasta)
4. In the search line, enter:<br/>
`“mitochondrion”[filter] AND "Ursidae"[ORGN] AND "Talbot SL"[Author] AND 1140[SLEN]`
5. Save sequences into 'fasta' file:</br> 
[ursidae-cytb.fasta](../blob/master/LAB1/cytb-ursidae.fasta)

### C. Select the outgroup
1. Open **Resources** on the top menu
2. Go to **Sequence Analysis** and select **_BLAST (Basic Local Alignment Search Tool)_**
3. Press ![Nucleotide BLAST](https://blast.ncbi.nlm.nih.gov/images/nucleutide-blast-cover.png)
4. Enter the NCBI accession number for Ursus maritimus as the query sequence:
`AY303843.1`
5. For search set, select **Nucleotide collection** and exclude `Ursidae` from the search
6. Press ![BLAST](https://blast.ncbi.nlm.nih.gov/images/blastButtonDown.jpg)
7. Scroll down through the BLAST results and select the appropriate outgroup sequence(s) with 100% query cover. For example, I chose:
`Panthera pardus` [AY525041.1](https://www.ncbi.nlm.nih.gov/nuccore/AY525041.1) (Leopard)
8. Save the outgroup sequence into the 'fasta' file:<br/>
[irbp-outgroup.fasta](../blob/master/LAB1/irbp-outgroup.fasta)
9. Go to **Nucleotide database**
10. In the search line, enter:<br/>
`“mitochondrion”[filter] AND ”Panthera pardus"[ORGN] AND ”complete genome”[TITL]`
11. Open any item with the complete mitochondrion genome of Panthera pardus (e.g., [KP001507.1](https://www.ncbi.nlm.nih.gov/nuccore/KP001507.1)
12. Click **Change region show** on the right side bar and select range from 15000 to 16500
13. Save the outgroup sequence into the 'fasta' file:<br/>
[cytb-outgroup.fasta](../blob/master/LAB1/cytb-outgroup.fasta)