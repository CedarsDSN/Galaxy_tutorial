**Functional enrichment analysis of DE genes**
===============================================

Now, one would like to carry out pathway analysis which gives an idea of what specific processes/categories these transcripts are enriched in. Gene ontology (GO) is an oft-used method to assign the differentially expressed genes from a RNA-Seq workflow to a process/category and give context to a set of transcripts. 

The mission of the GO consortium is to develop a comprehensive, computational model of biological systems, ranging from the molecular level to the organism level, across the multiplicity of species in the tree of life (`reference <http://geneontology.org/>`_)
The three main categories of GO are Biological Process (BP), Cellular Component (CC) and Molecular Function (MF). To understand more of these sub-categories, please refer to the `paper <https://doi.org/10.1093/genetics/iyad031>`_. One tool that provides methods for performing GO analysis of RNA-Seq data while taking length bias into account is goseq. This tool needs 2 files as inputs -

* A tabular file with the differentially expressed genes from all genes assayed in the RNA-Seq experiment with 2 columns
  
  a. The Gene IDs (unique within the file), in uppercase letters
  
  b. A boolean indicating whether the gene is differentially expressed or not (True if differentially expressed or False if not)

* A file with information about the length of a gene to correct for potential length bias in differentially expressed genes

Kyoto Encyclopedia of Genes and Genomes (KEGG) pathway database is a collection of pathway maps representing current knowledge of molecular interaction, recation and relation networks. A map can integrate many entities including genes, proteins, RNAs, chemical compounds, glycans, and chemical reactions, as well as disease genes and drug targets. Along with GO categories, including in KEGG pathway information enriches the understanding of what pathways the genes belong to.

.. toctree::

   GO pathway analysis
   Annotation of goseq output
   KEGG pathway analysis
