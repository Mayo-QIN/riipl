# riipl

A [grunt](https://github.com/Mayo-QIN/grunt) enabled Docker based on https://hub.docker.com/r/riipl/3d_qifp/.

Building:

    docker build -t mayoqin/riipl .

Running interactively:

    docker run --rm -it -p 9901:9901 mayoqin/riipl

## Example `config.ini` file

The `riipl/3d_qifp` processing engine requires a `config.ini` file for processing.  For the Docker to function correctly, the `global|parallelMode="none"` setting is critical.  Using a parallel environment fails on the docker.

```
global|parallelMode="none"
global|numberOfProcessors="max"
global|uidToProcess="all"
 
input|component="dsoLoader"
 
featureComputation|components="information,size,intensity,sphericity,roughness,edgeSigmoidFitting,lvii,glcm"
 
output|components="csvOutput,maxAreaImage"
 
edgeSigmoidFitting|numberOfNormals=1200
 
csvOutput|final=true
csvOutput|each=false
 
maxAreaImage|each=true
maxAreaImage|windowLevelPreset="ctLung"

preprocessing|components="maximumConnected,holeFilling"

csvOutput|outputRootName="3D"
```
