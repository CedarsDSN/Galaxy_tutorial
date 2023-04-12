Extraction and annotation of differentially expressed genes
===========================================================


You have now conducted differential expression analysis and can now explore your data further. In the summary table outputted by DESeq2, suppose you would like to extract the most differentially expressed genes with a fold change greater than a certain value and the adjusted p-value above a certain threshold. This would be able to extract the most significantly differentially expressed genes. 
For users that are running the workflow, these are the tools that would output a table with significantly differentially expressed genes -

* Filter data on any column using simple expressions

* Filter

* Annotate DESeq2/DEXSeq output tables

* Attaching a header to the DESeq2 output

* Concatenate datasets

At this stage, the user only has to enter a file for the fourth step - "Attaching a header to the DESeq2 output". After the DESeq2 annotated tables have been generated, they do not contain column names. The tables need to have column names in order to be used by the tools that use them next. The steps to add a header to the annotated DESeq2 table are as follows-

* Open the Upload data manager by clicking on "Upload data" on the left hand side

* Select "Paste/Fetch data"

* Paste the file contents attached here into the text field 

.. code-block:: RST

  GeneID	Base mean	log2(FC)	StdErr	Wald-Stats	P-value	P-adj	Chromosome	Start	End	Strand	Feature	Gene name
  

* Change the name of the dataset from "New file" to "header"

* Change the type from "Auto-detect" to "tabular"

* Press Start and close the window
