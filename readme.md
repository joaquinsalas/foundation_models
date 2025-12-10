# Creating a Foundation Model

This github contains the code accompaning the text in Medium


# CommonColumns.py

This script scans a directory of monitoring CSV files and builds compact summary tables of their structure:

* Expects files named like:
  `COMMUNITY_mm_yyyy_to_mm_yyyy.csv` (e.g., `XCommunity_01_2020_to_12_2020.csv`).
* For each file, it:

  * Parses the community name and date range from the filename.
  * Reads the header to get column names.
  * Counts the number of data rows (excluding the header).
* It then groups files by *identical column sets* and, for each group, computes:

  * Number of files.
  * Total number of rows across those files.
  * Number of columns and their names.
* The script produces two outputs in `../data`:

  * `monitoring_columnsets_rows.csv`: one row per unique column set with aggregated stats and list of files.
  * `monitoring_file_summary.csv`: one row per file with community, date range, row count, and column list.

