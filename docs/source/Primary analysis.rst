Primary analysis
================

The initial step in every next-generation sequencing experiment should be to check the sequencing quality of the reads before doing any secondary or tertiary analysis. The quality of the data is important in order to trust the biological conclusions that can be drawn. During any kind of sequencing, some errors could be introduced, mostly incorrect nucleotides being called. These errors could bias the analysis and lead to improper interpretation of the data. Most NGS technologies use adapters and trimming these could improve the quality of the data.
The Galaxy workflow uses FastQC for quality checks and assessments. For paired-end RNA samples in the Cedars Galaxy workflow, the read files are provided as a paired collection. Below are listed steps to convert fastq files to a format that can be provided to the workflow. Before you start, create a history for your work. The history is always on the right side and can be renamed by clicking on history and entering a custom name such as "RNA-Seq analysis" -

* Upload all your fastq files using the "Upload data" on the left upperhand corner on the Galaxy homepage

* Click on "Operations on multiple datasets" at the top of the history panel which is on the right hand side. 

* These files should appear in your history on the right hand side. Check all those that you would like to include in your analysis. 

* Click "For all selected" and choose "Build List of Dataset Pairs". 

* In the new panel that appears, rename the text of unpaired forward to a common selector for forward reads and do the same for reverse reads. 

* Click "Pair" these datasets for each valid forward and reverse pair. 

* Enter a name for the collection and click "Create List" to build the collection. 

* To lock the changes, click on the checkmark icon on the top of the history


1. Quality check and read processing

Once the paired dataset collection is created, this has to be converted from a list of pairs into a simple list to be able to be provided to the FastQC tool which is for quality check of the sequence data. You are now ready to start using the RNA-Seq workflow instead of running each step seperately. Through the steps, this tutorial will explain the meaning of each step, the inputs and outputs which will be useful if you are running each step seperately or running the workflow.

For those users that did not create a paired dataset collection, you can still select your list of files (just a simple list of your files in a collection, not paired) from the drop-down menu and the first tool in the workflow will create the paired collection. 
For users running each step - 

* The paired dataset collection can be provided to the next tool - FastQC, but only after converting the list of pairs into a simple list

* The flatten collection tool is pre-installed in Galaxy and can be used to convert the output for FastQC

* In the drop-down menu for "Flatten collection" tool, provide the paired dataset collection

* Run the tool and the output automatically saves to the history and can be easily provided to the FastQC tool

* Find FastQC in the toolshed on the left handside and launch the tool

* Provide the output of "Flatten collection" tool to the FastQC tool and run

Output of FastQC -


HTML file can be viewed after downloading it from the history. Below are all the information and plots that one can expect from the FastQ HTML report -
Basic statistics - This is exactly what it says, all basic statistics about your fastq samples which includes but not limited to total number of sequences, sequence length and GC%
Various plots showing per sequence quality scores, per base sequence content, per sequence GC content, per base N content, sequence duplication levels and adapter content
