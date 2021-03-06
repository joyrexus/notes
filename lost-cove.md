# Groundwater Flow

Inspired by the wind flow maps of [Viegas & Wattenberg](http://hint.fm/wind/) and [Cameron Beccario](http://earth.nullschool.net/), I'd like to design a map of the water flow (groundwater flowlines and subsurface flow) in Lost Cove.

Lost Cove is located in Franklin County, TN, near the eastern edge of the Southern Cumberland Plateau.  It's a short walk from the campus of the University of the South, which now manages the land.  In early 2008, Sewanee purchased the Cove's 3,000-acres, with a conservation easement held by The Land Trust for Tennessee.  Under the auspices of Sewanee's Environmental Institute, it now serves as a living laboratory for environmental stewardship, fieldwork, and research.

The Cove contains a large underground [watershed](http://en.wikipedia.org/wiki/Drainage_basin) with a fluctuating water table, consisting of a complex karst geology.  I've come across some references to work that's already been undertaken to map out its watershed network and flowlines.  See references and extracts below.

For the project I have in mind, the exact representation has yet to be determined.  In fact, the real problem driving this nascent project is that of the representation of natural processes: how to devise representations that are accurate, illuminating, and aesthetically pleasing? In this case, the representation of water flow through a subsurface watershed.  We need to think through the possibilities.  

The maps of wind flow beautifully illuminate a single natural process represented at a macro scale, where surface features are abstracted away.  Water flows, such as the [US River network](https://github.com/NelsonMinar/vector-river-map), can be represented in essentially the same way.  However, by focusing on a particular geographic region like Lost Cove, working at a meso- or even micro- scale, we no longer need to isolate water flow as a process from the other geological features which determine or impact that process.  We can try to represent this phenomena within the watershed as a whole, as a [drainage system](http://en.wikipedia.org/wiki/Drainage_system_(geomorphology)), where the geomorphic features of the land play a constitutive role.  Rather than abstracting away the topography and geomorphology of Lost Cove, we'd like to render water flows in and through the natural terrain.

With [Eduard Imhof](http://www.reliefshading.com/cartographers/imhof/), relief presentation became both a [coherent discipline](http://esripress.esri.com/display/index.cfm?fuseaction=display&websiteID=118) and [high art](http://www.library.ethz.ch/exhibit/imhof/imhof3_e.html).  How might Imhof's cartographic techniques be extended to incorporate the representation of **natural processes** occurring at the surface and subsurface layers?

For this project I'd like to investigate the applicability of some of the relatively recent work that's been done on [algorithms for elevation models](http://www.win.tue.nl/~hermanh/doku.php?id=algorithms_for_geographic_elevation_models) for inferring flow lines.  Some of the innovative techniques coming out of Bernhard Jenny's [Cartography and Geovisualization Group](http://cartography.oregonstate.edu/index.html), extending Imhof's work on terrain rendering, might be useful as well.

---

> **The complex karst geology of Lost Cove, a 39 km2 watershed in the southeast
quadrant of the 7.5’ Sewanee, TN Quadrangle, has been mapped using global
positioning systems (GPS), Arcview Geographic Information System (GIS), and
aerial photography.**  
>  
> **The most prominent sinks and springs in the Mississippian
Monteagle Limestone on the floor of Lost Cove along Lost Creek have been
monitored over the past year to study the effects of a fluctuating water
table.**  
>  
> During periods of heavy rain, a rising water table activates ephemeral springs
and streams found throughout the floor of Lost Cove. Most of the water
ultimately reaches the Big Sink, where it drops 40 m over the next 1.2 km in
the Buggytop Cave system and emerges as Crow Creek. **Detailed subsurface maps of
the Cove are preliminary**, and have not yet demonstrated that all surface water
enters the Buggytop system. Dye tracing in major sinks and springs of a major
tributary, Champion Cove, is underway but has already demonstrated there is no
direct connection between Prince Spring and the major upstream sink to the
northeast. Older dye traces on the eastern end of Champion Cove at Temple Sink
suggest no direct connection to the Lost Cove, Big Sink, or Buggytop systems.
**Other groundwater flowlines throughout lower Lost Cove continue to be traced
and mapped. Future work will include a comparison between calculated and
observed recharge and discharge throughout Lost Cove.**

- [Preliminary hydrologic mapping of groundwater flowlines in Lost Cove](https://gsa.confex.com/gsa/2003sc/finalprogram/abstract_49876.htm)

---

> Lost Cove, a topographic depression draining 39 sq km, is located in the
> Sewanee Quadrangle near the eastern edge of the Southern Cumberland Plateau.
> The cove is rimmed by Warren Point Sandstone bluffs of early Pennsylvanian
> age which overlie late Mississippian Pennington and Bangor Limestones. The
> lower slopes and floor of the cove are fossiliferous and oolitic
> Mississippian Monteagle Limestone, and exhibit typical karst features that
> include numerous sinks and springs along Lost Creek and its tributaries.
> Several times in a typical year rainfall exceeds the capacity of the sinks
> for a few days at a time, and an impoundment of up to 10 acres forms adjacent
> to the lowest point within the cove, the Big Sink. The Big Sink/Buggytop cave
> system at the southern end of Lost Cove is **the only documented
> joint-controlled karst conduit in the area**, but this study also demonstrates
> strong joint control of cave passages in the vicinity of Kirk Spring and
> other openings in the upper Monteagle Limestone near the floor of Lost Cove.
> **Surface and subsurface flows in the vicinity of Kirk Spring typically change
> direction over the course of several precipitation events.** The strongest
> fracture trends are concentrated at azimuths of 25, 40, and 126 degrees, with
> the 126-degree trend the most consistent throughout the
> Mississippian-Pennsylvanian section. **The fieldwork investigates the
> relationship between major fracture trends and the volume and direction of
> flow in sinks and springs at times of drought and high water.**

- [Effects of Joint Systems on Karst Features and Water Flow In Lost Cove](https://gsa.confex.com/gsa/2005AM/finalprogram/abstract_94958.htm)

---

## Resources

* [lost cove cave](http://en.wikipedia.org/wiki/Lost_Cove_Cave) - Lost Cove
  Cave is a part of the Carter Natural Area section of South Cumberland State
  Park and is located in Lost Cove

* [carter natural area](http://www.state.tn.us/environment/natural-areas/natural-areas/mrnmrscarter) - The Mr. and Mrs. Harry Lee Carter Natural Area is a 375-acre natural area located in Franklin County that is part of the South Cumberland Recreation Area. Named after the couple who donated the land to the state, this natural area protects part of a large solution valley associated with the karst erosional processes characteristic of the Cumberland Plateau escarpment. A significant cave system extends from Lost Cove to the head of Crow Creek. The stream systems draining into Lost Cove disappear into the Lost Cove Cave at the Big Sinks and travel underground for over a mile, emerging at the main entrance Buggytop Cave. 

* [guntersville lake watershed](http://www.tn.gov/environment/water/watersheds/guntersville-lake.shtml) - Lost Cove is a subwatershed the Guntersville Lake Watershed of the Tennessee River Basin

* [ground water and surface water: a single resource](http://pubs.usgs.gov/circ/circ1139/index.html) - USGS report on natural processes affecting ground-water / surface-water interation

* [water resources of the US](http://www.usgs.gov/water/) - comrehensive
  info on the nation's water resources offered by the USGS, including 
  [groundwater modeling software](http://water.usgs.gov/software/lists/groundwater/)

* [tn-gis](http://www.tngis.org/) - Tennessee GIS clearinghouse

---

* [vector-river-map](https://github.com/NelsonMinar/vector-river-map) - Nelson Minar's tutorial demonstrating how to make vector-based web map of the US river network

* [algorithms for elevation models](http://www.win.tue.nl/~hermanh/doku.php?id=algorithms_for_geographic_elevation_models) - algorithms to analyse the flow of water across a terrain given a digital elevation model

---

* [w randolph franklin](http://www.ecse.rpi.edu/Homepages/wrf/pmwiki/pmwiki.php/Research/Research) - the research of W. Randolph Franklin at RPI focuses on data structures and algorithms for computational cartography, much of it focused on the effecient representation and processing of terrain (surface elevation models)

* [brian klinkenberg](http://ibis.geog.ubc.ca/~brian/) - including work on
  the automatic detection of landforms

* [fernando schwartz](http://www.math.utk.edu/~fernando/index.html) - asst prof
  at UT Knoxville doing work in computational geometry/topology

* [TGDA@OSU](https://research.math.osu.edu/tgda/) - topology, geometry, and
  data analysis at OSU

* [appliedtopology.org](http://appliedtopology.org/) - feed and preprints

* [applied algebraic topology research network](https://www.ima.umn.edu/topology/) - promotes and enables collaboration in algebraic topology applied to the sciences and engineering by connecting researchers through a virtual institute

---

* [topography](http://en.wikipedia.org/wiki/Topography) - the study of surface
  shape and features of the Earth

* [geomorphology](http://en.wikipedia.org/wiki/Geomorphology) - the scientific
  study of the origin and evolution of topographic and bathymetric features
  created by physical or chemical processes operating at or near Earth's
  surface
  * [physical landscape](http://en.wikipedia.org/wiki/Landscape#Physical_landscape) 
  * [landform](http://en.wikipedia.org/wiki/Landform)

* [geomorphometry](http://en.wikipedia.org/wiki/Geomorphometry) - the science
  of quantitative land surface analysis
  * [open geomorphometry project](http://en.wikipedia.org/wiki/Open-geomorphometry_project) - an open library for analyzing DEMs

* [geomorphometrics](http://en.wikipedia.org/wiki/Geomorphometrics) - the
  discipline based on the computational measures of the geometry, topography
  and shape of the Earth's horizons, and their temporal change

* [geohydrology](http://en.wikipedia.org/wiki/Hydrogeology)
  * [subsurface flow](http://en.wikipedia.org/wiki/Subsurface_flow)
  * [groundwater](http://en.wikipedia.org/wiki/Groundwater) 
    * [model](http://en.wikipedia.org/wiki/Groundwater_model)
    * [flow](http://en.wikipedia.org/wiki/Groundwater_flow)
    * [flow equation](http://en.wikipedia.org/wiki/Groundwater_flow_equation)
