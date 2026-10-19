# ughyeah-whisper-vulkan

Windows x64 builds of [whisper.cpp](https://github.com/ggml-org/whisper.cpp) with the Vulkan backend, used by UghYeah
as an optional GPU speed-up for local transcription (any NVIDIA, AMD or Intel graphics driver with Vulkan).

Nothing here is modified: the workflow checks out an upstream tag of whisper.cpp, builds it and attaches the zip to a
release named `vulkan-<tag>`. whisper.cpp is MIT licensed; its license is included in the zip.

## Publishing a build

1. Open **Actions → Build whisper.cpp (Vulkan, Windows) → Run workflow**.
2. Keep `whisper_ref` equal to `ENGINE_TAG` in UghYeah's `src-tauri/src/local_whisper.rs`.
3. When it finishes, the release `vulkan-<tag>` holds `whisper-bin-vulkan-x64.zip`. The app finds it by that name and
   checks the SHA-256 GitHub records for the file.
