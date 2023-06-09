RNA-seq introduction
====================

Gene expression is a process where genes are transcribed to an RNA molecule and then eventually translated to form a protein product. Quantifying the expression of genes under a certain condition can be carried out using RNA-Sequencing (RNA-Seq). When a gene is expressed, it produces RNA molecules and the number of RNA molecules helps quantify the amount to which it is expressed.  There are different classes of RNA molecules, one of which is messenger RNA (mRNA), which enters into the cytoplasm from the nucleus where it is translated to the final protein product. For comparing two conditions, quantifying the number of transcripts can be a good indicator of the expression repertoire and help understand what genes are turned on or off between two circumstances. In RNA-Seq, one of the most important downstream analyses that are created is "Differential Expression analysis". When two conditions are compared, for example, treated vs. untreated, usually these are the factors to be compared in a study. DESeq2 is a tool that is used to carry out "Differential Expression analysis" and it is important to include all known factors that could affect gene expression.  

===========

With next-generation sequencing, the number of genes that can be profiled for expression levels has increased to tens of thousands. There are several steps in data analysis that have been refined over the years. This tutorial goes through the steps of RNA-Seq analysis mentioned below and is based on a Galaxy RNA-Seq tutorial -  
  - Primary analysis 
      * Processing raw data
      * Quality check and read processing
      * Trimming raw reads
  - Secondary analysis
      * Alignment
      * Quantification of reads
  - Tertiary analysis
      * Analysis of differential gene expression
        # Identification of differentially expressed features
        # Extraction and annotation of differentially expressed genes
        # Visualization of the expression of differentially expressed genes
      * Functional enrichment analysis of DE genes
        # Gene Ontology analysis
        # KEGG pathway analysis
This tutorial will go into the details of each step and the inputs and outputs for each step for the Galaxy workflow "RNA-Seq analysis".

**Important notes**:  

1. For users who need to run this tutorial with their data and need to run differential expression analysis, only run this "RNA-seq" workflow if you have two factors that you know can contribute to differences in gene expression (for example treatment  and sequencing type)

2. For users who have fewer or more factors that they think may affect the gene expression, it would be better to use the "RNA-Seq Primary analysis" workflow and then run the "RNA-Seq secondary analysis" workflow separately which is also explained in detail in this tutorial 

3. For all the workflows, until all the inputs have been entered and each step is discussed, do not  click on the "Run workflow" button

4. One more note for those conducting the secondary analysis - For the read names that you upload and use, name the sample as such "sample_name_factor1factorlevel_factor2factorlevel" and so on so that it can be used when submitting these samples to DESeq2 for differential expression analysis
