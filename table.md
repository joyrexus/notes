# Table Munging Terminology

We need a simple vocabulary for talking about the manipulation of tabular data structures.  That is, we want a clean and elegant way of describing how to **munge** tables.  We want to slice and dice them with minimal pain.  Implementation can follow once we settle on the right verbs for data manipulation operations and the right nouns for post-manipulated elements.  Yes, we have relational algebra codified in SQL and its mungy extensions.  So we're just talking about a coherent distillation of those parts potentially applicable to any tabular data store.

What follows are extracts from Hadley Wickham's [dplyr](https://github.com/hadley/dplyr) project README file.


## Context

You need to **split** up a big data structure into homogeneous pieces, **apply** a function to each piece and then **combine** all the results back together. For example, you might want to:

* fit the same model for each subset of a data frame
* quickly calculate summary statistics for each group
* perform group-wise transformations like scaling or standardising


## Unary verbs

* `select()`: focus on a subset of variables
* `filter()`: focus on a subset of rows
* `mutate()`: add new columns
* `summarise()`: reduce each group to a smaller number of summary statistics
* `arrange()`: re-order the rows


### Binary verbs

As well as verbs that work on a single table, we also want verbs describing how to operate on two tables at a time, viz. your standard **joins**:

* `inner_join(x, y)`: matching x + y
* `left_join(x, y)`: all x + matching y
* `semi_join(x, y)`: all x with match in y
* `anti_join(x, y)`: all x without match in y


### Other

We might also want to provide `head()` and `print()` methods for summary display of our tables.


## Existing tools

* [reshape](https://github.com/hadley/reshape)

* [dplyr](https://github.com/hadley/dplyr)

* [pandas](http://pandas.pydata.org/)

* [crossfilter](https://github.com/square/crossfilter) - fast n-dimensional
  filtering and grouping of records in javascript.


## Further Reading

* [The split-apply-combine strategy](http://vita.had.co.nz/papers/plyr.html)

* [Crossfilter API](https://github.com/square/crossfilter/wiki/API-Reference)

* [Pandas comparison w/ R](http://pandas.pydata.org/pandas-docs/stable/comparison_with_r.html#comparison-with-r-r-libraries)

* [R and pandas and what I've learned about each](http://blog.yhathq.com/posts/R-and-pandas-and-what-ive-learned-about-each.html)

* [SQL for pandas DataFrames](http://blog.yhathq.com/posts/pandasql-sql-for-pandas-dataframes.html)

* [Data aggregation and reshaping with pandas](http://slendrmeans.wordpress.com/2012/04/26/will-it-python-machine-learning-for-hackers-chapter-1-part-4-data-aggregation-and-reshaping/)
