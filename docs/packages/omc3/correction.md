# OMC3 Optics Corrections Workflow
This page contains a walk-through of how to perform a global correction us. To follow along, the reader needs to have installed the omc3 package and to have measurement or simulation data to use the codes on. In addition, the modifiers file (opticsfile) coresponding to the simulated data is needed.
## Optics Correction workflow
Before performing the global correction one must perform frequency and optics analysis in order to get the .tfs files for the quantities you want to correct. The analysis is done according to this workflow (TODO: cite workflow). If one wants to perform a correction based on a twiss file, this script (TODO: refrence fake_measurement_file) can be used to convert the twiss into the correct format for the global correction. 

The response creator and global correction code, both take a model directory as a input. To genereate this model on
```python
python -m omc3.model_creator \
    --accel lhc \
    --type nominal \
    --year 2018 \
    --beam 1 \
    --energy 6.5 \
    --nat_tunes 62.31 60.32 \
    --modifiers /afs/cern.ch/eng/lhc/optics/runII/2018/PROTON/opticsfile.22 \
    --outputdir lhc_model
```
Go and write now :)
