**Secondary Analysis**
======================

At this stage, the reads have been filtered by quality, and adapters have been trimmed; they are ready to be aligned to a genome in order to assess which genes they originate from. However, the genome is not always available and has to use a reference genome, a representative example of the set of genes in a particular species. However, one must keep in mind that these genes do not accurately represent all the sets of genes in one organism. They act as a skeleton on which new genomes are built. For alignment in this tutorial, RNA STAR is used. It can align the reads to a reference genome and output BAM files or gene count files, which can then be provided to the quantification tool, which can output a gene level table, which can be used for downstream analysis.

If you would like to learn in-depth about RNA-seq, this `tutorial <https://artbio.github.io/springday/cDNAs/>`_ developed by Galaxy goes into each step and explains along with examples. This tutorial also explains strandedness and how one should think of what they want to achieve before performing an RNA-seq analysis.


.. toctree::

   Alignment
   Quantification of reads
   Accessing results


