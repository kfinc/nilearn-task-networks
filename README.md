# nilearn_task_networks
Building a pipeline and tutorial for task fMRI analysis from nistats to nilearn 

## Data description
Human Connectome Project N-back task fMRI data (N = 35)

Emotional Music (N = 21; 11 controls and 10 patients w/ MDD)

## N-back task description
Within each run, the 4 different image types are presented in separate blocks within the run. Within each run, ½ of the blocks use a 2-back working memory task (respond ‘target’ whenever the current stimulus is the same as the one two back) and ½ use a 0-back working memory task (a target cue is presented at the start of each block [(Barch et al. 2013, NeuroImage](https://www.sciencedirect.com/science/article/pii/S1053811913005351)[; Moser et al. 2017, Molecular Psychiatry)](https://www.nature.com/articles/mp2017247).

## Emotional music description
Participants listened to blocks of positive and negative music. (2x2 matrix: MDD vs. control; postive vs. negative music) [(Lepping et al. 2016, PLOS ONE)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4902194/pdf/pone.0156859.pdf)

## Pipeline overview
[Data processing and signal extraction:](https://github.com/kfinc/nilearn_task_networks/blob/master/glm_hcp.ipynb)

[Peak ROI connectivity analysis for HCP](https://github.com/kfinc/nilearn_task_networks/blob/master/nilearn_HCP_pipeline.ipynb)

[Peak ROI connectivity analysis for emotional music](https://github.com/kfinc/nilearn_task_networks/blob/master/nistats_task_activations_demo_music_comb_groups.ipynb)

[Whole brain connectivity analysis for emotional music](https://github.com/kfinc/nilearn_task_networks/blob/master/nilearn_musictask_powerparcellation.ipynb)

### Nistats steps
1. Load [Working Memory fMRI HCP data](https://db.humanconnectome.org/) or [Emotional Music fMRI data](https://openneuro.org/datasets/ds000171)
  * tfMRI_WM_RL.nii.gz <- BOLD data for run 1
2. Smoothing
3. Define the design matrix using onset timing
4. Conduct GLM (including appropriate confounds)
5. Compute contrasts (e.g., 2back, 0back, and 2back vs. 0back)
6. Save z_maps and peak ROI coordinates 

### Nilearn analyses
1. Peak ROI connectivity analysis
2. Whole brain connectivity analysis

