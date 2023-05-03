This is the list of steps that one would require to run the RNA-seq workflow without getting into too much detail about each step. To understand each step in-depth, please proceed to the next page.

1. Open Galaxy and sign in with your username and password 
2. Upload your fastq files that you would like to run the RNA-seq analysis with
3. Upload the header, the gene annotation file and file with pathways that is provided with the workshop tutorial. If you are not following the tutorial, please navigate to the Galaxy tutorial to download the appropriate files
4. Navigate to the "Workflows" tab on the top of the Galaxy homepage
5. Next to the workflow named "RNA-seq analysis", click on the start button 
6. This will navigate you to the page to enter all the values to run this workflow. Here, you can either send all the output to the current history or make a new history
7. Under "Create a collection of input files" and "Flatten collection", select your fastq files from the dropdown menu
8. Under "KEGG pathways to plot", enter the file with the pathways in the dropdown menu
9. Under "header", enter the header file provided in the dropdown menu
10. Under "featureCounts", select your GFF3 file from the dropdown menu
11. Under "DESeq2", under the first factor under "Specify a factor name, e.g. effects_drug_x or cancer_markers" using the edit button and under that enter the factor level under "Specify a factor level, typical values could be 'tumor', 'normal', 'treated' or 'control'"
12. If you have more than one factor, repeat the same procedure in step 12 for every factor
13. Under "Annotate DESeq2/DEXSeq output tables", select your GFF3 file from the dropdown menu
14. Scroll to the top of the page and click on "Run workflow"
15. You have run your first workflow successfully on Galaxy
16. The end
