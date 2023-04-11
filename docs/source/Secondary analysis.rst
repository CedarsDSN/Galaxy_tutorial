**Secondary Analysis**
======================

At this stage, the reads have been filtered by quality and adapters have been trimmed, they are ready to be aligned to a genome in order to assess which genes they originate from. However, the genome is not always available and have to use a reference genome which is a representative example of the set of genes in a particular species. However, one has to keep in mind that these geoes do not accurately represent all the set of genes in one single organism. They act as a skeleton on which new genomes are built. For alignment in this tutorial, RNA STAR is used and can align the reads to a reference genome and output BAM files or gene count files which can then be provided to quantification tool which can output gene level table which can be used for downstream analysis.

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

The output of MultiQC on RNA STAR results should contain a webpage which can be accessed from the history and downloaded to be viewed -

* A table on the webpage gives the statistics of alignment with the percentage of uniquely mapped reads along with the number 

* A plot gives the amount of reads uniquely mapped, mapped to multiple loci, mapped to too many loci, unmapped because of being too short and unmapped generally



Quantification of reads
=======================

Both STAR and FeatureCounts can be used to quantify and obtain gene level quantification of expression. We will use FeatureCounts here. As compared to STAR, featureCounts offers more customization on how to count reads such as counting reads instead if fragments, counting transcripts instead of genes and minimum mapping quality. Before carrying out quantification, it's important to determine the strandedness of your samples. Reach out to your sequencing facility to determine the strandedness of your samples.

For workflow users -

* Expand the featureCounts part in the workflow 

* The default value under "Specify strand information" is "Unstranded" and can be changed by using the edit button next to "Specify strand information"

* A Gene annotation file is required and can be uploaded by using the "Upload Data" button on the left upperhand side of the page

* The file should appear in the history and can then be selected from the dropdown menu of Gene annotation file

* The output format default is "Gene-ID "\t" read-count (MultiQC/DESeq2/edgeR/limma-voom compatible)" and can be edited using the edit button

* We would also need a gene length file for downstream analysis which is selected as true



For users running each step -

* On the left hand side of homepage, search for "featureCounts" and open up the tool

* Select the output of RNA STAR (RNA STAR on collection N: mapped.bam) from the dropdown list under "Alignment file"

* Depending on whether your samples were stranded or unstranded, select it from the dropdown menu

* Upload a gene annotation file for the genome you are working with using the "Upload Data" button on the left upperhand side of the page

* The file should appear in the history and can then be selected from the dropdown menu of Gene annotation file

* Under "Output format", specify the format as "Gene-ID "\t" read-count (MultiQC/DESeq2/edgeR/limma-voom compatible)"

* Select "Yes" under "Create gene-length file"

* Under "Options for paired-end reads", select "Enabled; fragments (or templates) will be counted instead of reads" under "Count fragments instead of reads" (This is the format you need for downstream analysis)

* Set "Minimum mapping quality per read" as 10 under "Read filtering options"

* Under "Advanced options", select "exon" under "GFF feature type filter"

* Set "gene_id" as the "GFF gene identifier"

* Select "Disabled; reads that align to multiple features or overlapping features are excluded" under "Allow reads to map to multiple features"

* Click "Run" to run the tool

MultiQC can be run on featureCounts output and is optional. In order to run MultiQC -

* Under "Results" > "Insert Results" > select "featureCounts" for "Which tool was used to generate logs?"

* Select "featureCounts on collection N: Summary" (the output of featureCounts) under "Output of FeatureCounts"

The output of MultiQC on featureCounts results should contain a webpage which can be accessed from the history and downloaded to be viewed. At this stage, you are done with the primary analysis workflow and are ready with the expression table with which you can work with the secondary analysis workflow.
