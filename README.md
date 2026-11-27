# inconnu-models

Model files used by the Inconnu reading app. The app downloads them only when a reader chooses an optional feature, checks each file against a pinned SHA-256, and then runs them on the phone.

The files are published as **release assets**, not in git. Each release has a matching folder here with its licence and attribution.

## natural-v1: the "Natural voice"

Release: [natural-v1](https://github.com/perwendelboe-lab/inconnu-models/releases/tag/natural-v1)

| File | Bytes | SHA-256 |
|---|---|---|
| `model.onnx` | 70,868,610 | `520f750b6c8ebe4a51426058dde07cab389bec232a2d1a3f8ad3f05167fa7f07` |
| `tokens.txt` | 954 | `bcb4a50830e9402112fe8cb57d53ae8523908868a5015f2040dde5f5fd231697` |

- **Model:** a VITS English voice (LJ Speech, "medium") trained with the [k2-fsa icefall](https://github.com/k2-fsa/icefall) VITS recipe and exported to ONNX by the k2-fsa project. Training checkpoint: [csukuangfj/icefall-tts-ljspeech-vits-medium-2024-03-12](https://huggingface.co/csukuangfj/icefall-tts-ljspeech-vits-medium-2024-03-12).
- **Source of these files:** extracted unchanged from `vits-icefall-en_US-ljspeech-medium.tar.bz2` in the [k2-fsa/sherpa-onnx `tts-models` release](https://github.com/k2-fsa/sherpa-onnx/releases/tag/tts-models).
  - **Repackaging:** only `model.onnx` and `tokens.txt` were kept. The archive's `espeak-ng-data` folder (GPL) was left out and is not in this repository. Inconnu does not use eSpeak; it phonemises text itself with CMUdict.
- **Licence:** Apache License 2.0 (k2-fsa icefall / sherpa-onnx). See [natural-v1/LICENSE-Apache-2.0.txt](natural-v1/LICENSE-Apache-2.0.txt).
- **Training data:** [The LJ Speech Dataset](https://keithito.com/LJ-Speech-Dataset/) (Keith Ito and Linda Johnson, 2017), public domain.
- **In the app:** Inconnu's licence page says: "VITS voice trained with the k2-fsa icefall recipe (Apache-2.0) on the LJ Speech dataset (public domain)."

The pronunciation dictionary the app uses with this voice (CMUdict, BSD-2-Clause) is downloaded from its own source at a pinned commit and is not hosted here.

## es-v1: Spanish language pack

Release: [es-v1](https://github.com/perwendelboe-lab/inconnu-models/releases/tag/es-v1). The app downloads these only when a profile reads in Spanish; each part is fetched when it is first needed. See [es-v1/NOTICE.md](es-v1/NOTICE.md).

### Speech recogniser: Moonshine Streaming Small, Spanish (121,800,392 bytes)

| File | Bytes | SHA-256 |
|---|---|---|
| `adapter.ort` | 2,869,296 | `04b54114c8aab534222922640f7ca0882948ff9f6ed76777f6e184e55a8e8b15` |
| `cross_kv.ort` | 5,358,752 | `4bfd0a641d72ccdae22751f86bbb2e25ff70c1fba4f81213f2415a1accff9618` |
| `decoder_kv.ort` | 61,314,512 | `5b77c3d6baf801ef925a5bc54d7eb3db0c35ebbb86f8eaf5390d7f5bb42fef37` |
| `encoder.ort` | 44,358,376 | `a9b8d6d5d9348d0e319cceffdb0196ef622df8e4e9f3fb4797dcd8dfafd50857` |
| `frontend.model.ort` | 26,776 | `69c76287f49db365aa278d4908ec450e69ca1b4bfb7e836159d963d623ee0c13` |
| `frontend.weights.ort` | 7,769,280 | `2f5a0eb5f3004c9447810d74274a352746319a32144e31d95ef410f425b84dda` |
| `streaming_config.json` | 512 | `12d16c7f5ea6734d197b79baf47914ea7e996d6fca8d303a19aca10d0617cecc` |
| `tokenizer.bin` | 102,888 | `5fbb7d4314dcb18e03c5f975609e4a4cd572b22b01d2b2accb1b3e6830696f36` |

- **Source:** `https://download.moonshine.ai/model/small-streaming-es/quantized_26_08_24/`, unchanged. File list and sizes match Moonshine's `core/moonshine-model-file-metadata.generated.cpp` at commit d8d8fa2.
- **Licence:** MIT (Useful Sensors, Inc., dba Moonshine AI). See [es-v1/LICENSE-MIT-Moonshine.txt](es-v1/LICENSE-MIT-Moonshine.txt). Moonshine's licence states that every streaming model is MIT. The non-commercial Spanish *Base* model is **not** used.
- **In the app:** run by Inconnu's own build of Moonshine's streaming code (MIT) on ONNX Runtime (MIT).

### Aligner: Montreal Forced Aligner, Spanish v3.3.0 (96,426,428 bytes)

| File | Bytes | SHA-256 |
|---|---|---|
| `spanish_mfa.zip` | 91,852,283 | `287f0a6a0f0c38380e794ea92e1eb04d5d61a6c24c8cd795b832e00d7939f15f` |
| `spanish_spain_mfa.dict` | 4,574,145 | `68f5bc7e97e756f5b96dd9bdc8d7c70641a6f7357b8d4819c7b45faa96fca5ff` |

- **Source:** [acoustic-spanish_mfa-v3.3.0](https://github.com/MontrealCorpusTools/mfa-models/releases/tag/acoustic-spanish_mfa-v3.3.0) and [dictionary-spanish_spain_mfa-v3.3.0](https://github.com/MontrealCorpusTools/mfa-models/releases/tag/dictionary-spanish_spain_mfa-v3.3.0), unchanged.
- **Licence:** Creative Commons Attribution 4.0 International. See [es-v1/LICENSE-CC-BY-4.0.txt](es-v1/LICENSE-CC-BY-4.0.txt). Attribution: *Spanish MFA acoustic model v3.3.0* and *Spanish (Spain) MFA dictionary v3.3.0*, Michael McAuliffe and Morgan Sonderegger, Montreal Corpus Tools, https://mfa-models.readthedocs.io/.

### Voice: Piper es_ES davefx, medium (63,228,159 bytes)

| File | Bytes | SHA-256 |
|---|---|---|
| `es_ES-davefx-medium.onnx` | 63,221,984 | `d2c9224e122321aac3c33343957fff4d0f465226cb74c66b0f520ca3f8c0dd07` |
| `es_ES-davefx-medium.onnx.json` | 6,175 | `7d82d069eccca0f87963bd23c33166fe1ef6d24a6b231543931bfe692397f256` |

- **Source:** [rhasspy/piper-voices `es/es_ES/davefx/medium`](https://huggingface.co/rhasspy/piper-voices/tree/main/es/es_ES/davefx/medium), unchanged.
- **Licence:** the model card gives the dataset licence as CC0, and the voice is fine-tuned from the CC0 rdh base. The piper-voices repository is tagged MIT. See [es-v1/MODEL_CARD-es_ES-davefx-medium.md](es-v1/MODEL_CARD-es_ES-davefx-medium.md).
- **In the app:** run with sherpa-onnx (Apache-2.0) from Inconnu's own Spanish pronunciation rules. There is no Piper engine and no eSpeak.
