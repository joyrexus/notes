# Behaviors

We want a system that lets us work with dynamic/evolving values (i.e., values that change over time). We might call such values "behaviors".  A behavior is a function of time: it changes (over time) and has a current state (at the present moment).

The behaviors we'll be dealing with are typically sensor-driven: an event stream. Each event has an associated time and value.

Given a set of behaviors, we want a vocabulary for composing new behaviors, by filtering, transforming, and combining existing behaviors.

(In [bacon.js](https://github.com/baconjs/bacon.js#intro) terminology, things that change and have a current state are called **Properties**, while things that consist of discrete events are **EventStreams**.)
