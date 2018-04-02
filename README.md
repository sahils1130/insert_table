
<!-- README.md is generated from README.Rmd. Please edit that file -->
inserttable
===========

`inserttable` is an RStudio add-in facilitating insertion of nicely formatted tables in R markdown documents.

Installation
------------

You can install `inserttable` from [GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("lbusett/insert_table")
```

Upon installing, `inserttable` will register a new RStudio Addin that can be used to easily insert a table in a `Rmd` document. To use it, open a R markdown document and, with the cursor in a `r` chunk, select "Addins --&gt; INSERTTABBLE --&gt; Insert Table". There are two use cases:

### Launch the addin with the cursor on a empty line

In this case, a GUI will open allowing you to **select the desired output format** ( `kable`, `DT` and `rhandsontable` are currently implemented), and to **edit the content of the table**. After clicking **Done** the Addin will add the code needed to generate the table (in `tribble` format to allow easier editing, thanks to [`datapasta`](https://github.com/milesmcbain/datapasta!) and to render it with the selected output format in the `Rmd` document using some default options:

![](man/animation_1.gif)

For larger tables, you can also **cut and paste content from a spreadsheet** :

![](man/animation_2.gif)

Rendering of the table can successively be tweaked further by changing the arguments of the rendering functions.

### Launch the addin while selecting the name of a variable

In this case, the GUI allows you to select **only the desired output format** ( `kable`, `DT` and `rhandsontable` are currently implemented). After clicking **Done** the Addin will add in the `Rmd` document the code needed to render the selected variable as a table with the selected output format. The code will be added at the first empty line below that containing the name of the selected variable.

![](man/animation_3.gif)

**IMPORTANT NOTE**: `inserttable` will make no effort to guarantee that the variable you select is a `data.frame`. It is up to you to select a meaningful variable!

Usage from the console
----------------------

You can also use (part of) `inserttable` functionality from the console by calling function `insert_table()`.

``` r

> insert_table(tbl_name = "table_1", nrows = 4, ncols = 4, tbl_format = "DT")
```

The function will return **to the console** the code needed to create a empty table of the specified dimensions and render it with the selected format:

![](man/animation_4.gif)
