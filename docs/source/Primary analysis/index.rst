
**Primary analysis**
====================

The initial step in every next-generation sequencing experiment should be to check the sequencing quality of the reads before doing any secondary or tertiary analysis. The quality of the data is important in order to trust the biological conclusions that can be drawn. During any kind of sequencing, some errors could be introduced, mostly incorrect nucleotides being called. These errors could bias the analysis and lead to improper interpretation of the data. Most NGS technologies use adapters and trimming these could improve the quality of the data.

.. note::

  Users of the quick start can use this part to download the gtf/ggf3 annotation file which is required for the workflow. 
  
  1. Go to `Ensembl <http://www.ensembl.org/index.html>`_ or `UCSC <https://hgdownload.soe.ucsc.edu/downloads.html>`_
  
  2. Enter your species of interest in the search button if you are using Ensembl or use the genome you're interested in UCSC
  
  3. Download the GFF3 file / GTF file. Most of the times, it would be gzipped
  
  4. If you're using a Mac device, double click and this would expand the file and this would make it as gtf or gff3 file
  
  5. If you're using a Windows device, use the putty terminal and type "gunzip name_of_the_gff3/gtf_file"
  
  6. You can now use the upload button on the left hand corner of the page to upload this gff3/gtf file

The Galaxy workflow uses FastQC for quality checks and assessments. For paired-end RNA samples in the Cedars Galaxy workflow, the read files are provided as a paired collection. Below are listed steps to convert fastq files to a format that can be provided to the workflow. Before you start, create a history for your work. The history is always on the right side and can be renamed by clicking on history and entering a custom name such as "RNA-Seq analysis" -

* Upload all your fastq files using the "Upload data" on the left upperhand corner on the Galaxy homepage

* Click on "Operations on multiple datasets" at the top of the history panel which is on the right hand side

* These files should appear in your history on the right hand side. Check all those that you would like to include in your analysis like below

.. image:: /images/Naming_datasets.png
   :width: 200
   :height: 275
   :alt: Choosing datasets

* Click "For all selected" and choose "Build List of Dataset Pairs"

* In the new panel that appears, rename the text of unpaired forward to a common selector for forward reads and do the same for reverse reads

* Click "Pair" these datasets for each valid forward and reverse pair

* Enter a name for the collection and click "Create List" to build the collection

* To lock the changes, click on the checkmark icon on the top of the history

Below are the links to perform quality checks, and process and trim raw reads -



.. toctree::

   Quality check and read processing
   Trimming raw reads
