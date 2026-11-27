es-v1: Spanish language pack for Inconnu

All files are unchanged copies of the published originals; SHA-256 values are in ../README.md.

1. Moonshine Streaming Small, Spanish (speech recogniser)
   - Copyright (c) 2025 Useful Sensors, Inc. (dba Moonshine AI). MIT License: LICENSE-MIT-Moonshine.txt.
   - Origin: https://download.moonshine.ai/model/small-streaming-es/quantized_26_08_24/ (8 files).
   - Changes: none.

2. Montreal Forced Aligner Spanish models v3.3.0 (aligner)
   - "Spanish MFA acoustic model v3.3.0" and "Spanish (Spain) MFA dictionary v3.3.0", by Michael McAuliffe and
     Morgan Sonderegger (Montreal Corpus Tools), https://mfa-models.readthedocs.io/.
   - Licence: Creative Commons Attribution 4.0 International (CC BY 4.0), LICENSE-CC-BY-4.0.txt,
     https://creativecommons.org/licenses/by/4.0/.
   - Origin: https://github.com/MontrealCorpusTools/mfa-models/releases/tag/acoustic-spanish_mfa-v3.3.0 and
     https://github.com/MontrealCorpusTools/mfa-models/releases/tag/dictionary-spanish_spain_mfa-v3.3.0
   - Changes: none. (If Inconnu later repacks them for the phone, the changed form gets its own file and is marked
     here as modified.)

3. Piper voice es_ES-davefx-medium (voice)
   - From rhasspy/piper-voices (repository tagged MIT), es/es_ES/davefx/medium. Model card (included): dataset
     licence CC0; fine-tuned from the rdh base model (nl_BE, CC0).
   - Origin: https://huggingface.co/rhasspy/piper-voices/tree/main/es/es_ES/davefx/medium
   - Changes: none. Inconnu does not use the Piper engine or eSpeak; it runs the ONNX file with sherpa-onnx.
