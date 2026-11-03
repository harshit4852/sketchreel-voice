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

Sketchreel turns voiceover lines into sounds with its own pronunciation engine (no espeak): Hindi lines and, since app v67, English
ones. Its data files live here too, and the voice script fetches the ones a voiceover's language needs with the model (Hindi and British
voices: the first two; American voices: the last two):

| File | Bytes | SHA-256 |
|---|---|---|
| `g2p-en.json.xz` (British English dictionary, from misaki, Apache 2.0) | 1,197,484 | `7c902818a53d578a191fe34fa3515df4caadeeaf9f38c5e0265ed8963c550f7a` |
| `g2p-lts.json.xz` (Sketchreel's English letter-to-sound table) | 194,748 | `967e18ef7d025ccf5f6ba1fd44ba06ec0114f7b9a5fcbcac918630e18e2dc71d` |
| `g2p-en-us.json.xz` (American English dictionary, from misaki, Apache 2.0) | 1,125,056 | `30efb5767b0eaca99a9c96212fadc48afb87625398cb5f021eb8bf88d4d8a071` |
| `g2p-lts-us.json.xz` (Sketchreel's American English letter-to-sound table) | 193,976 | `33cabab59eea1b8ba4308b9129cecd0f711e3b996fe764e56d00b5a7f38c9d0f` |


## A second copy: the release

The same files, unchanged, are also attached to this repository's release
[`model-files-v1.0`](https://github.com/harshit4852/sketchreel-voice/releases/tag/model-files-v1.0): the model in one piece
(`kokoro-v1.0.onnx`), `voices-v1.0.bin`, the four pronunciation data files and the font below, with `LICENSE`, `NOTICE` and
`SHA256SUMS`. Sketchreel's voice script downloads from there when it can't clone this repository, so every file it needs comes from
this account: it no longer falls back to another project's release.

## Font for the graphics preview

`fonts/caveat-latin-500-normal.woff2` and `fonts/caveat-latin-700-normal.woff2` are the Caveat font (Latin, weights 500 and 700),
the handwriting Sketchreel draws its labels in. The preview script in Sketchreel's Claude file fetches them from here to show
Claude's graphics as they'll look in the video. Caveat is under the SIL Open Font License 1.1 (`fonts/OFL-Caveat.txt`).

| File | Bytes | SHA-256 |
|---|---|---|
| `fonts/caveat-latin-500-normal.woff2` | 50,904 | `edbfb1a768829d4e85127cd327e59faaec9701cb043e96430938f1f66acf009f` |
| `fonts/caveat-latin-700-normal.woff2` | 51,020 | `15f9638095ad5ec9816f93d66805ca1a87e71dc5a76b596bfce1c78d4704c405` |
