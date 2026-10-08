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
