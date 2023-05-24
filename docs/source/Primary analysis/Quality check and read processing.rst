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
