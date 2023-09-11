**Identification of differentially expressed genes**
====================================================

If you want to learn more about the DESeq2 model and how it works, please refer to the `paper <https://genomebiology.biomedcentral.com/articles/10.1186/s13059-014-0550-8>`_. The Galaxy DESeq2 tool is designed to accept as many factors as the user wants to add, along with levels for each factor. For example, a factor could be treatment and the factor levels could be treated and un-treated. Moving forward from the count table obtained from featureCounts, the table needs to be in a format that can be understood by DESeq2 in order to carry out normalization and differential gene expression. 

If you used the "RNA-seq Primary analysis" workflow, you should have the output from featureCounts in the history from the earlier workflow on the right-hand side of the homepage. This counts collection would be under "featureCounts on collection N: Counts" and this contains counts for each sample under a different table. If you didn't run the "RNA-seq Primary analysis" workflow, and you would like to use an example dataset for the "RNA-seq Tertiary analysis" workflow, follow the instructions `here <https://galaxy-tutorial.readthedocs.io/en/latest/Tertiary%20analysis/Importing%20data/Importing%20example%20data%20for%20running%20Tertiary%20Analysis.html>`_.

.. note::

  1. The "RNA-seq Tertiary analysis" workflow has DESeq2 tool setup so that it can take in one factor, with two factor levels. If you have two or more factors, consider running each step of the pipeline rather than the workflow.


**For users running the workflow**

Navigate to the "Workflows" tab and scroll down to the "RNA-seq Tertiary analysis" workflow. Below are the steps that help identify differentially expressed genes. The four tools that are required for the identification of differentially expressed features (genes in our case) are as follows -

* Extract element identifiers 

* Replace text

* Tag elements

* DESeq2

For the first three tools, the user doesn't need to enter any values as everything is pre-entered when creating the workflow. However, the most important thing to note at this step is the factors to be entered within the DESeq2 tool. 

**Setting up DESeq2** -

* Scroll down to the DESeq2 part of the workflow and click the edit button next to "Specify a factor name, e.g. effects_drug_x or cancer_markers"

* This allows you to edit the "FactorName"

* Enter the factor name that you want to include (For example, Treatment)

* Under the "factor level" of this "FactorName", click the edit button next to "Specify a factor level, typical values could be 'tumor', 'normal', 'treated' or 'control'"

* This allows you to edit the "FactorLevel"

* Enter the first factor level that correspond to this "FactorName" (For example, treated)

* In the textbox under "Select groups that correspond to this factor level", select the factor level tag that is attached to your samples (For example, since my samples are xxx_treat, I would enter treat here. 

* Under the second "factor level", click the edit button and enter the second factor level (For example, untreated)

* In the textbox under "Select groups that correspond to this factor level", select the factor level tag that is attached to your samples (For example, since my samples are xxx_untreat, I would enter untreat here)

.. note::

  Remember that the word that you enter into the factor levels should correspond to the word that you enter when you make your sample name (So, for example, if your samples are named as xxx_treat and xxx_untreat, then the two factor levels under Treatment factor in DESeq2, specifically under "Select groups that correspond to this factor level" should correspond to the words in the sample name after the underscore)

* If you have batch factors that you know would affect your model, upload a tabular file with the factors that you would like to include (Note: This file is optional and could be produced by other tools like RUVseq or svaseq)

The output of this step will be explained in the next page. For users running the workflow, you can read further down this page if you would like to know how the other three tools work and what they do.


**For users running each step separately** let's get into the nitty-gritty of identifying differentially expressed features (genes in our case) -

The first tool that is used is "Extract element identifers"

* The tool takes in the output of featureCounts "all counts" which should show up in your history on the right hand side

* In the dropdown menu, select "all counts" and click "Execute"

* This tool basically extracts the sample names from the count tables

The second tool that is used is "Replace text in entire line"

* This tool is basically to assign the factor names to groups which will be provided to DESeq2 in order to perform "Differential expression analysis"

* Search for the tool under "Tools" and select the file to process (Your output from "Extract element identifiers")

* Under "Find pattern", enter "(.*)_(.*)" if you have one factor (Here, the sample name looks like xxx_treat, xxx_untreat, etc where factor is treatment) 

* If you have three or more factors, modify the entry accordingly ((.*)_(.*)_(.*)_(.*) for three factors where the sample name would be xxx_treat_paired_time. Note: .* is a regular expression which searches for any character)

* Under "Replace with", enter "\1_\2\tgroup:\2" if you have two factors (Basically, the tool is creating two additional columns with the two factors that can be used with the next tool which can be then submitted to DESeq2)

* Click "Execute"

* Change the datatype of the result file to "tabular" in the history section

  a. Changing the datatype - Click on the pencil icon for the dataset and a panel opens up
  
  b. Click on Datatypes tab on the top and select "tabular" in the dropdown menu
  
  c. Click the Save button
  
The third tool that is used is "Tag elements"

* This tool attaches the tags that were extracted earlier to the counts file so that it can be used by the DESeq2 tool

* Search for the tool under "Tools" and under "Input Collection", select the output from featureCounts - "all counts"

* Under "Tag collection elements according to this file", select the output from "Replace text" in the dropdown menu

The fourth tool that is used is "DESeq2"

* This tool carries out differential expression analysis

* Search for the tool under "Tools" and under the first dropdown, select "Select group tags corresponding to levels"

* Select the output of "Tag elements" tool in the dropdown menu under "Count file(s) collection"

* Click on "+ Insert Factor"

* Under "Specify a factor name, e.g. effects_drug_x or cancer_markers", type in the factor name (For example, Treatment is a factor)

* Under this factor, one can add the corresponding factor levels by clicking on "+ Insert Factor level"

* Enter the factor level under "Specify a factor level, typical values could be 'tumor', 'normal', 'treated' or 'control'" (treated and untreated are two factor levels)

* The tags built earlier will be useful in the next step under "Select groups that correspond to this factor level" where one can select the corresponding tags from the dropdown menu (For our examples, the tag would be "Tags: treat")

* Insert more factor levels using the "+ Insert Factor level" (For example, untreated and the corresponding tag - "Tags: untreat")

* Repeat this procedure of adding factors and corresponding factor levels for as many factors you have 

* Under "Files have header?", choose No

* Under "Choice of Input data", select "Count data (e.g. from HTSeq-count, featureCounts or StringTie)"

* Expand "Output Options", select "Generate plots for visualizing the analysis results" and "Output normalised counts" and click "Execute"

The output of this step will be explained in the next page.
