**Quick-start**
===============

**Primary analysis**


This is the list of steps that one would require to run the RNA-seq "Primary analysis" workflow without getting into too much detail about each step. To understand each step in-depth, please proceed to the next page.

1. Open Galaxy and sign in with your username and password 
2. Upload your fastq files that you would like to run the RNA-seq analysis with. If you would like to use an example dataset, please use these detailed `instructions <https://artbio.github.io/springday/uploads/>`_
3. Navigate to the "Workflows" tab on the top of the Galaxy homepage
4. Next to the workflow named "RNA-seq Primary analysis", click on the start button 
5. This will navigate you to the page to enter all the values to run this workflow. Here, you can either send all the output to the current history or make a new history
6. Under "Create a collection of input files" and "Flatten collection", select your collection of fastq files from the dropdown menu. To create a collection of your fastq files, refer to the step on `this <https://galaxy-tutorial.readthedocs.io/en/latest/Primary%20analysis/>`_ page
7. Under "featureCounts", select your gene annotation GFF3 from the dropdown menu
8. Scroll to the top of the page and click on "Run workflow"
9. You have successfully conducted primary and secondary analysis using "Primary analysis" workflow in Galaxy

**Tertiary analysis**


1. For the "RNA-seq Tertiary analysis" workflow, upload your counts file if you have them. If using the example datasets, you can import the counts from before using these `instructions <https://artbio.github.io/springday/count/>`_
2. Navigate to the workflows tab, and select the Run button for "RNA-seq Tertiary analysis" workflow to open the workflow and select datasets
3. You need a header for this workflow. Get a header file from `here <https://galaxy-tutorial.readthedocs.io/en/latest/Analysis%20of%20Differential%20gene%20expression/Expression%20and%20annotation%20of%20differentially%20expressed%20genes/>`_ Under "header", enter the header file provided in the dropdown menu
4. You need a list of KEGG pathways for this workflow. Get a KEGG pathway file from `here <https://training.galaxyproject.org/training-material/topics/transcriptomics/tutorials/ref-based/tutorial.html#functional-enrichment-analysis-of-the-de-genes>`_
5. Under "DESeq2", under the first factor under "Specify a factor name, e.g. effects_drug_x or cancer_markers" using the edit button and under that enter the factor level under "Specify a factor level, typical values could be 'tumor', 'normal', 'treated' or 'control'"
6. If you have more than one factor, repeat the same procedure in step 12 for every factor
7. Under "Annotate DESeq2/DEXSeq output tables", select your GFF3 file from the dropdown menu
8. Scroll to the top of the page and click on "Run workflow"
9. You have run the tertiary workflow successfully on Galaxy
