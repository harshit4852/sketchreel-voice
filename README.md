# Sketchreel voice model

The free, open voice model behind Sketchreel's Claude voiceover: **Kokoro v1.0** (ONNX), with its voices.
Licensed under Apache 2.0 (see `LICENSE` and `NOTICE`), so it's fine for monetised videos.

Sketchreel's voice script clones this repository and rebuilds the model by itself. To rebuild it by hand:

```sh
git clone --depth 1 https://github.com/harshit4852/sketchreel-voice.git
cd sketchreel-voice
cat kokoro-v1.0.onnx.part* > kokoro-v1.0.onnx
sha256sum -c SHA256SUMS
```

| File | Bytes | SHA-256 |
|---|---|---|
| `kokoro-v1.0.onnx` (rebuilt from 7 parts) | 325,532,387 | `7d5df8ecf7d4b1878015a32686053fd0eebe2bc377234608764cc0ef3636a6c5` |
| `voices-v1.0.bin` | 28,214,398 | `bca610b8308e8d99f32e6fe4197e7ec01679264efed0cac9140fe9c29f1fbf7d` |

These are the unchanged files from the kokoro-onnx project's `model-files-v1.0` release.

## Pronunciation data

Sketchreel turns Hindi voiceover lines into sounds with its own pronunciation engine (no espeak). Its two data files live here too,
and the voice script fetches them with the model:

| File | Bytes | SHA-256 |
|---|---|---|
| `g2p-en.json.xz` (British English dictionary, from misaki, Apache 2.0) | 1,197,484 | `7c902818a53d578a191fe34fa3515df4caadeeaf9f38c5e0265ed8963c550f7a` |
| `g2p-lts.json.xz` (Sketchreel's English letter-to-sound table) | 194,748 | `967e18ef7d025ccf5f6ba1fd44ba06ec0114f7b9a5fcbcac918630e18e2dc71d` |

