# Data Viz 


## Resources

* [Data + Design](https://infoactive.co/data-design/titlepage01.html) - a
  simple introduction to preparing and visualizing information

* [Interactive Data Visualization for the Web](http://chimera.labs.oreilly.com/books/1230000000345/index.html) - an intro to D3 for non-programmers

* [Crossfilter](http://square.github.io/crossfilter/) - Fast Multidimensional
  Filtering for Coordinated Views

* [Vega](http://trifacta.github.io/vega/) - a declarative format for 
  creating, saving and sharing visualization designs


## Notes

**Coordinated views** are multiple visualizations (often presented as Tufte-style [small multiples](http://en.wikipedia.org/wiki/Small_multiple)) that summarize data along different dimensions, where filtering in one dimension updates the others.


### Interactive Dynamics for Visual Analysis

[Stolen notes](https://raw.github.com/sirrice/csail/master/papers.md) on the [Heer paper](http://queue.acm.org/detail.cfm?id=2146416).

Taxonomy separates into ...

* Data/nview specification
  * visualize: choose visual encodings
  * filter: construct subsets of data
  * sort: rearrange items to show patterns
  * derive: execute transforms

* Manipulation/interaction
  * Select
  * Navigate (explore): panning (sideways) and zooming (up/down)
  * Coordinate: linking
  * Organize: multiple views/windows (gg algebra falls into this)

* Provenance (the labeling kind, not data kind)
  * Record
  * Annotate
  * Share: deep into the state of a vis, not just the page
  * Guide: provide workflows, common steps, walkthroughs


#### Data/View Specs

* Visualize
  * Data flow: more mechanical, imperitive work
  * Grammar: users need to understand the underlying model
  * Tableau is drag-n-drop translated into a formal grammar

* Filter
  * Filter individual items, or use widgets to filter abstract space
  * [crossfilter](http://square.github.io/crossfilter/) adds controls
    directly on a histogram
  * querying


#### Manipulation

* Select
  * Indirect: Query over a space
  * Direct: a collection of objects
  * Starting point for other interactions

* Navigate
  * overview -> zoom/filter -> details on demand
  * search -> show context -> expand context
  * Viz as viewport on data
  * Basic scroll, pan, zoom
  * Picture in picture type overview+details coordinated views

* Coordinate
  * join with other data (join _source_ with other data)
  * facetting and small multiples

