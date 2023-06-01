Quality check and read processing
=================================
  

Let's start with the first step of Primary analysis which is conducting a Quality check and read processing. Through the steps, this tutorial will explain the meaning of each step, the inputs and outputs which will be useful if you are running each step seperately or running the workflow. 

For users of the workflow, let's start with the "RNA-seq Primary analysis" workflow. 

* From the homepage, navigate to "Workflow" and scroll down to "RNA-seq Primary analysis"

* Provide the collection of fastq files that you created in the previous step from the dropdown menu under "Flatten collection" and "Create a collection of input files". This step is just providing input to the tools within the workflow

* The tool that will run the first step i.e. Quality check is FastQC and you don't have to provide any values under FastQC. We will be using the default values

For users running each step - 

* The paired dataset collection created in the previous step can be provided to the tool - FastQC, but only after converting the list of pairs into a simple list

* The flatten collection tool is pre-installed in Galaxy and can be used to convert the output for FastQC

* In the drop-down menu for "Flatten collection" tool, provide the paired dataset collection

* Run the tool and the output automatically saves to the history and can be easily provided to the FastQC tool

* Find FastQC in the toolshed on the left handside and launch the tool

* Provide the output of "Flatten collection" tool to the FastQC tool and run


Output of FastQC -


HTML file can be viewed after downloading it from the history. Below are all the information and plots that one can expect from the FastQ HTML report -

* Basic statistics - This is exactly what it says, all basic statistics about your fastq samples which includes but not limited to total number of sequences, sequence length and GC%

* Various plots showing per sequence quality scores, per base sequence content, per sequence GC content, per base N content, sequence duplication levels and adapter content. One of the plot below shows the per base sequence quality

.. figure:: /images/fastqc_sequence_quality.png
   :alt: fastqc plot
   
   Figure showing the per base sequence quality of a sample in the FastQC HTML report
