## Preprocessing pipeline for this Dataset using EEGLAB (MATLAB), as explained in the README:
-----------------

 (1) Load channel locations from ModGSN-HydroCel-257.sfp with Cz as reference

 (2) Highpass filter at 0.1 Hz (pop_eegfiltnew)

 (3) Lowpass filter at 50 Hz (pop_eegfiltnew)

 (4) Line noise removal with CleanLine at 60 and 120 Hz (bandwidth=2, tau=100, winsize=4, winstep=3)

 (5) Automatic channel rejection by kurtosis (threshold=2, normalized, applied twice; pop_rejchan)

 (6) Manual channel rejection based on visual inspection of scrolling data and spectral properties

 (7) Average re-reference (pop_reref)

 (8) ICA decomposition (runica, extended=1)

 (9) ICLabel component classification, flagging non-brain components with >0.8 probability (muscle, eye, heart, line noise, channel noise)

 (10) Manual verification of flagged components (pop_selectcomps)

 (11) Removal of flagged ICA components

 (12) Spherical interpolation of rejected channels using channel locations from the pre-rejection filtered data (pop_interp, method=spherical).