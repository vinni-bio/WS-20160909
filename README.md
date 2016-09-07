09/09/2016

# UH Bioinformatics Core Workshop Series:<br/>["An Introduction to Molecular Phylogenetic Inference"](http://uh-bioinformatics.github.io/training/details/phylogenetics/)

## CONTENTS
* [Lab 1](https://github.com/vinni-bio/WS-20160909#lab-1)
* [Lab 2](https://github.com/vinni-bio/WS-20160909#lab-2)
  1. [Homework on Maximum Parsimony](https://github.com/vinni-bio/WS-20160909#homework-questions-maximum-parsimony)
  2. [Homework on Distance-matrix methods](https://github.com/vinni-bio/WS-20160909#homework-questions-distance-matrix-methods)
  3. [Homework on Model Selection](https://github.com/vinni-bio/WS-20160909#homework-questions-model-selection)
  4. [Homework on Sequence Partition Analysis](https://github.com/vinni-bio/WS-20160909#homework-questions-partition-analysis)
* [Lab 3](https://github.com/vinni-bio/WS-20160909#lab-3)

## Lab 1

### Software required for the Lab 1:
* Text editor [TextWrangler](http://www.barebones.com/products/textwrangler/download.html) (Mac Os X) or [Notepad++](https://notepad-plus-plus.org/download/v6.9.2.html) (Windows)
* [MEGA 7.0](http://www.megasoftware.net/)
* [Sequence Matrix](http://gaurav.github.io/taxondna/) 

### A. Check the number of GenBank entrees for the group of interest (i.e., Bears)
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
[irbp-ursidae.fasta](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/irbp-ursidae.fasta)
4. In the search line, enter:<br/>
`“mitochondrion”[filter] AND "Ursidae"[ORGN] AND "Talbot SL"[Author] AND 1140[SLEN]`
5. Save sequences into 'fasta' file:</br> 
[cytb-ursidae.fasta](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/cytb-ursidae.fasta)

### C. Select the outgroup
1. Open **Resources** on the top menu
2. Go to **Sequence Analysis** and select **_BLAST (Basic Local Alignment Search Tool)_**
3. Press ![Nucleotide BLAST](https://blast.ncbi.nlm.nih.gov/images/nucleutide-blast-cover.png)
4. Enter the NCBI accession number for using *Ursus maritimus* as the query sequence:
`AY303843.1`
5. For search set, select **Nucleotide collection** and exclude `Ursidae` from the search
6. Press ![BLAST](https://blast.ncbi.nlm.nih.gov/images/blastButtonDown.jpg)
7. Scroll down through the BLAST results and select the appropriate outgroup sequence(s) with 100% query cover. For example, I chose:
`Panthera pardus` [AY525041.1](https://www.ncbi.nlm.nih.gov/nuccore/AY525041.1) (Leopard)
8. Save the outgroup sequence for *irbp* gene into the 'fasta' file:<br/>
[irbp-outgroup.fasta](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/irbp-outgroup.fasta)
9. Go to **Nucleotide database**
10. In the search line, enter:<br/>
`“mitochondrion”[filter] AND ”Panthera pardus"[ORGN] AND ”complete genome”[TITL]`
11. Open any item with the complete mitochondrion genome of *Panthera pardus* (e.g., [KP001507.1](https://www.ncbi.nlm.nih.gov/nuccore/KP001507.1))
12. Click **Change region shown** on the right side bar and select range from `15000` to `16500`. Click **update**.
13. Save the outgroup sequence for *cytb* gene into the 'fasta' file:<br/>
[cytb-outgroup.fasta](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/cytb-outgroup.fasta)

### D. Multiple sequence alignment with MUSCLE in MEGA 7.0
1. Open [MEGA 7.0](http://www.megasoftware.net/)
2. Open **Data** menu and select **Open a File** to open [cytb-ursidae.fasta](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/cytb-ursidae.fasta) file for the alignment
3. On the top, open **Edit** menu and select **Insert sequence from file** to add `cytb-outgroup.fasta`
4. Select all sequences `Ctr+A` and click **MUSCLE** icon on the top bar
5. Click **Compute**
6. Trim ends of the alignment with gaps
6. On the top, open **Data** menu and select **Export alignment** to save the results in:<br/>
[cytb.fasta](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/cytb.fasta)
7. REPEAT the same procedure with *irbp* gene:<br/>
[irbp.fasta](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/irbp.fasta)

### E. Sequence file format conversion
1. Open [Sequence Matrix](http://gaurav.github.io/taxondna/) program
2. Drag and drop [irbp.fasta](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/irbp.fasta) file to Sequence Matrix window 
3. Click **Use species names**
4. Export sequences in Nexus format ("naked" Nexus for GARLI):<br/>
[irbp.nex](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/irbp.nex) 
5. Export sequences as Phylip (RAxML)<br/>
[irbp.phy](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/irbp.phy)
6. In the top **File** menu, select **Clear all sequences**
6. Drag and drop [cytb.fasta](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/cytb.fasta) file to Sequence Matrix window
7. Click **Use species names**
8. Export sequences in Nexus format ("naked" Nexus for GARLI):<br/>
[cytb.nex](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/cytb.nex) 
9. Export sequences as Phylip (RAxML)<br/>
[cytb.phy](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/cytb.phy)
10. Drag and drop [irbp.fasta](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/irbp.fasta) file to Sequence Matrix window 
11. Export sequences in Nexus format ("naked" Nexus for GARLI):<br/>
[bears.nex](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/bears.nex) 
12. Export sequences as Phylip (RAxML)<br/>
[bears.phy](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/bears.phy)

### F. Check entrees for *irbp* protein in UniProt Database
1. Go to http://www.uniprot.org/
2. In the search line, enter:<br/>
`name:"interphotoreceptor retinoid binding"`
3. In the search line, enter:<br/>
`name:"interphotoreceptor retinoid binding” AND taxonomy:”Ursidae”`

## Lab 2

### Software required for the Lab 1:
* [MEGA 7.0](http://www.megasoftware.net/)
* [jModelTest  v2.1.10](https://drive.google.com/drive/folders/0ByrkKOPtF_n_OUs3d0dNcnJPYXM)
* [PartitionFinder v.1.1.1](http://www.robertlanfear.com/partitionfinder/)
* [MrBayes v.3.2.6](http://mrbayes.sourceforge.net/download.php)
* [FigTree v.1.4.2](http://tree.bio.ed.ac.uk/software/figtree/)
* [RAXML v8.2.4](https://github.com/stamatak/standard-RAxML)(Optional)

### A. Import concatenated alignment file to MEGA 7.0
1. Open [MEGA 7.0](http://www.megasoftware.net/)
2. Open top **File** meny and select **Convert file format to MEGA** 
3. Select [bears.nex](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/bears.nex)
4. Save new file as [bears.meg](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB2/bears.meg) 
5. Quit from **MEGA _File Editor and Format Converter_**
6. Open **Data** menu and select **Open a File** to open [bears.meg](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB2/bears.meg) 


### B. Maximum Parsimony analysis (MP)
1. Open **Phylogeny** menu and select **Construct/Test Maximum Parsimony Tree** 
2. Set **bootstrap test** with *100 replicates*
3. Set **gaps** for *complete deletion*
4. Set **SPR** as tree search method
5. Run the analysis
6. After completion, root the tree with the outgroup
7. Save the tree as the image file in png format:
![Maximum Parsimony Tree](../master/LAB2/bears_parsimony.png)

#### HOMEWORK QUESTIONS (Maximum Parsimony):
  * Does the original tree differ from the bootstrap consensus tree?
  * Run the MP analysis with the larger number of bootstrap replications. How did the bootstrap support values change?
  * Run the MP analysis using only 1st and 2nd codon positions. How did the tree topology and bootstrap support values change?
  * Run the MP analysis with different tree search methods. Did the tree topology and bootstrap support values change?
  * Run the MP analysis for two genes separately (open *.fasta files). Does the tree topology differ between the two genes?

### C. Neighbor-Joining test in MEGA 7.0
1. Open **Phylogeny** menu and select **Construct/Test Neighbor-Joining Tree** 
2. Set **bootstrap test** with 100 replicates
3. Set **gaps** for complete deletion
4. Set **model** option to *p-distance*
5. Run the analysis
6. After completion, root the tree with the outgroup
7. Save the tree as the image file in png format:
![Maximum Parsimony Tree](../master/LAB2/bears_distance.png)

#### HOMEWORK QUESTIONS (Distance-matrix methods):
  * Does the original tree differ from the bootstrap consensus tree?
  * Run the NJ analysis with the larger number of bootstrap replications. How did the bootstrap support values change?
  * Run the NJ analysis using only 1st and 2nd codon positions. How did the tree topology and bootstrap support values change?
  * Run the NJ analysis with different substitution models. How did the tree topology and bootstrap support values change?
  * How does the tree topology differ between the corresponding NJ and MP trees?

### D. Model Selection with jModelTest
1. Start the program [jModelTest.jar](https://drive.google.com/drive/folders/0ByrkKOPtF_n_OUs3d0dNcnJPYXM)
2. Load the alignment file for *cytb* gene: [cytb.nex](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/cytb.nex)
3. In **Analysis** menu on the top, select **_Compute Likelihood scores_**
4. Select search through 7 substitution schemes and run the analysis
5. In **Analysis** menu on the top, select **AIC**, **AICc**, **BIC** or **DT** (you can do it by clicking on the menu of each criteria one after another)
6. In **Results** menu on the top, click **_Show results table_**
7. Sort the results by the column containing criterion scores 
8. Check the parameters of each selected model in the program console window
9. REPEAT the same procedure for *irbp* gene: [irbp.nex](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/irbp.nex)
 
#### HOMEWORK QUESTIONS (Model Selection):
  * Do all four criteria support the same model?
  * If not, check how chosen models differ from each other by comparing their parameters (use the table provided on the lecture slide).
  * Compare the model chosen by AICc with the model that has the closest AICc score to it. How strong is the difference between the models (check **delta**)? Which parameters are different between these two models?
  * Which model would you choose for the following phylogenetic inference? Explain why.
  * Do *irbp* and *cytb* genes have similar substitution models? If not, explain how they differ.

### E. Search for Sequence Partitions with [PartitionFinder](http://www.robertlanfear.com/partitionfinder/)
1. Open `PartitionFinderV1.1.1/examples/nucleotide/` folder and copy `partition_finder.cfg` to the folder with your alignment files
2. Open  `partition_finder.cfg` file in the text editor (e.g., TextWrangler)
3. Change the name of the alignment to `bears.phy`
4. Change the data block section as the following:
<pre><code>cytb_pos1 = 1-1140\3;
	cytb_pos2 = 2-1140\3;
	cytb_pos3 = 3-1140\3;
	irbp_pos1 = 1141-2420\3;
	irbp_pos2 = 1142-2420\3;
	irbp_pos3 = 1143-2420\3;</code></pre>
5. Save the file, leaving its original file name, in the folder with your alignment files:<br/>
[partition_finder.cfg](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB2/partition_finder.cfg)
6. Open Terminal (Mac) or Command Prompt (Windows)
7. Type `python `
8. Drag and drop `PartitionFinder.py` file to the terminal window and press space
9. Drag and drop the folder containing your alignment files and [partition_finder.cfg](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB2/partition_finder.cfg). <br/>Now your terminal command line should somewhat similar to:<br/>
`python /Users/vinni/Desktop/PartitionFinder.py /Users/vinni/Desktop/LAB2/`
10. Press **ENTER**
11. After analysis completion, you should see **analysis** folder within the folder containing your sequence files
12. Open [best_scheme.txt](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB2/best_scheme.txt) file in the text editor to see the results
13. Copy and save the RAxML partition section into a separate text file:<br/>
[partitions.txt](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB2/partitions.txt)

#### HOMEWORK QUESTIONS (Partition Analysis):
  * How many partitions have been revealed in your alignment data?
  * Do the partition models correspond with the models that you have obtained in the jModelTest analysis?
  
### F. Maximum Likelihood Analysis (ML) with RAxML
	
<p><b>Command line tutorial for RAxML:</b></p>
1. Type `raxmlHPC -help` to see the manual for all RAxML commands and settings 
2. Perform multiple ML searches for the best-scoring trees from parsimony inference:<br/>
`raxmlHPC -s bears.phy -q partitions.txt -m GTRGAMMA -p 12345 -n bears_ML -# 20`
3. Conduct 100 bootstrap searches:</br>
`raxmlHPC -s bears.phy -q partitions.txt -m GTRGAMMA -p 12345 -b 12345 -n bears_boot -# 100`
4. Draw bipartitions from bootstrap analysis on the ML tree:<br/>
`raxmlHPC -f b -t RAxML_bestTree.bears_ML -z RAxML_bootstrap.bears_boot -m GTRGAMMA -p 12345 -n bears_final`
5. Open `RAxML_bipartitions.bears_final` in FigTree

<p><b>CIPRES tutorial for RAxML:</b></p>
1. Go to CIPRES portal: https://www.phylo.org
2. Click ![Use the CIPRES Science Gateway](http://www.phylo.org/images/interface/blue-button.png)
3. Click **_Proceed without Registering_**
4. Go to your **Data** folder and click **Upload/Enter Data** button
5. Upload your [bears.phy](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/bears.phy) and [partitions.txt](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB2/partitions.txt) files
6. Go to your **Task** folder and click **Create New Task**
7. Select [bears.phy](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/bears.phy) as your input data
8. Select **RAxML-HPC v.8 on XSEDE** as your tool
9. In **Simple parameters** section:
	* Set the name for search output: `bears_ML`
	* Select the file with sequence partitions (-q): `partitions.txt`
10. In **Advanced parameters** section, go to **Configure the Analysis**:
	* Click on specify the number of alternative runs on distinct starting trees
	* Enter the number of alternative runs: `20`
11. Provide the name for your task (e.g., BEARS-ML) and click **Save and Run Task**
12. Click **Create New Task**
13. Select [bears.phy](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/bears.phy) as your input data
14. Select **RAxML-HPC v.8 on XSEDE** as your tool
15. In **Simple parameters** section:
	* Set the name for search output: `bears_boot`
	* Select the file with sequence partitions (-q): `partitions.txt`
16. In **Advanced parameters** section, go to **Configure Bootstrapping**:
	* Select **Non-parametric Boostrapping (-b)**
	* Enter the appropriate number of bootstrap iterations (or leave it as a default): `100`
17. Provide the name for your task (e.g., BEARS-BOOTSTRAP) and click **Save and Run Task**
18. Download `RAxML_bestTree.bears_ML` and `RAxML_bootstrap.bears_boot` files
19. Go to your **Data** folder and click **Upload/Enter Data** button
20. Upload `RAxML_bestTree.bears_ML` and `RAxML_bootstrap.bears_boot` files
21. Go to your **Task** folder and click **Create New Task**
22. Select [bears.phy](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB1/bears.phy) as your input data
23. Select **RAxML-HPC v.8 on XSEDE** as your tool
24. In **Simple parameters** section:
	* Set the name for search output: `bears_final`
	* Supply a tree (-t): `RAxML_bestTree.bears_ML`
25. In **Advanced parameters** section, go to ** Configure the Analysis**:
	* Select the Analysis type: `Draw bipartitions onto a single tree topology (-f b)`
	* Select file with topologies for bipartitions (-z): `RAxML_bootstrap.bears_boot`
26. Provide the name for your task (e.g., BEARS-FINAL) and click **Save and Run Task**
27. Download and open [RAxML_bipartitions.bears_final](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB2/RAxML_bipartitions.bears_final.txt) in FigTree <br/>
![ML tree reconstructed with RAxML](../master/LAB2/bears_ML.png)

### Bayesian analysis with MrBayes
1. Go to the folder with your multiple sequence alignments:
	* for Mac users: Open terminal and type `cd <path_to_your_folder>
	* for Windows users: 
2. Start MrBayes program by typing `mb` in Mac Os terminal or by executing mrbayes.exe program in Windows
3. To read the help menu, type `MrBayes > help`
4. Read the file with multiple sequence alignment:<br/>
`MrBayes > execute LAB2/bears.nex`
5. Define gene partitions in your sequences:
<pre><code>MrBayes > charset cytb = 1-1140
MrBayes > charset irbp = 1141-2420 
MrBayes > partition by_gene = 2: cytb,irbp
MrBayes > set partition = by_gene</code></pre>
6. Check the default model settings:<br/>
`MrBayes > showmodel`<br/>
or<br/>
`MrBayes > help lset`
7. Change the model settings for each partition:
<pre><code>MrBayes > lset applyto=(1) code=vertmt nst=2 rates=gamma
MrBayes > lset applyto=(2) nst=2 rates=gamma</code></pre>
8. Check the default prior settings:<br/>
`MrBayes > help prset`
9. Change the prior settings for each partition:<br/>
<pre><code>MrBayes > unlink statefreq=(all) shape=(all) revmat=(all)
MrBayes > prset applyto=(1) shapepr = exponential(10.0)</code></pre>
10. Check the default mcmc settings:<br/>
`MrBayes > help mcmcp`
11. Change the mcmc settings
`MrBayes > mcmcp ngen=1000000 nruns=2 nchains=2 samplefreq=200 burninfrac=0.2`
12. Run the mcmc search:<br/>
`MrBayes > mcmc`
13. Summarize the mcmc search information and build the tree:
<pre><code>MrBayes > sump
MrBayes > sump</code></pre>
14. Quit the MrBayes program<br/>
`MrBayes > quit`
15. Open consensus tree [bears.nex.con.tre](https://raw.githubusercontent.com/vinni-bio/WS-20160909/master/LAB2/bears.nex.con.tre) in FigTree
![Bayesian tree reconstructed with MrBayes](../master/LAB2/bears_BA.png)











