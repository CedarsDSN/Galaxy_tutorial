Identification of differentially expressed features
====================================================

If you want to learn more about the DESeq2 model and how it works, please refer to the `paper <https://genomebiology.biomedcentral.com/articles/10.1186/s13059-014-0550-8>`_. The Galaxy DESeq2 tool is designed to accept as many factors as the user wants to add, along with levels for each factor. For example, a factor could be treatment and the factor levels could be treated and un-treated. Providing these helps the model compare the factors and the different levels there-in. Moving forward from the count table obtained from featureCounts, the table needs to be in a format that can be understood by DESeq2 in order to carry out normalization and differential gene expression. If you carried out primary analysis from this tutorial, you should have the output from featureCounts in the history on the right hand side of the homepage. If users want to use the workflow, it can be used but the number of factors that can be given to the workflow is two. So, if the user has more or less factors, it would be better to run the secondary analysis as seperate steps as specified in the Introduction. 

For users running the workflow, the four tools that are needed for this step are -

* Extract element identifiers 

* Replace text

* Tag elements

* DESeq2

For the first three tools, the user doesn't need to enter any values as everything is pre-entered when creating the workflow. However, the most important thing to note at this step is the factors to be entered within the DESeq2 tool. The steps to do this are -

* Scroll down to the DESeq2 part of the workflow and click the edit button next to "Specify a factor name, e.g. effects_drug_x or cancer_markers"

* This allows you to edit the "FactorName"

* Enter the first factor name that you want to include (For example, Treatment)

* Under the "factor level" of this "FactorName", click the edit button next to "Specify a factor level, typical values could be 'tumor', 'normal', 'treated' or 'control'"

* This allows you to edit the "FactorLevel"

* Enter the first factor level that correspond to this "FactorName" (For example, treated)

* In the textbox under "Select groups that correspond to this factor level", select the factor level tag that is attached to your samples (For example, since my samples are xxx_treat_(sequencing_type), I would enter treat here. Note: Here "sequencing type" is the other factor that I need to account for, and could be paired or single)

* Under the second "factor level", click the edit button and enter the second factor level (For example, untreated)

* In the textbox under "Select groups that correspond to this factor level", select the factor level tag that is attached to your samples (For example, since my samples are xxx_untreat_(sequencing_type), I would enter untreat here)

* Now, repeat the whole procedure for the next factor that needs to be accounted for (For example, sequencing type would be my Factor name and paired and single would be the factor levels)

* If you have batch factors that you know would affect your model, upload a tabular file with the factors that you would like to include (Note: This file is optional and could be produced by other tools like RUVseq or svaseq)

For users running the workflow, you can read further down this page if you would like to know how the other three tools work and what they do.

For users running each step or running the secondary analysis seperately, let's get into the nitty-gritties of this step -

The first tool that is used is "Extract element identifers"

* The tool takes in the output of featureCounts "all counts" which should show up in your history on the right hand side

* In the dropdown menu, select "all counts" and click "Execute"

* This tool basically extracts the sample names from the count tables

The second tool that is used is "Replace text in entire line"

* This tool is basically to assign the factor names to groups which will be provided to DESeq2 in order to perform "Differential expression analysis"

* Search for the tool under "Tools" and select the file to process (Your output from "Extract element identifiers")

* Under "Find pattern", enter "(.*)_(.*)_(.*)" if you have two factors (Here, the sample name looks like xxx_treat_paired, xxx_untreat_paired, etc where my two factors are treatment and sequencing type) 

* If you have three or more factors, modify the entry accordingly ((.*)_(.*)_(.*)_(.*) for three factors where the sample name would be xxx_treat_paired_time. Note: .* is a regular expression which searches for any character)

* Under "Replace with", enter "\1_\2_\3\tgroup:\2\tgroup:\3" if you have two factors (Basically, the tool is creating two additional columns with the two factors that can be used with the next tool which can be then submitted to DESeq2)

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
