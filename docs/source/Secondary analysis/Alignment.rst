Alignment
=========

For workflow users, three reference genomes are available - Homo sapiens (hg38), Mus musculus (mm10) and Drosophila melanogaster (dm6). If you want to add your own reference genome, please contact the Data Navigation Team (DSN) in the Computational Biomedicine Team at Cedars-Sinai medical center. If working with one of the provided genomes, dm6 is the default genome and can be changed within the workflow. If you want to change the genome you are working with -

* Expand the "RNA STAR" component of the workflow and click on the edit button next to "Select reference genome" and a dropdown will appear

* Select the genome that you want to work with and click the edit button again and it should save the genome that you want to work with

For users running each step -
The Galaxy instance at the time of writing this tutorial has three genomes - Homo sapiens (hg38), Mus musculus (mm10) and Drosophila melanogaster (dm6). If you want to add your own reference genome, please contact the Data Navigation Team (DSN) in the Computational Biomedicine Team at Cedars-Sinai medical center. The steps to follow if working with one of the three genomes are -

* Select "Paired-end collection" under "Single-end or paired-end reads" and provide the output of Cutadapt from the dropdown list

* Under "Custom or built-in reference genome", select "Use a built-in index" and under "Reference genome with or without an annotation, select "use genome reference with builtin gene-model"

* Select the genome that you are working with (Homo sapiens (hg38), Mus musculus (mm10) and Drosophila melanogaster (dm6)) from the dropdown menu

* To obtain gene level counts, select "Per gene read counts" under "Per gene/transcript counts

* The gene level counts will be then provided to next tool, FeatureCounts

MultiQC can be run on RNA STAR output and is optional. In order to run MultiQC -

* Under "Results" > "Insert Results" > select "STAR" for "Which tool was used to generate logs?"

* In "STAR output" > "Insert STAR output" > "Type of STAR output > "Log"

* Select your STAR log output - "RNA STAR on collection N: log" 

After running STAR, a STAR log report like this shows that alignment has completed -

.. image:: /images/STAR_report.png
   :width: 250
   :height: 300
   :alt: STAR report

The output of MultiQC on RNA STAR results should contain a webpage which can be accessed from the history and downloaded to be viewed -

* A table on the webpage gives the statistics of alignment with the percentage of uniquely mapped reads along with the number 

* A plot gives the amount of reads uniquely mapped, mapped to multiple loci, mapped to too many loci, unmapped because of being too short and unmapped generally
