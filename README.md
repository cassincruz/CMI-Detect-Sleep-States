# CMI-Detect-Sleep-States
Detecting sleep states for the Child Mind Institute Kaggle competition. 

In this notebook I: 
- Use the Polars library to load and transform the CMI dataset and incorporate features inspired by the work done in my Sleep Data Exploration notebook.
- Import and implement the Event Detection AP score function to validate results prior to submission.
- Define helper functions to create training sets and formatted submissions based on classifier results.
- Train a Random Forest classifier (as well as gradient boost classifier) and use the above work to validate and create a submission.

My approach is based on the observation that during sleep states the time series behaves more like a jump process, while during wakeful stages it behaves like a diffusion process. I use rolling total variation to engineer features which are used to train a random forest classifier to determine whether participant is awake or asleep. 
