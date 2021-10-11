# The Beta-Beat GUI Model Creation
The model creation is the first step to be done before starting analysing the files. 
## Settings Tab
The first thing to set it the modifiers file which will define the optics. This can for example be injection but sometimes they also have more compicated the names 
## Tunes Tab
Input the tunes for the measurement in question. 
<figure>
  <img src="../../../assets/images/betabeat_gui/tune_model_creation.png" width="90%" />
  <figcaption>Tune for the model creation.</figcaption>
</figure>

## Misc Tab

This is to check if a fullresponse should be created, which is needed for calculating corrections. The dpp in here is only when the nominal beam has a dpp which is not the case for protons.
Normally nothing should be changed here. 
<figure>
  <img src="../../../assets/images/betabeat_gui/tunes_input.png" width="90%" />
  <figcaption>Misc for model creation.</figcaption>
</figure>

## Best Knowledge
The best knolwedge model is used to get accurate estimates of the beta-function and the associated error bars. Here one should chose the energy and make sure to extract the settings of the MQTs.
The best knowledge model has no impact on the corrections we normally perform. 
<figure>
  <img src="../../../assets/images/betabeat_gui/best_knowledge.png" width="90%" />
  <figcaption>.</figcaption>
</figure>