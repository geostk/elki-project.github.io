---
layout: page
title: Release Notes 0.6.5~20141030
---


ELKI 0.6.5~20141030 release notes
=================================

- Major refactoring of distances - removal of `Distance` values and removed support for non-`double`-valued distance functions. While this reduces the generality of ELKI, we could remove about 2.5% of the codebase by not having to have optimized codepaths for double-distance anymore. Generics for distances were present in almost any distance-based algorithm, and we were also happy to reduce the use of generics this way. Support for non-double-valued distances can trivially be added again, e.g. by adding the specialization one level higher: at the query instead of the distance level, for example.
- In this process, `NumberVector` was also stripped off its generic. The object-based `get` was deprecated for a good reason long ago, and e.g. `doubleValue` are more efficient (even for non-`DoubleVector`s).

- Dropped some long-deprecated classes

- K-means
  - speedups for some initialization heuristics
  - K-means++ initialization no longer squares distances (again)
  - farthest-point heuristics now uses minimum instead of sum (renamed)
- additional evaluation criteria
- CLARA clustering
- LSDBC clustering
- X-means
- kNN classification (with index acceleration)

- Parallel computation framework, and some parallelized algorithms
- Parallel k-means
- Parallel LOF and variants

- LibSVM format parser

- Silhouette index for evaluating clusterings of unlabeled data

- Additional statistical dependence measures
- Distance correlation
- Hoeffings D
- Some divergence / mutual information measures

- Time series distances refactored, allow variable length series now
- Hellinger distance and kernel function

- bug fix in kNN weight, when distances are tied and kNN yields more than k results.
- kNN and kNN weight outlier have their k parameter changed: old 2NN outlier is now 1NN outlier, as commonly understood in classification literature (1 nearest neighbor *other than the query object*; whereas in database literature the 1NN is usually the query object itself). You can get the old result back by decreasing `k` by one easily.
- KDEOS outlier detection (SDM14)
- Precomputed distance matrix "index".
- iDistance index.
- Inverted-list index for sparse data and cosine/arccosine distance.
- Improved APRIORI implementation.
- LOCI implementation is now only O(n<sup>3</sup> log n) instead of O(n<sup>4</sup>).
- k-means based outlier detection (distance to centroid) and Silhouette coefficient based approach (which does not work too well on the toy data sets - the lowest silhouette are usually where two clusters touch).
- EM clustering was refactored and moved into its own package. The new version is much more extensible.

- MiniGUI has two "secret" new options: `-minigui.last -minigui.autorun` to load the last saved configuration and run it, for convenience.

- Logging API has been extended, to make logging more convenient in a number of places (saving some lines for progress logging and timing).


