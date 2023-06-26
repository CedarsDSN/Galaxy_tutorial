**Files needed for RNA-seq workflows**
=====================================

There are two files needed for carrying out the RNA-seq workflows successfully. One is the header file needed to be concatenated to the DESeq2 annotation file. The other file needed is the KEGG pathway file used to run the pathview tool with KEGG pathways.

The header file is below. For users of Quick start Tertiary analysis or the Tertiary analysis - please copy paste the header file below and follow the instructions `here <https://galaxy-tutorial.readthedocs.io/en/latest/Supplementary%20files/Creating%20a%20data%20file/>`_

.. code-block:: RST

  GeneID	Base mean	log2(FC)	StdErr	Wald-Stats	P-value	P-adj	Chromosome	Start	End	Strand	Feature	Gene name

Remember to rename your file to "header"


The KEGG pathways file is below. For users of Quick start Tertiary analysis or the Tertiary analysis - please copy paste the header file below and follow the instructions `here <https://galaxy-tutorial.readthedocs.io/en/latest/Supplementary%20files/Creating%20a%20data%20file/>`_

.. code-block:: RST

  00010
  03040

Remember to rename your file to "KEGG pathway file"
