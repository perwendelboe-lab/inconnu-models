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
