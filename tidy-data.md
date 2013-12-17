# Tidy Data

* Each table is of one observational type 
* Each column is a variable
* Each row is an observation
* Each value represents a fact about the observation


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
