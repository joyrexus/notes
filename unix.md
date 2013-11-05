# Unix Tools

Before unsheathing [pandas](http://pandas.pydata.org/) on your next data munging problem, consider pulling out your [unix toolbox](http://joyrexus.spc.uchicago.edu/public/reference/oreilly/unix/index.htm) to slice-and-dice stuff old-school.

Unix pipelines will take you far.  Repeated operations can then be encapsulated in a script.

In addition to your standard stable of unix scripting languages (`bash` and
other shell dialects, `sed`, `awk`, and `perl`), there are a handful standard
power tools and add-ons worth your consideration.  Use `jot` to print sequential or random data and `rs` to reshape a data array.


## Intro Surveys

* [Explorations in Unix](http://www.drbunsen.org/explorations-in-unix/) 

* [Command-line tools for data science](http://jeroenjanssens.com/2013/09/19/seven-command-line-tools-for-data-science.html)

---

## Quick Tips 

* [Unix Tools](http://joyrexus.spc.uchicago.edu/labs/notes/unix.html)


#### Misc

Print sorted list of all unique terms in first column:

    cut -d '.' -f 1 FILE | uniq | sort -n
 	
Reformat text in FILE into two columns:

    fmt -34 FILE | pr -2 -t 

Use a backslash for line continuations:

    svn import mytree file:///var/svn/repos/some/project \ 
    -m "Initial import" 

Use `time` to benchmark run times:

    time COMMAND


#### Simple Filters

    perl -ne 'print if /REGEX/' FILE
    perl -pe's/SEARCH/REPLACE/' FILE 

    ruby -ne 'print if /REGEX/'
    ruby -pe '$_ = "" unless /REGEX/'
    ruby -e 'print STDIN.grep /REGEX/'
    ruby -i -pe "gsub!(/PATTERN/, STRING)" FILE1 FILE2 ...


#### Python one-liners

    python -c 'command' [ARG] ...
    python -m module [ARG] ...

Interactively plot vectors with gnuplot:

    gnuplot> plot '-' with vectors
    input data ('e' ends) > 0 0 4 3
    input data ('e' ends) > 2 1 -4 2
    input data ('e' ends) > e
