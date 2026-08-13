# Release Notes

## v1.0.0, August 2026

Initial release, prepared for the AfricomPLing Summer School 2026 project submission.

### Added

- Notebook (`malayalam_asr_benchmark.ipynb`) benchmarking ai4bharat/indic conformer 600m multilingual against thennal/whisper small ml imasc on the OpenSLR63 Malayalam speech corpus (2113 files, 182 minutes and 5 seconds of audio).
- WER and CER computation using the jiwer library, with an additional Unicode normalisation step to remove punctuation and joiner characters before rescoring.
- Character level deletion analysis identifying which Malayalam characters each model most frequently drops.
- Visualisations: average WER by model, combined WER and CER summary, WER versus CER correlation, per file error density heatmap, top character loss chart, and normalisation impact chart.
- Results export to CSV and saved chart images for project documentation.

### Results

AI4Bharat Indic Conformer 600M achieved a normalised WER of 0.2829, against 0.4350 for Whisper Small (IMaSC), making it the stronger performing model on this corpus.

### Author

Rahul Krishna H S (GitHub: rahulkrishnahs)
