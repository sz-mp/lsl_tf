## testing LSL and timeflux
LSL + Timeflux as a potential experimental infrastructure.

### install
- install conda environment with `conda env create -f environment.yml` 
- only tested on macos, might need to install liblsl differently for other OSs first
  
### running the demo
- activate the conda environment `conda activate pylsl`
- start LSL stream by running `python send_data.py`, which generates random 8-channel EEG data
- in another terminal, start timeflux by running `timeflux -d test_timeflux.yaml` (d for debug)
  - it will receive the data from LSL
  - do some basic sigproc (by adding 1 to the signal)
  - stream to a monitor (visible in a browser tab in the following [link](http://localhost:8000/monitor/))
  - save the data to a new subdirectory called `./data` in hdf5 format

### possible extensions
- timeflux allows creating individual plugins using their [template](https://github.com/timeflux/timeflux_example)
- some [sigproc](https://github.com/timeflux/timeflux_dsp) and [ML tools](https://github.com/timeflux/timeflux/blob/master/timeflux/nodes/ml.py) already available as exisiting plugins

### TODOs
- make brain product and vive eye tracking data play well with it