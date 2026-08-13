# Malayalam ASR Benchmark

Benchmarking two Malayalam automatic speech recognition models, ai4bharat/indic conformer 600m multilingual and thennal/whisper small ml imasc, on the OpenSLR63 Malayalam speech corpus.

This notebook was built for the AfricomPLing Summer School 2026 project submission.

## What this does

The notebook runs both models over a folder of Malayalam audio files, compares each model's output against reference transcriptions, and reports:

- Word Error Rate (WER) and Character Error Rate (CER) for each model
- Unicode normalised WER, which removes punctuation and joiner characters (ZWJ and ZWNJ) so the comparison reflects genuine transcription accuracy rather than encoding differences
- A character level deletion analysis, showing which Malayalam characters each model most often drops
- Comparison charts, including WER by model, a WER versus CER correlation plot, a per file error density heatmap, and a normalisation impact chart

## Dataset

OpenSLR63, a Malayalam sentence reading speech corpus (He et al., 2020). 2113 audio files were used, totalling 182 minutes and 5 seconds.

## Models evaluated

- **ai4bharat/indic conformer 600m multilingual**, an ONNX based conformer model from AI4Bharat's IndicConformer family, run in CTC mode for Malayalam. Available at https://huggingface.co/ai4bharat/indic-conformer-600m-multilingual
- **thennal/whisper small ml imasc**, a Whisper Small model fine tuned on the IMaSC Malayalam dataset. Available at https://huggingface.co/thennal/whisper-small-ml-imasc

## How to run

1. Open the notebook in Google Colab.
2. Mount Google Drive and place audio files in an `audio_files/` folder, with a matching `transcriptions.csv` containing `id` and `transcription` columns.
3. Run the setup cells to install dependencies (`transformers`, `torch`, `torchaudio`, `librosa`, `jiwer`, `huggingface_hub`, `onnxruntime`, `tqdm`).
4. Log in with a Hugging Face access token when prompted, since the AI4Bharat model is gated.
5. Run the evaluation pipeline, then the analysis and visualisation cells.

## Results summary

| Model | Average WER | Average CER | Normalised WER |
|---|---|---|---|
| AI4Bharat Indic Conformer 600M | 0.2452 | 0.0403 | 0.2829 |
| Whisper Small (IMaSC) | 0.4000 | 0.0814 | 0.4350 |

AI4Bharat Indic Conformer achieved the lower error rate of the two models on this corpus. Both models most frequently dropped the virama sign and Unicode joiner characters, reflecting the difficulty of Malayalam's conjunct consonant orthography for automatic speech recognition.

The full analysis and discussion are written up in the accompanying project report.

## Author

Rahul Krishna H S
GitHub: [rahulkrishnahs](https://github.com/rahulkrishnahs)
Department of Linguistics, University of Kerala

## Licence

Released under the MIT Licence. See LICENSE.txt for details.
