## XBD

We're pushing the idea of **explorable behavioral datasets**.

We're investigating:

* tooling
* [standards](https://gist.github.com/joyrexus/7643968)
* best practices

Currently exploring strategies for the immediate capture and playback of gesture/hand-motion samples, but ultimately interested in techniques for persisting, editing, annotating, and replicating behavioral activity streams in general.


### Why?

The rise of proximal sensors.

They provide a stream of behavioral data that can be ...

* captured
* visualized
* edited
* munged
* analyzed
* replicated


### Relevant Domains

* [motion capture](http://en.wikipedia.org/wiki/Motion_capture)
* [motion analysis](http://en.wikipedia.org/wiki/Motion_analysis)

* [motor learning](http://en.wikipedia.org/wiki/Motor_learning)
* [motor control](http://en.wikipedia.org/wiki/Motor_control)


## Tooling

In general, the plan is to build off D3 for visualization/interaction and IndexedDB as a distributed datastore.

The following modules encapsulate some key methods and techniques that we plan to utilize.


### Munging

* [nest](https://gist.github.com/joyrexus/7360353) - convert tables to trees

* [crossfilter](https://gist.github.com/joyrexus/7439256) - fast multidimensional filtering for coordinated views


### Visualization

* [dc.js](http://nickqizhu.github.io/dc.js/) - reactive dimensional charting

* [catcorr.js](http://deanmalmgren.github.io/catcorrjs/) - visualize correlations across many dimensions of categorical data


### Persistence and Replication

* [dat](http://dat-data.com/) - real-time replication and versioning for large tabular data sets

* [level.js](https://github.com/maxogden/level.js) - leveldb for the browser

* [levelweb](https://github.com/hij1nx/levelweb) - leveldb gui w/ builtin
  visualization tools


## Further Reading

* [The vision behind Harvest](http://harvest.research.chop.edu/manifesto/)
* [Replicating large datasets in HTML5](http://maxogden.com/replicating-large-datasets-into-html5.html)
* [Your API does REST, but can it SLEEP?](https://gist.github.com/joyrexus/7643968)
* [Designing coordinated visualizations](http://bl.ocks.org/milroc/raw/7032589/#0)
