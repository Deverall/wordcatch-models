# WordCatch models

On-device models downloaded by the WordCatch app (iPhone and iPad), hosted here so the
app can fetch them. Nothing is uploaded from the app; these are only downloaded.

## Phonemes (release `phonemes-v1`)

`Phonemes.mlmodelc.zip` — a phoneme recognizer that writes out the sounds in a short
recording (for example g · ɑ · i), so WordCatch can suggest how someone says a word.

- Based on [vitouphy/wav2vec2-xls-r-300m-timit-phoneme](https://huggingface.co/vitouphy/wav2vec2-xls-r-300m-timit-phoneme)
  (Apache License 2.0), which fine-tunes Meta's wav2vec 2.0 XLS-R 300M on TIMIT phonemes.
- Changes: converted to Core ML (ML Program, iOS 18), weights quantized to 8-bit, output
  wrapped in log-softmax. Input: 16 kHz mono audio, normalized to zero mean and unit
  variance, 0.5–8 seconds (`audio`, shape 1 × samples). Output: `logprobs`, 1 × frames × 42.
- Vocabulary (index → symbol): 0 `|`, 1 ɑ, 2 æ, 3 ə, 4 aʊ, 5 aɪ, 6 b, 7 ʧ, 8 d, 9 ð, 10 ɾ,
  11 ɛ, 12 ɝ, 13 eɪ, 14 f, 15 g, 16 space, 17 h, 18 ɪ, 19 i, 20 ʤ, 21 k, 22 l, 23 m, 24 n,
  25 ŋ, 26 oʊ, 27 ɔɪ, 28 p, 29 ɹ, 30 s, 31 ʃ, 32 t, 33 θ, 34 ʊ, 35 u, 36 v, 37 w, 38 j,
  39 z, 40 [UNK], 41 [PAD] (CTC blank).

Licensed under the Apache License 2.0 (see LICENSE), like the original model.
Made for WordCatch by ColeCustomWorks — https://wordcatch.app
