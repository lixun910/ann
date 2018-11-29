# ANN: A Library for Approximate Nearest Neighbor Searching

Authors: David M. Mount and Sunil Arya

Website: https://www.cs.umd.edu/~mount/ANN/

## Update:
This version is based on original ANN libray version 1.1.2, and I added some small changes to make it working as a library for GeoDa Software. 

The purpose of the changes is to allow user to specify the distance metric as a parameter when create ANN tree. 

A global variable `ANNdistMetric` and an enum `ANN_DIST_METRIC` have been added:
```C++
enum ANN_DIST_METRIC { ANNManhattan, ANNEuclidean };

extern ANN_DIST_METRIC ANNdistMetric;
```
This is a global control variable, to use just specify the value of ANNdistMetric before creating ANN tree

```C++
ANNdistMetric = ANNEuclidean;
ANNkd_tree* kdTree = new ANNkd_tree(data, n_rows, n_cols /*dim*/);
```
