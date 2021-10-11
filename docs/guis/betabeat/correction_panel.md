# The Beta-Beat GUI Correction Panel

The `Correction` panel displays the corrections computed from the `Optics` panel to bring back the measured machine to nominal model conditions.
Note that the convention is to correct in MAD-X which means that the corrections for the skew elements need to be inverted or the knob needs to be trimmed to -1. 

It provides an `Open Knob Panel` button to access the LHC beam process list.
## Corection Test Panel
Before any global correction is sent to LSA it should be verfied. One way of doing this is to use the correction tests. 
The file containing the corrections need to be loaded and then run. 

<figure>
  <img src="../../../assets/images/betabeat_gui/correction_evaluation.png" width="90%" />
  <figcaption>Evaluation of calculated correction.</figcaption>
</figure>

## The Knob Panel

Through the `Knob Panel`, corrections can be provided directly inside the LHC beam system.

!!! info
    Being inside of the Technical Network is required for the KnobPanel.
    To do so, `ssh` into one of the hosts, for instance `cs-ccr-dev<number>.cern.ch`.

In the `Knob Panel`, one can create Knobs (in the `Creation` tab) by using the previously computed corrections.

To create a knob, one or several beam processes have to be selected.
Once selected, the corresponding optics will appear.
At least one optic has to be selected.

After providing a `Knob name`, the `Create Knob` button will create a new Knob given that the user has the rights. 
!!! All the EIC have the rights to assign this role to any user but might not necessairly have the right them self (but they can self asign.)
<figure>
  <img src="../../../assets/images/betabeat_gui/create_knob.png" width="90%" />
  <figcaption>Knob panel to create a knob.</figcaption>
</figure>

The `View Knobs` tab displays a list of all BETA-BEATING Knobs.
By selecting one, the user can examine or visualize the values attributed to each component.

!!! todo
    Include a screenshot of the Knob Panel view knobs table

!!! todo
    Include a screenshot of the Knob Panel view knobs chart