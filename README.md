# EMG_preprocessing_onset_detection

Python workflow for preprocessing EMG recordings, correcting event timing, automatically detecting EMG bursts, and manually validating EMG onset/offset markers.

## Overview

This repository provides a Python pipeline for extracting manually validated EMG onset and offset markers from electrophysiological recordings.

The workflow consists of three main steps:

1. **EMG preprocessing and event correction**
   - Extract EMG channels from the original recording
   - Compute bipolar EMG derivations
   - Apply EMG filtering
   - Correct response-marker timing using behavioral reaction times
   - Segment the EMG signal into stimulus-locked trials

2. **Automatic EMG onset/offset detection**
   - Detect periods of EMG activity using a threshold-based procedure
   - Refine burst onset and offset estimates using the integrated-profile method
   - Add EMG onset (`350`) and offset (`351`) markers to the event structure

3. **Visual inspection and manual correction**
   - Inspect each trial and both EMG channels
   - Visualize the EMG signal together with stimulus, response, onset, and offset markers
   - Manually move, add, or delete EMG onset/offset markers when necessary
   - Save the final manually validated events in both segmented and continuous CSV formats

## EMG toolbox

The EMG processing functions used in this repository are largely based on the **MyOnset** toolbox developed by Laurent Spieser, with additional custom adaptations for the present processing pipeline.

Original MyOnset toolbox:
https://github.com/lspieser/myonset

## Main dependencies

- Python
- MNE-Python
- NumPy
- Pandas
- Matplotlib
- PyQt (for interactive visual inspection)
- MyOnset / custom EMG toolbox

## Output

The main final outputs are:

- `*_segmentedEvts.csv` — event markers expressed within stimulus-locked trials
- `*_continuousEvts.csv` — corresponding event markers expressed relative to the continuous recording

Intermediate preprocessing files may also include corrected trigger arrays (`.npy`) and preprocessed EMG recordings (`.fif`).

> **Warning — protect manual corrections**
>
> Automatic detection should be performed before manual validation. Once EMG onset/offset markers have been manually corrected, the validated event files should not be overwritten by re-running the automatic detection pipeline.

## Tutorial

The Jupyter notebook included in this repository provides a step-by-step explanation of the complete workflow, from EMG preprocessing to automatic onset/offset detection and manual visual validation.

