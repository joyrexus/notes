# Munging Tools

Before unsheathing [pandas](http://pandas.pydata.org/) on your next data munging problem, consider pulling out your [unix toolbox](http://joyrexus.spc.uchicago.edu/public/reference/oreilly/unix/index.htm) to slice-and-dice stuff old-school.

Unix pipelines will take you far.  Repeated operations can then be encapsulated in a script.

In addition to your standard stable of unix scripting languages (`bash` and
other shell dialects, `sed`, `awk`, and `perl`), there are a handful standard
power tools (`jot`, `rs`, etc) and add-ons worth your consideration.  Use `jot` to print sequential or random data and `rs` to reshape a data array.


## Intro Surveys

* [Explorations in Unix](http://www.drbunsen.org/explorations-in-unix/) 

* [Command-line tools for data science](http://jeroenjanssens.com/2013/09/19/seven-command-line-tools-for-data-science.html)


## Using `jot`

Create two columns of random numbers:

    jot -r 100 | rs 50

Given a list of random numbers, ranging from 1 to 20, show the count
of those numbers >= 10 and those < 10:

    jot -r 20 1 20 | perl -ne 'print $_ >= 10 ? 1 : 0, "\n"' | sort | uniq -c

... or showing percentages:

    jot -r 20 1 20 
      | perl -ne 'print $_ >= 10 ? 1 : 0, "\n"' 
      | sort 
      | uniq -c 
      | cut -c 3-4 
      | perl -ne'chomp; $sum += $_; push @counts, $_; 
                END { print $_, " : ", $_ / $sum, "\n" for @counts }'

... or to show the percentage of nines in the list:

      | perl -ne 'print $_ == 9 ? 1 : 0, "\n"' 

Given a list of numbers, ranging from 0 to 20,000, show the distribtion (i.e., 
individual counts) of those numbers after each is rounded to the nearest 
$1,000 increment:

    jot -r 20 0 20000 
      | perl -pe'$_ = 1000 * int($_/1000)."\n"' 
      | sort -n 
      | uniq -c

... or showing percentages:

    jot -r 20 1000 20000 
      | perl -pe'$_ = 1000 * int($_/1000) . "\n"' 
      | sort -n
      | uniq -c 
      | perl -ne'($n,$num) = /(\d+)/g; $counts{$num} = $n; $sum += $n; 
                  END { print $_, 
                        " : ", 
                  $counts{$_} / $sum, "\n" 
                  for sort {$a<=>$b} keys %counts }'

... or to find the median (i.e., the middle number):

	    | perl -e'@lines = <>; print $lines[int($#lines/2)]'

... or to find the average:

    jot -r 20 0 20000 | perl -pe'$_=1000 * int($_/1000)."\n"'

