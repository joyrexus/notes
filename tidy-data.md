# Tidy Data

* Each table is of one observational type 
* Each column is a variable
* Each row is an observation
* Each value represents a fact about the observation

Restated ...

* Each data set contains information on only one observational unit of analysis
* Each variable forms a column
* Each observation forms a row
* Each value in a row is about the observation

A data set that meets these criteria is "tidy". 

---

The following is largely excerpted from [this series](http://www.prometheusresearch.com/good-data-management-practices-for-data-analysis-tidy-data-part-2/) on data management practices.

A tidy data set is, by definition, about only one type of thing or event (observational unit) that has been observed a certain number of times (rows) using certain measurements and identifiers (variables).  The first two criteria essentially define long-format or panel data, a structure that will be familiar to you if you’ve ever analyzed repeated-measures or longitudinal data. In that case it might be easiest to think of tidy data as long-format data that is about only one observational unit.

Tidy data is a useful intermediate data structure for data analysis because it
can easily be changed into other useful formats. All of the primary data
manipulation activities (filtering, transforming, sorting, and aggregating) as
well as visualization and modeling are greatly simplified when working with
tidy data. This is especially true when we process tidy data with "tidy tools".
 
Tidy tools are those that accept, manipulate, and return tidy data, thus preserving the versatility of the tidy data structure and minimizing the need for additional data restructuring.

Recall that data in a relational database is stored in multiple tables, usually arranged in a structure called **Third Normal Form** (**3NF**).  A table is in 3NF if all of its data relates to one thing (entity), each observation of that thing forms a unique row, and each aspect (variable) about the thing forms a column. This should sound a lot like the definition of tidy data—because it is. Each table in relational database is, effectively, a tidy data set.


## Melting

* Existing variable columns (colvars) used as is.  
* Create a *variable* column for variables stored in column names.  
* Create a *value* column for values in untidy table.


## Casting

Casting consists of "pivoting" a table into the column variables desired.

* filter where "variable" = (list of desired columns)
* groupby colvars + list of desired columns, extract "value"
* need agg function if each group is not unique

Essentially ...

    SELECT dimensions, measurements, agg(val1), .., agg(valn)
    FROM data
    GROUP BY dimensions, measurements

... where table header is:

    dim1, ..., dimn, meas1, ..., measn | agg1, ... aggn
    ----------------------------------------------------

Traditional tables are a special case where we GROUP BY everything and aggregate NULL (i.e., don't collect aggregates)


## See Also

* [Tidy Data Talk](http://vimeo.com/33727555) by Hadley Wickham
