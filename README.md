# EMG_preprocessing_onset_detection
Python workflow to extract EMG onsets/offsets from BDF files: align markers, auto-detect activity, visualize, and manually correct.

**Pipeline**

A Python pipeline for processing raw BDF recordings to extract manually validated EMG onsets/offsets. This workflow includes:

- Response-marker timing correction (alignment with EMG data)
- Automatic EMG onset/offset detection (customizable thresholds)
- Interactive visualization (signal inspection, overlay with markers)
- Manual correction tools (GUI-based validation and fine-tuning)
- Structured output (validated onsets saved in CSV/JSON for analysis)

Built with MNE-Python, NumPy, and Matplotlib for reproducible EMG research.

