# iqran-setoran-model

File model pengecek bacaan untuk fitur **Setoran Hafalan** di aplikasi iQran.
Model dijalankan langsung di HP pengguna (offline) dengan whisper.cpp; rekaman tidak dikirim ke server.

## File (Release `v1`)

| File | Ukuran | SHA-256 |
|---|---|---|
| `ggml-base-ar-quran-q5_0.bin` | 55.295.433 byte | `fca5a052a94718a4fed09e52b4a88b4a434987e6fb0d5f08965550dd8fc55db9` |

## Asal model

- **Sumber:** [`tarteel-ai/whisper-base-ar-quran`](https://huggingface.co/tarteel-ai/whisper-base-ar-quran) oleh Tarteel AI — lisensi Apache-2.0.
- **Model dasar:** [`openai/whisper-base`](https://huggingface.co/openai/whisper-base) oleh OpenAI — lisensi MIT.

## Perubahan yang dilakukan

1. Dikonversi dari format Hugging Face (`pytorch_model.bin`) ke format ggml memakai
   `whisper.cpp/models/convert-h5-to-ggml.py` (whisper.cpp commit `aba02de`), dengan satu perbaikan:
   `n_text_ctx` diambil dari `max_target_positions` (448), bukan `max_length`.
2. Dikuantisasi ke `q5_0` dengan `whisper-quantize`.

Bobot tidak dilatih ulang atau diubah selain konversi format dan kuantisasi di atas.

## Lisensi

Didistribusikan di bawah Apache License 2.0 — lihat [LICENSE](LICENSE) dan [NOTICE](NOTICE).
