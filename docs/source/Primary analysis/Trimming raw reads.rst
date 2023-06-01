Trimming raw reads
==================

Reads should be trimmed to get rid of bases that were sequenced with high uncertainty and also remove the reads of overall bad quality. During the library preparation steps, adaptors are attached to the sequence ends that serve a purpose when sequencing. These adaptors also need to be removed before any processing. There has been quite a lot of debates as to whether adaptor and quality trimming are required when carrying quantification of RNA-Seq reads. For this tutorial, the "Cutadapt" tool is used to carry out adapter and quality trimming.

For workflow users - 

* The Galaxy workflow doesn't allow you to select "Single-end" or "Paired-end" reads. The way that is it set up within a workflow doesn't give you the option to select the kind of analysis you need. The default is "Paired-end collection" as used in the original RNA-Seq Galaxy tutorial 

* All other settings are default and no user input has to be entered at this step. For further explanation of the default parameters, they are explained below for users that are running each step seperately

* The next tool i.e. MultiQC has default parameters and the user doesn't need to enter anything

.. figure:: /images/cutadapt.png
   :width: 800
   :height: 400
   :alt: Cutadapt input
   
   Cutadapt parameters within the "RNA-seq Primary Analysis" workflow
   
   
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
