Tapping behavorial data streams: a case study in the use of proximal sensors for __

* analyzing gesture?
* human motion analysis?
* investigating multimodal deixis?
* constructing multimodal corpora?

Voice, image, touch, motion, orientation, and geolocation sensors are now ubiquotous, embedded into the communication devices we carry in our pockets.  Complementing this already pervasive technology is a new breed of compact, powerful, low-cost motion and depth sensors.  We'll refer to the various sensors designed to gauge user behavior within close range of the human body as **proximal sensors**, distinguishing them from **distal** sensors that are designed to sense activity from a distance.

Much of the appeal of proximal sensors is their potential for enabling new
forms of perceptual computing and natural user interaction, especially when
used in concert with one another.  They can be utilized as coordinated set of input devices, each sensing one facet of the user's behavior or context, which can then be rendered in an appropriate form for the user to respond to as part of a tight perceptual feedback loop. 

However, designing new forms of user interaction requires a lot of empirical
groundwork: gathering observations, testing what works and what doesn't.
And therein lies a futher appeal of proximal sensors: they can function
as effective tools for gathering the very behavioral data that is being designed for and needs to evaluated.

Converting the behavioral data streams afforded by proximal sensors into
explorable multimodal datasets is a new challenge. We intend to present a case study that demonstrates a particular approach to this problem.

Our aim is to describe our development toolchain, which we've found to be particularly appropriate for this task, and to highlight some basic techniques for working with (viz., capturing, filtering, synchronizing, rendering, extracting, analyzing, and replicating) the behavioral data streams afforded by proximal sensors.



* evented I/O
  * streams
  * redirection
  * pipelines

* sync / async

* synchronous events
* the synchronization of multiple modalities
* timed metadata
* coordinated views
* features/dimensions (detection/extraction/learning)


Node - platform and ecosystem for building fast, scalable network applications
Crossfilter - fast feature filtering
D3 - flexible rendering, coordinated views
LevelDB/IndexedDB - distributed datastores, replication

WebRTC - plugin-free realtime communication protocol
Tracks/Cues/[WebVTT](https://developer.mozilla.org/en-US/docs/HTML/WebVTT) -
event synchronization
[SLEEP](http://bl.ocks.org/joyrexus/7643968) - Syncable Lightweight Event Emitting Persistence

---

## Node

[Node.js](http://nodejs.org/) is a platform built on Chrome's JavaScript runtime for easily building fast, scalable network applications. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices.


## Crossfilter

[Crossfilter](https://gist.github.com/joyrexus/7439256/) provides fast n-dimensional filtering and grouping of records, enabling live histograms.  It's designed for exploring large multivariate datasets, where interactions consist of grouping by a dimension followed by incremental filtering and reducing along another dimension.

In other words, it enables you to define **dimensions** on your dataset, by
which you can then filter, sort, group and reduce the dataset. It's internal
indicing makes this all very fast and efficient.

In this [tutorial](http://bl.ocks.org/joyrexus/7439256) we walkthrough
crossfilter's basic features.
