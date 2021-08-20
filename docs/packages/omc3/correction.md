# OMC3 Optics Corrections Workflow
This page contains a walk-through of how to perform a global correction us. To follow along, the reader needs to have installed the omc3 package and to have measurement or simulation data to use the codes on. In addition, the modifiers file (opticsfile) coresponding to the simulated data is needed.
## Optics Correction workflow
Before performing the global correction one must perform frequency and optics analysis in order to get the .tfs files for the quantities you want to correct. The analysis is done according to this workflow (TODO: cite workflow). If one wants to perform a correction based on a twiss file, this script (TODO: refrence fake_measurement_file) can be used to convert the twiss into the correct format for the global correction. The path to the folder where the tfs files are outputed is assumed to be meas_dir in this page.

The response creator and global correction code, both take a model directory as a input. the model is generated with the follwing code
```bash
python -m omc3.model_creator \
    --accel lhc \
    --type nominal \
    --year 2018 \
    --beam 1 \
    --energy 6.5 \
    --ats True \ (True or true in command line??)
    --nat_tunes 62.31 60.32 \
    --drv_tunes 62.30 60.332 \
    --driven_excitation acd \
    --dpp 0. \
    --modifiers modifiers \
    --outputdir lhc_model
```
Where the modifiers, tunes, beam, etc must correspond to the state of the machine when the measurement was performed. The next step is to create the responsematrix wich is done with the following code
```bash
python -m omc3.create_response_entrypoint \
        --model_dir lhc_model \
        --accel lhc \
        --year 2018 \
        --energy 6.5 \
        --beam = 1 \
        --ats True \
        --delta_k 0.00002 \
        --variable_categories coupling_knobs \
        --outfile_path responsematrix \   
```
Where the variable categories specify which variables will be included in the responsematrix. The responsematrix is stored at the path specified by ``responsematrix``. After c
```
 python -m omc3.global_correction_entrypoint \
        --accel lhc \
        --year 2018 \
        --energy 6.5 \
        --beam 1 \
        --ats True \
        --model_dir lhc_model \
        --meas_dir meas_dir \
        --variable_categories coupling_knobs \
        --fullresponse_path responsematrix \
        --optics_params = F1001R F1001I \
        --weights = 1. 1. \
        --output_dir = output_dir \
        --svd_cut = 0.01 \
        --max_iter = 1 \
        )
```
