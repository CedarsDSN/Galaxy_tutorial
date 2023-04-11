**Primary analysis**
====================

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



Quality check and read processing
=================================
  

Let's start with the first step of Primary analysis which is conducting a Quality check and read processing. Once the paired dataset collection is created, this has to be converted from a list of pairs into a simple list to be able to be provided to the FastQC tool which is for quality check of the sequence data. You are now ready to start using the RNA-Seq workflow instead of running each step seperately. Through the steps, this tutorial will explain the meaning of each step, the inputs and outputs which will be useful if you are running each step seperately or running the workflow.

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

* Basic statistics - This is exactly what it says, all basic statistics about your fastq samples which includes but not limited to total number of sequences, sequence length and GC%

* Various plots showing per sequence quality scores, per base sequence content, per sequence GC content, per base N content, sequence duplication levels and adapter content


Trimming raw reads
==================

Reads should be trimmed to get rid of bases that were sequenced with high uncertainty and also remove the reads of overall bad quality. During the library preparation steps, adaptors are attached to the sequence ends that serve a purpose when sequencing. These adaptors also need to be removed before any processing. There has been quite a lot of debates as to whether adaptor and quality trimming are required when carrying quantification of RNA-Seq reads. It has been shown in previous studies that performing trimming in RNA-Seq analysis leads to decrease in number of reads, while increasing the proportion of mapped reads. Researchers also indicate that aggressive trimming can negatively impact any secondary and tertiary analysis conducted. Further, the quality of the dataset also determines whether quality trimming is required. Higher the quality of RNA-Seq dataset, lower the impact of quality trimming. For this tutorial, the "Cutadapt" tool is used to carry out adapter and quality trimming.


For workflow users - The Galaxy workflow doesn't allow you to select "Single-end" or "Paired-end" reads. The way that is it set up within a workflow doesn't give you the option to select the kind of analysis you need. The default is "Paired-end collection" as used in the original RNA-Seq Galaxy tutorial. All other settings are default and no user input has to be entered at this step. For further explanation of the default parameters, they are explained below for users that are running each step seperately. The Cutadapt step in the workflow can be run in default and nothing has to be entered.

For users running each step - 
Cutadapt tool is used but there are other tools too such as Trimmomatic, BBDuk, TrimGalore. Here are the steps to run Cutadapt as part of running the pipeline not as part of the workflow -

* On the left hand side of homepage, search for "CutAdapt" and open up the tool

* Select whether your sequences are single-ended, pair-ended or a pair-ended collection (Paired-end collection if you followed the steps in the "Processing raw data")

* In "Filter options", enter 20 under "Minimum length (R1)" which specifies the miminum length that the adapter needs to be in order to be trimmed

* In "Read Modification options", enter 20 under "Quality cutoff"  

* In "Output selector" option, select "Report: Cutadapt's per-adapter statistics" which can be provided to MultiQC tool

* Click "Run"

* The output of Cutadapt will show up in the history section on the right hand side

The next step is optional, but can be run to get more insights into your sample quality and whether adapter trimming has worked optimally. Here are the steps for the same -

* On the left side of the homepage, search for "MultiQC" and open up the tool

* Under "Results" > "Insert Results" > Select "Cutadapt/TrimGalore!" under "Which tool was used to generate logs?"

* Under "Output of Cutadapt", select Cutadapt on Collection N: Report" where N is the output of Cutadapt and should show up in the dropdown menu since the output of Cutadapt is stored in the history

* Click "Run"


The output of MultiQC on Cutadapt results should contain a webpage which can be accessed from the history and downloaded to be viewed -

* The first table on the webpage shows the percentage of the basepairs which have been trimmed by Cutadapt

* The plot below that shows the number of reads (SE) / pairs (PE) which have been removed by Cutadapt


You are now ready to go to the next step, Alignment/mapping
