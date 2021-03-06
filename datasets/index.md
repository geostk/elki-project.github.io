---
layout: page
title: Data sets
section: datasets
navigation: 15
---


Example data sets for ELKI
==========================

We are collecting a few example data sets along with a description to try out ELKI. Many of the data sets are artificial test cases that we use in internal unit testing, and are not well suited for benchmarking due to various biases, but mostly meant for use in *teaching*. Often they work near-perfectly for one algorithm, while another algorithm fails badly and are used to explain strengths and weaknesses of different approaches. They are not meant to even just resemble real data.

The XML files are data sets specifications for use with the [data set generator](generator).

Artificial data sets
--------------------

| **Data set name** | **Size** | **Dim.** | **Properties** | **Parameters** | **Files** |
|-------------------|----------|----------|----------------|----------------|-----------|
| Vary Density      | 150      | 2        |3 Gaussian clusters with variable density<br>Easy for EM, hard for density clustering|em.k=3|[CSV](https://github.com/elki-project/elki/blob/master/data/synthetic/ABC-publication/pov.csv), [XML](https://github.com/elki-project/elki/blob/master/data/synthetic/ABC-publication/pov.xml)|
|Mouse|500|2|3 Gaussian clusters and noise<br>For comparing EM and kMeans|em.k=3<br>kmeans.k=3|[CSV](https://github.com/elki-project/elki/blob/master/data/synthetic/Vorlesung/mouse.csv), [XML](https://github.com/elki-project/elki/blob/master/data/synthetic/Vorlesung/mouse.xml)|

[Toy data sets used in LoOP publication](https://github.com/elki-project/elki/blob/master/data/synthetic/LoOP-publication)

See [SNN data sets](http://fogo.dbs.ifi.lmu.de/cms/Research/SNN/DataSets) for a number of high dimensional artificial data sets.

Real data sets
--------------

See [multi-view](multi_view) for data sets such as the ALOI data set.

[Outlier data sets](outlier) are hosted at the [outlier detection data repository][outl1] ([mirror][outl2]).

[outl1]: http://www.dbs.ifi.lmu.de/research/outlier-evaluation/
[outl2]: http://lapad-web.icmc.usp.br/repositories/outlier-evaluation/

More to come!
