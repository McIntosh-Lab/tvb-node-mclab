# Frequently Asked Questions (FAQ)

## Can I create TVB models without individualized MRI data?
It is possible to model datasets that lack individualized MRI. Some approaches include:
- Population-averaged connectomes: using age-matched average structural connectivities from openly available datasets.
- Alternative constraints: everyone receives the same structural connectivity, but the models are informed by other imaging such as [PET](https://www.frontiersin.org/journals/computational-neuroscience/articles/10.3389/fncom.2019.00054/full) or known features such as lesions.

The approach you take will depend on the research questions you want to address.

## Can I apply TVB to MEG or EEG data?
[This tutorial](https://thevirtualbrain.org/tvb/zwei/newswire-educase/single/42189-learn-neural-masses-as-source-models-for-eeg-and-meg) covers the selection of neural mass models for MEG and EEG modelling. The TVB-node workshop focuses on fMRI, but the similar modelling principles apply to MEG and EEG. Key steps are:
1. Determining what MEG or EEG features you want to fit the models to.
2. Ensuring that your neural mass model can reproduce those features.
