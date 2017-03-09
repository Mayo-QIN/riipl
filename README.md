# riipl

A [grunt](https://github.com/Mayo-QIN/grunt) enabled Docker based on https://hub.docker.com/r/riipl/3d_qifp/.

From the `riipl/3d_qifp` Docker's readme:

```
The docker container contains the feature pipeline runner at
/riipl/runFeaturePipeline. This program takes in 3 inputs in the
following order:

  <directory path with a DSO> <directory path with DICOM series> <output directory path>

Here is an example of how to run the program (assuming the local
~/feature_data path holds the 3 input directories):

  docker run -v ~/feature_data:/riipl/data -i -t riipl/feature ./runFeaturePipeline /riipl/data/dso /riipl/data/series /riipl/data/output

The output directory should contain a boundary image and a scores csv
file. The boundary image should show a correct segmentation of a
tumor. The scores csv file should be checked with Sebastian's standard
set of scores to see if they are reasonable.

Look inside the example_output directory to see some example outputs.
```

