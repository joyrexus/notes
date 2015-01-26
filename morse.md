# Morse Theory

The [calculus of variations](http://en.wikipedia.org/wiki/Calculus_of_variations) has a long and storied history in mathematics and classical mechanics. One chapter of that story is the development of the calculus of variations "in the large", where [Marston Morse](http://en.wikipedia.org/wiki/Marston_Morse) introduced the techniques of [differential topology](http://en.wikipedia.org/wiki/Differential_topology).  Morse [showed](http://en.wikipedia.org/wiki/Morse_theory) how one could analyze the [topology](http://en.wikipedia.org/wiki/Topological_space) of a [manifold](http://en.wikipedia.org/wiki/Manifold) by studying [differentiable functions](http://en.wikipedia.org/wiki/Differentiable_function) on that manifold. 


## Applied Morse Theory

Arthur Cayley ([On Contour and Slope Lines](http://www.maths.ed.ac.uk/~aar/papers/cayleyconslo.pdf) and James Clerk Maxwell ([On Hills and Dales](http://www.maths.ed.ac.uk/~aar/papers/cayleyconslo.pdf)) had originally developed some of the ideas of Morse theory in the context of topography.

This applied development continues.  In particular, Morse theory can be utilized for inferring key topographic features (peaks, pits, ridges, saddle points, etc.) of surface terrain.  For example, mountaineers are often interested in the [topographic prominence](http://en.wikipedia.org/wiki/Topographic_prominence) of mountain summits (the elevation of a summit relative to the surrounding terrain).

---

The essay [Prominence and Orometrics](http://www.peaklist.org/theory/theory.html), which nicely describes prominence theory and its key concepts: summits, ridge networks, key saddles, mountain lineage, and domains.) Further information on topographic prominence can be found [here](http://www.cohp.org/prominence/index.htm).

Surface elements (types of points on terrain):

* summit
* pit
* saddle
* channel
* ridge
* slope

Surface networks:

* **ridge network** - the set of summits, saddles, and ridges 
* **channel network** - the set of pits and channels

The **divide tree** is an extracted set of critical points from the ridge
network, used to derive measurements of summits.

---

The idea is to utilize a topological model to characterize certain fundamental features of a given topographic surface.  The model can then be used to characterize and reason about the global shape of the surface.

Topological data structures are used to enable such analysis, wherein certain surface-specific features and relations are efficiently encoded.  See [Topological Data Structures for Surfaces](http://www.amazon.com/Topological-Data-Structures-Surfaces-Introduction-ebook/dp/B000TB8AK2), which introduces **surface networks** and [Reeb graphs](http://en.wikipedia.org/wiki/Reeb_graph). 

Both are graph-based data structures which encode the fundamental points and lines in a surface, capturing only the key features of the original metric map (a dense array of elevation data).

See [this working paper](http://www.bartlett.ucl.ac.uk/casa/publications/working-paper-43) for an introduction to surface networks.
