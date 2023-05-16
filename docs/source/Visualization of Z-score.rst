Visualization of the Z-score
================================

For the steps to generate the heatmap for "Visualization of the Z-score" -

* The first tool that is used is "Table compute" and is not required to plot the heatmap but is provided here to understand how Z-scores are generated
Table Compute tool helps compute Z-score and is done in 2 steps

* Subtract each value by the mean of values in a row using the normalized count table

* Divide the previous values by the standard deviation of values in the row, using the two tables (the normalized counts and table computed in the first step)

* Table Compute one -

  a. Under "Input Single or Multiple Tables", select "Single Table" and provide the output of DESeq2 - "Normalized counts"

  b. Under "Type of table operation", select "Perform a full table operation"

  c. Select "Custom" under "Operation"

  d. Select "Custom expression on table along 'axis' (0 or 1)" and input "table.sub(table.mean(1), 0)"

  e. The table.mean(1) expression computes the mean for each row (here the genes) and table.sub(table.mean(1), 0) substracts each value by the mean of the row (computed with table.mean(1))

  f. Click on "Execute"

* Table Compute two

  a. Under "Input Single or Multiple Tables", select "Multiple Table" and provide the output of DESeq2 - "Normalized counts"

  b. Click on "Insert Tables"

  c. In "Tables, enter the output of "Table Compute one"

  d. Select "Custom" under "Operation"

  e. Enter "Custom expression on ‘tableN’" and enter "table2.div(table1.std(1),0)"

  f. The table1.std(1) expression computes the standard deviations of each row on the 1st table (normalized counts) and table2.div divides the values of 2nd table (previously computed) by these standard deviations

  g. Click on "Execute"

  h. Rename the output to "Z-scores"

  i. The next tool used is "heatmap2"

  j. Under "Input should have column headers", enter the file- "Normalized counts for the most differentially expressed genes"

  k. Under "Data transformation", enter "Plot the data as it is"

  l. Select "Compute on rows" under "Compute z-scores prior to clustering"

  m. Select "Yes" under "Enable data clustering"

  n. Under "Labeling columns and rows", enter "Label columns and not rows" (If you want to see sample labels and not genes)

  o. Select "Gradient with 3 colors" under "Type of colormap to use"

  p. Click on "Execute"
