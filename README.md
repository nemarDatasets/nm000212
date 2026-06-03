[![DOI](https://img.shields.io/badge/DOI-10.82901%2Fnemar.nm000212-blue)](https://doi.org/10.82901/nemar.nm000212)

# BNCI 2015-007 Motion VEP (mVEP) Speller dataset

BNCI 2015-007 Motion VEP (mVEP) Speller dataset.

## Dataset Overview

- **Code**: BNCI2015-007
- **Paradigm**: p300
- **DOI**: 10.1088/1741-2560/9/4/045006
- **Subjects**: 16
- **Sessions per subject**: 1
- **Events**: Target=1, NonTarget=2
- **Trial interval**: [0, 0.7] s
- **Runs per session**: 2
- **Session IDs**: practice, calibration, copy_spelling, free_spelling
- **File format**: gdf
- **Data preprocessed**: True

## Acquisition

- **Sampling rate**: 100.0 Hz
- **Number of channels**: 63
- **Channel types**: eeg=63
- **Channel names**: Fp1, Fp2, AF3, AF4, AF7, AF8, Fz, F1, F2, F3, F4, F5, F6, F7, F8, F9, F10, FCz, FC1, FC2, FC3, FC4, FC5, FC6, FT7, FT8, T7, T8, Cz, C1, C2, C3, C4, C5, C6, TP7, TP8, CPz, CP1, CP2, CP3, CP4, CP5, CP6, Pz, P1, P2, P3, P4, P5, P6, P7, P8, P9, P10, POz, PO3, PO4, PO7, PO8, Oz, O1, O2
- **Montage**: 10-10
- **Hardware**: BrainAmp EEG amplifier
- **Software**: Pyff, VisionEgg, MATLAB
- **Reference**: linked mastoids
- **Ground**: forehead
- **Sensor type**: active electrode
- **Line frequency**: 50.0 Hz
- **Online filters**: hardware bandpass filter 0.016–250 Hz
- **Impedance threshold**: 10.0 kOhm
- **Cap manufacturer**: Brain Products
- **Electrode type**: actiCap active electrode system

## Participants

- **Number of subjects**: 16
- **Health status**: patients
- **Clinical population**: Healthy
- **Age**: mean=23.8, min=21, max=30
- **Gender distribution**: male=10, female=6
- **Handedness**: normal or corrected-to-normal vision
- **BCI experience**: naive
- **Species**: human

## Experimental Protocol

- **Paradigm**: p300
- **Task type**: visual_speller
- **Number of classes**: 2
- **Class labels**: Target, NonTarget
- **Trial duration**: 30.0 s
- **Study design**: Three different Cake Speller modifications: Overt Cake Speller (gaze toward target), Covert Cake Speller (central fixation, covert attention), Motion Center Speller (foveal stimulation). Two-level selection (group-level and symbol-level) from 30 symbols.
- **Study domain**: gaze-independent communication
- **Feedback type**: visual
- **Stimulus type**: motion VEP (mVEP)
- **Stimulus modalities**: visual
- **Primary modality**: visual
- **Synchronicity**: synchronous
- **Mode**: online
- **Training/test split**: True
- **Instructions**: Copy-spelling and free-spelling with attention to target symbols. Participants counted moving bar/pattern presentations in target location.
- **Stimulus presentation**: soa_ms=200 ms (Cake Spellers) or 266 ms (Motion Center Speller), stimulus_duration_ms=100 ms, isi_ms=100 ms, repetitions=10 repetitions per level, total_presentations=120 per selection (2 levels × 10 repetitions × 6 groups/symbols)

## HED Event Annotations

Schema: HED 8.4.0 | Browse: https://www.hedtags.org/hed-schema-browser

```
  Target
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Target

  NonTarget
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Non-target

```
## Paradigm-Specific Parameters

- **Detected paradigm**: p300
- **Number of targets**: 6
- **Number of repetitions**: 10
- **Inter-stimulus interval**: 100.0 ms
- **Stimulus onset asynchrony**: 200.0 ms

## Data Structure

- **Trials**: 120
- **Blocks per session**: 4
- **Trials context**: per_selection (2 levels × 10 repetitions × 6 groups/symbols)

## Preprocessing

- **Data state**: filtered
- **Preprocessing applied**: True
- **Steps**: downsampling, low-pass filter, baseline correction, artifact rejection
- **Highpass filter**: 0.016 Hz
- **Lowpass filter**: 250.0 Hz
- **Bandpass filter**: {'low_cutoff_hz': 0.016, 'high_cutoff_hz': 250.0}
- **Filter type**: hardware bandpass, Chebyshev low-pass for offline
- **Artifact methods**: min-max criterion (70 μV), variance criterion
- **Re-reference**: linked mastoids
- **Downsampled to**: 100.0 Hz
- **Epoch window**: [-0.2, 1.0]
- **Notes**: For offline analysis: downsampled to 200 Hz, low-pass filtered (42 Hz passband, 49 Hz stopband). For online: downsampled to 100 Hz. Artifact rejection: min-max ≥70 μV. Nontarget epochs filtered to avoid overlap with targets (3 preceding and 4 following stimuli must be nontargets).

## Signal Processing

- **Classifiers**: LDA with shrinkage of covariance matrix
- **Feature extraction**: signed square values of point-biserial correlation coefficients
- **Frequency bands**: analyzed=[100.0, 800.0] Hz
- **Spatial filters**: LDA spatial filter

## Cross-Validation

- **Method**: train on calibration, test on copy-spelling and free-spelling
- **Evaluation type**: within_session

## Performance (Original Study)

- **N200 Latency Overt Ms**: 164.0
- **N200 Latency Covert Ms**: 180.0
- **N200 Latency Motion Center Ms**: 198.0
- **P300 Latency Range Ms**: 300-500
- **N200 Latency Range Ms**: 100-250

## BCI Application

- **Applications**: speller, communication
- **Environment**: laboratory
- **Online feedback**: True

## Tags

- **Pathology**: Healthy
- **Modality**: Visual
- **Type**: P300, VEP

## Documentation

- **Description**: Exploring motion VEPs for gaze-independent communication
- **DOI**: 10.1088/1741-2560/9/4/045006
- **Associated paper DOI**: 10.1088/1741-2560/11/2/026009
- **License**: CC-BY-NC-ND-4.0
- **Investigators**: Sulamith Schaeff, Matthias Sebastian Treder, Bastian Venthur, Benjamin Blankertz
- **Senior author**: Benjamin Blankertz
- **Contact**: benjamin.blankertz@tu-berlin.de
- **Institution**: Berlin Institute of Technology
- **Department**: Neurotechnology Group
- **Country**: Germany
- **Repository**: BNCI Horizon
- **Publication year**: 2012
- **Funding**: DFG grant; grant nos s; BMBF grant; grant no MU MU
- **Ethics approval**: Declaration of Helsinki
- **Keywords**: motion visually evoked potentials, mVEP, BCI, speller, gaze-independent, covert attention, P300, N200

## References

Treder, M. S., Purwins, H., Miklody, D., Sturm, I., & Blankertz, B. (2012). Decoding auditory attention to instruments in polyphonic music using single-trial EEG classification. Journal of Neural Engineering, 11(2), 026009. https://doi.org/10.1088/1741-2560/11/2/026009

Notes

.. versionadded:: 1.2.0

See Also

BNCI2015_008 : Center Speller P300 dataset (gaze-independent) BNCI2015_009 : AMUSE auditory spatial P300 dataset BNCI2015_010 : RSVP visual speller (gaze-independent visual paradigm)
Appelhoff, S., Sanderson, M., Brooks, T., Vliet, M., Quentin, R., Holdgraf, C., Chaumon, M., Mikulan, E., Tavabi, K., Hochenberger, R., Welke, D., Brunner, C., Rockhill, A., Larson, E., Gramfort, A. and Jas, M. (2019). MNE-BIDS: Organizing electrophysiological data into the BIDS format and facilitating their analysis. Journal of Open Source Software 4: (1896). https://doi.org/10.21105/joss.01896

Pernet, C. R., Appelhoff, S., Gorgolewski, K. J., Flandin, G., Phillips, C., Delorme, A., Oostenveld, R. (2019). EEG-BIDS, an extension to the brain imaging data structure for electroencephalography. Scientific Data, 6, 103. https://doi.org/10.1038/s41597-019-0104-8

---
Generated by MOABB 1.5.0 (Mother of All BCI Benchmarks)
https://github.com/NeuroTechX/moabb
