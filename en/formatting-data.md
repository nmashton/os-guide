OpenSpending expects all data to be in a simple format.

#### CSV

OpenSpending accepts data in a single file format, the Comma-Separated Values (CSV) file. A CSV is a plain text file that represents data as a table, which is similar to a spreadsheet. In a table, each data point is represented by a row, and each data point's properties are represented by a column. CSV files encode tables by giving each row a line in the text file and by separating columns with commas.

CSVs accepted by OpenSpending are *denormalized*, meaning that they do not save space by removing redundant values. OpenSpending-ready CSVs are also *rectangular*, having exactly the same number of columns in each row.

#### The OpenSpending format

CSVs for OpenSpending must have the following properties.

1. One header row. The first row of the CSV file should contain the names of the columns, separated by commas. All other rows are treated as data rows.

2. At least three columns. The bare minimum of columns are an amount, a date (which could be just a year), and a spender or a recipient (which could just be the name of an account).

3. Consistent columns. Each column must consistently represent a single type of value for all rows. (There can be no subheader rows, for example.)

4. Rows are data points. Rows should contain only one type of information: one transaction or one budget line. One row must represent a maximum of one time period. (Rows cannot represent multiple transactions.)

5. No blank rows or cells. Each row of an imported data file should contain all of the information required to construct the resulting item.

6. No pre-aggregated totals (e.g. sub-totals or "roll-ups"). OpenSpending will do the maths and compute these automatically.

7. A unique identifier. There must be a column (or a combination of columns) whose values uniquely identify each row. The easiest way to create such an identifier is to add a dummy column to the dataset in which you put a number that increases for each row. You can do this in Excel by typing the numbers into the first two rows, selecting both cells and dragging down the lower right corner of the cell to extend the series.

8. Dates in the correct format. Dates must be in the format "yyyy-mm-dd".

9. Numbers in the correct format. Numbers must contain only digits and an optional period—no commas! (Readable numbers like "12,345.67" should be converted to numbers like “12345.67”.)

The OpenSpending community has gathered some [example spreadsheets](https://drive.google.com/a/okfn.org/#folders/0B_dkMlz2NopEbmRoTExsMDFMR2M) in order to illustrate what "good" and “bad” tabular data looks like. Here are some examples of badly formatted spreadsheets:

* [Many blank cells](https://docs.google.com/a/okfn.org/spreadsheet/ccc?key=0AvdkMlz2NopEdEtIMFlEVDZXOWdDUEthUTQ0c21aV2c#gid=0) (probably redundant info omitted)

* [Multiple transactions, one row](https://docs.google.com/a/okfn.org/spreadsheet/ccc?key=0AvdkMlz2NopEdG5kR0kzQ0E5V3BuTS16MndBT3dMdEE#gid=0) (multiple years on one row)

* [Bad numbers](https://docs.google.com/a/okfn.org/spreadsheet/ccc?key=0AvdkMlz2NopEdEo1Y2p2R0VvdnJvRXMwUVREbHRoLXc#gid=0) (numbers have commas for readability)

Here is a good spreadsheet:

* [Washington, DC](https://docs.google.com/a/okfn.org/spreadsheet/ccc?key=0AvdkMlz2NopEdDhrZnRkWl9ZX2ZZNVptTzdueWw3emc#gid=0)

**Next**: [Publishing data on the web](../publishing-data)

**Up**: [OpenSpending Guide](../)