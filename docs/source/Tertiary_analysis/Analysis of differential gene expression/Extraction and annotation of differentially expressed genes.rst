Extraction and annotation of differentially expressed genes
===========================================================


You have now conducted differential expression analysis and can now explore your data further. In the summary table outputted by DESeq2, suppose you would like to extract the most differentially expressed genes with a fold change greater than a certain value and the adjusted p-value above a certain threshold. This would be able to extract the most significantly differentially expressed genes. On this page, we are basically creating a file that can be used downstream.
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

.. note::

  This is the **Header** file for those that are running the Quick start

.. code-block:: RST

  GeneID	Base mean	log2(FC)	StdErr	Wald-Stats	P-value	P-adj	Chromosome	Start	End	Strand	Feature	Gene name
  

* Change the name of the dataset from "New file" to "header"

* Change the type from "Auto-detect" to "tabular"

* Press Start and close the window

For users running the workflow, you can read further down this page if you would like to know how the other tools work and what they do (This will also show you the default parameters)

For users running each step or running the secondary analysis seperately, the steps are delineated below -

The first tool that is used is "Filter data on any column using simple expressions"

* This tool is used to extract genes with. significant change in gene expression (adjusted p-value < 0.05) between two levels of a factor (treated and untreated samples)

* Search for the tool under "Tools" 

* Select the output from DESeq2 from history under "Filter"

* Under "With following condition", input "c7<0.05" (Filter the file on the seventh column with threshold of 0.05 where the column represents adjusted p-value)

* Click on "Execute"

* Rename the file as "Genes with significant adj p-value"

The second tool that that will be used is "Filter"

* This tool is used to select only the genes with a fold change (FC) > 2 or FC < 0.5 (or log2 FC >1)

* Select for the tool under "Tools"

* Select the file "Genes with significant adj p-value" under "Filter"

* Under "With following condition", input "abs(c3)>1" (Filter the file on the absolute value of the third column which is the log2 FC with threshold of 1)

* Click on execute

The next tool that is used is "Annotate DESeq2/DEXSeq output tables"

* Before running this tool, upload your Ensembl gene annotation (GFF/GTF format) for the organism you are working with into the current history

* Select for "Annotate DESeq2/DEXSeq output tables" tool under "Tools"

* Select the output of "Filter" under "Tabular output of DESeq2/edgeR/limma/DEXSeq"

* Select "DESeq2/edgeR/limma" under "Input file type"

* Select the gene annotation file under "Reference annotation in GFF/GTF format"

* Click on execute

"Concatenate datasets" is the next tool that is used

* Before executing this tool, a header has to be added to the annotated DESeq2 file so that downstream tools can use it

* The steps to make a new file which has the columns of the header are at the top of this page 

* Once the header is created, select "Concatenate datasets" under tools

* Under "Concatenate dataset", select the header dataset

* Under "Dataset", click on "Insert dataset"

* Under "Select", select the output of "Annotate DESeq2/DEXSeq output tables"

* Rename the output to "Genes with significant adj p-value & abs(log2(FC)) > 1"


