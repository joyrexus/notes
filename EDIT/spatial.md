Introduction
============

Deterministic spatial analysis is an important component of computational
approaches to problems in agriculture, ecology, epidemiology, sociology, and
many other fields. What is the surveyed perimeter/area ratio of these patches
of animal habitat? Which properties in this town intersect with the 50-year
flood contour from this new flooding model? What are the extents of findspots
for ancient ceramic wares with maker's marks "A" and "B", and where do the
extents overlap? What's the path from home to office that best skirts
identified zones of location based spam? These are just a few of the possible
questions addressable using non-statistical spatial analysis, and more
specifically, computational geometry.

Shapely is a Python package for set-theoretic analysis and manipulation of
planar features using (via Python's :mod:`ctypes` module) functions from the
well known and widely deployed GEOS_ library. GEOS, a port of the `Java
Topology Suite`_ (JTS), is the geometry engine of the PostGIS_ spatial
extension for the PostgreSQL RDBMS. The designs of JTS and GEOS are largely
guided by the `Open Geospatial Consortium`_'s Simple Features Access
Specification [1]_ and Shapely adheres mainly to the same set of standard
classes and operations. Shapely is thereby deeply rooted in the conventions of
the geographic information systems (GIS) world, but aspires to be equally
useful to programmers working on non-conventional problems.

The first premise of Shapely is that Python programmers should be able to
perform PostGIS type geometry operations outside of an RDBMS. Not all
geographic data originate or reside in a RDBMS or are best processed using SQL.
We can load data into a spatial RDBMS to do work, but if there's no mandate to
manage (the "M" in "RDBMS") the data over time in the database we're using the
wrong tool for the job. The second premise is that the persistence,
serialization, and map projection of features are significant, but orthogonal
problems. You may not need a hundred GIS format readers and writers or the
multitude of State Plane projections, and Shapely doesn't burden you with them.
The third premise is that Python idioms trump GIS (or Java, in this case, since
the GEOS library is derived from JTS, a Java project) idioms.

If you enjoy and profit from idiomatic Python, appreciate packages that do one
thing well, and agree that a spatially enabled RDBMS is often enough the wrong
tool for your computational geometry job, Shapely might be for you.

.. _intro-spatial-data-model:

Spatial Data Model
------------------

The fundamental types of geometric objects implemented by Shapely are points,
curves, and surfaces. Each is associated with three sets of (possibly infinite)
points in the plane. The `interior`, `boundary`, and `exterior` sets of a
feature are mutually exclusive and their union coincides with the entire plane
[2]_.

* A `Point` has an `interior` set of exactly one point, a `boundary` set of
  exactly no points, and an `exterior` set of all other points. A `Point` has
  a topological dimension of 0.

* A `Curve` has an `interior` set consisting of the infinitely many points
  along its length (imagine a `Point` dragged in space), a `boundary` set
  consisting of its two end points, and an `exterior` set of all other points.
  A `Curve` has a topological dimension of 1.

* A `Surface` has an `interior` set consisting of the infinitely many points
  within (imagine a `Curve` dragged in space to cover an area), a `boundary`
  set consisting of one or more `Curves`, and an `exterior` set of all other
  points including those within holes that might exist in the surface. A
  `Surface` has a topological dimension of 2.

That may seem a bit esoteric, but will help clarify the meanings of Shapely's
spatial predicates, and it's as deep into theory as this manual will go.
Consequences of point-set theory, including some that manifest themselves as
"gotchas", for different classes will be discussed later in this manual.

The point type is implemented by a `Point` class; curve by the `LineString` and
`LinearRing` classes; and surface by a `Polygon` class. Shapely implements no
smooth (`i.e.` having continuous tangents) curves. All curves must be
approximated by linear splines. All rounded patches must be approximated by
regions bounded by linear splines.

Collections of points are implemented by a `MultiPoint` class, collections of
curves by a `MultiLineString` class, and collections of surfaces by a
`MultiPolygon` class. These collections aren't computationally significant, but
are useful for modeling certain kinds of features. A Y-shaped line feature, for
example, is well modeled as a whole by a `MultiLineString`.

The standard data model has additional constraints specific to certain types
of geometric objects that will be discussed in following sections of this
manual.

See also http://www.vividsolutions.com/jts/discussion.htm#spatialDataModel
for more illustrations of this data model.

.. _intro-relationships:

Relationships
-------------

The spatial data model is accompanied by a group of natural language
relationships between geometric objects â€“ `contains`, `intersects`, `overlaps`,
`touches`, etc. â€“ and a theoretical framework for understanding them using the
3x3 matrix of the mutual intersections of their component point sets [2]_: the
DE-9IM. A comprehensive review of the relationships in terms of the DE-9IM is
found in [4]_ and will not be reiterated in this manual.

.. _intro-operations:

Operations
----------

Following the JTS technical specs [5]_, this manual will make a distinction
between constructive (`buffer`, `convex hull`) and set-theoretic operations
(`intersection`, `union`, etc.). The individual operations will be fully
described in a following section of the manual.

.. _intro-coordinate-systems:

Coordinate Systems
------------------

Even though the Earth is not flat â€“Â and for that matter not exactly spherical â€“
there are many analytic problems that can be approached by transforming Earth
features to a Cartesian plane, applying tried and true algorithms, and then
transforming the results back to geographic coordinates.  This practice is as
old as the tradition of accurate paper maps.

Shapely does not support coordinate system transformations. All operations on
two or more features presume that the features exist in the same Cartesian
plane.

.. _objects:

Geometric Objects
=================

Geometric objects are created in the typical Python fashion, using the classes
themselves as instance factories. A few of their intrinsic properties will be
discussed in this sections, others in the following sections on operations and
serializations.

Instances of `Point`, `LineString`, and `LinearRing` have as their most
important attribute a finite sequence of coordinates that determines their
interior, boundary, and exterior point sets. A line string can be determined by
as few as 2 points, but contains an infinite number of points. Coordinate
sequences are immutable. A third `z` coordinate value may be used when
constructing instances, but has no effect on geometric analysis.  All
operations are performed in the `x-y` plane.

In all constructors, numeric values are converted to type ``float``. In other
words, ``Point(0, 0)`` and ``Point(0.0, 0.0)`` produce geometrically equivalent
instances. Shapely does not check the topological simplicity or validity of
instances when they are constructed as the cost is unwarranted in most cases.
Validating factories are trivially implemented, using the :attr:`is_valid`
predicate, by users that require them.

