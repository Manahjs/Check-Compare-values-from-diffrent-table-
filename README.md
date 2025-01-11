# Check-Compare-values-from-diffrent-table-
analysis understand and compare the data from different sources [AUC CONCEPT] A small code used in every industries  Relive  for sql devlopers and HR &amp; Startigies partner
# Excel Comparison Script Overview

## Key Improvements
1. It reads the entire Excel files instead of just specific columns, allowing us to provide full row details for unmatched items.
2. It uses a dictionary (`search_dict`) created from the second DataFrame for faster searching. This approach is more efficient than using a set, especially for large datasets.
3. The script now provides more detailed information about unmatched rows, including the full row details from the first file.
4. It separates matched and unmatched results for better readability.
5. A summary is added at the end, showing the total number of rows, matched rows, and unmatched rows.

## How to Use the Script
1. Make sure you have the `pandas` library installed. If not, you can install it using `pip install pandas`.
2. Replace the file paths (`file1` and `file2`) with the correct paths to your Excel files.
3. Set the `column1` and `column2` variables to the correct column names in your Excel files.
4. Run the script.

## Script Updates

### Quantity Matching Script
This improved version will provide you with a comprehensive comparison of the two Excel files, giving you detailed information about both matched and unmatched rows. The hash-based search algorithm (using a dictionary) should also provide better performance for large datasets.

```python
# Excel Comparison Script with Quantity Matching
# ...

# Excel Comparison Script with Quantity and Rate Matching
# ...





<!DOCTYPE html>
<html>
<head>
    <title>Excel Comparison Script Overview</title>
</head>
<body>
    <h1>Excel Comparison Script Overview</h1>

    <h2>Key Improvements</h2>
    <p>1. It reads the entire Excel files instead of just specific columns, allowing us to provide full row details for unmatched items.<br>
       2. It uses a dictionary (<code>search_dict</code>) created from the second DataFrame for faster searching. This approach is more efficient than using a set, especially for large datasets.<br>
       3. The script now provides more detailed information about unmatched rows, including the full row details from the first file.<br>
       4. It separates matched and unmatched results for better readability.<br>
       5. A summary is added at the end, showing the total number of rows, matched rows, and unmatched rows.</p>

    <h2>How to Use the Script</h2>
    <p>1. Make sure you have the <code>pandas</code> library installed. If not, you can install it using <code>pip install pandas</code>.<br>
       2. Replace the file paths (<code>file1</code> and <code>file2</code>) with the correct paths to your Excel files.<br>
       3. Set the <code>column1</code> and <code>column2</code> variables to the correct column names in your Excel files.<br>
       4. Run the script.</p>

    <h2>Script Updates</h2>
    <h3>Quantity Matching Script</h3>
    <p>This improved version will provide you with a comprehensive comparison of the two Excel files, giving you detailed information about both matched and unmatched rows. The hash-based search algorithm (using a dictionary) should also provide better performance for large datasets.</p>
    
    <pre><code>```python project="Excel Comparison" file="compare_excel_with_quantity.py"
...
```</code></pre>
    <p>This updated script includes the following improvements:</p>
    <ul>
        <li>It now compares the quantity columns (<code>Quantity</code> in the first file and <code>LD WT</code> in the second file) for matched rows.</li>
        <li>A new column called 'Match Result' is added to the first DataFrame to store the match results.</li>
        <li>For matched rows, it checks if the quantity difference is within 0.2. If so, it considers it a match and specifies whether it's an exact match or a close match.</li>
        <li>The script writes the results to a new Excel file, including the 'Match Result' column.</li>
        <li>For unmatched rows due to quantity mismatch, it includes the quantity difference in the output.</li>
    </ul>

    <h3>Quantity and Rate Matching Script</h3>
    <p>I'll modify the script to include the comparison of the 'Frt/MT' column with the 'Rate/Ton' column, considering matches within a 1-10 Rs difference. I'll also include the unmatched amount and value in the results.</p>
    
    <pre><code>```python project="Excel Comparison" file="compare_excel_with_quantity_and_rate.py"
...
```</code></pre>
    <p>This updated script includes the following improvements:</p>
    <ul>
        <li>It now compares both the quantity columns (<code>Quantity</code> and <code>LD WT</code>) and the rate columns (<code>Frt/MT</code> and <code>Rate/Ton</code>) for matched rows.</li>
        <li>Three new columns are added to the first DataFrame: 'Quantity Match', 'Rate Match', and 'Match Result'.</li>
        <li>For matched rows:
            <ul>
                <li>It checks if the quantity difference is within 0.2, as before.</li>
                <li>It checks if the rate difference is exactly 0 or within 1-10 Rs.</li>
            </ul>
        </li>
        <li>The script categorizes matches as:
            <ul>
                <li>"Full Match": Both quantity and rate match (within the specified tolerances)</li>
                <li>"Partial Match": Either quantity or rate doesn't match</li>
                <li>"No match found": No matching row found in the second file</li>
            </ul>
        </li>
        <li>For unmatched or partially matched rows, it includes both the quantity difference and the rate difference in the output.</li>
        <li>The script writes the results to a new Excel file, including the new 'Quantity Match', 'Rate Match', and 'Match Result' columns.</li>
    </ul>

    <h2>Handling Unmatched Rows</h2>
    <p>It keeps track of which rows in the 'test' file (file2) were used in the comparison by adding them to a <code>used_rows</code> set.<br>
       After the main comparison, it identifies the unused rows in the 'test' file by creating a new DataFrame <code>unused_df</code> that contains all rows from file2 where the key column (Inv No) is not in the <code>used_rows</code> set.<br>
       It saves these unused rows to a separate CSV file specified by the <code>unused_rows_file</code> parameter.<br>
       The script now prints information about the number of unused rows in file2 and where they were saved.<br>
       At the end of the script, it reads and prints the contents of the unused rows file to verify the output.</p>

    <h2>Duplicate Check</h2>
    <p>The script now checks for duplicate or repeated ODN NO values in the 'tar' file (file1) at the beginning of the script.<br>
       It uses the <code>Counter</code> class from the <code>collections</code> module to count the occurrences of each ODN NO value.<br>
       If duplicates are found, it prints out each duplicate ODN NO value and the number of times it's repeated.<br>
       If no duplicates are found, it prints a message stating that no duplicate ODN NO values were found.<br>
       The rest of the script remains the same, performing the comparison, creating output files, and printing results as before.</p>
</body>
</html>
