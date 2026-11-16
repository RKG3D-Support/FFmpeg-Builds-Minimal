# Corresponding source — Grapheo 3D FFmpeg build

This repository is a fork of [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds) (MIT License;
the project is now hosted as FFmpeg-Builds/FFmpeg-Builds), reduced to a minimal LGPL build of FFmpeg for
Windows x64 and built with GitHub Actions (workflow "Build FFmpeg (Grapheo 3D minimal LGPL)",
variant `lgpl 8.1`).

The exact build recipe is in `scripts.d/` and `variants/`. Every library below is pinned to a fixed
revision by its script. FFmpeg itself is taken from the `release/8.1` branch at build time: the exact
FFmpeg version and commit of each build are shown on the first line of `ffmpeg -version` and in the
description of the corresponding release.

Revisions below match upstream master as of 2026-11-07 (commit c9fe511). If this fork is updated from
upstream, re-check `scripts.d/` and update this table.

| Component | Licence | Source | Pinned revision |
|---|---|---|---|
| FFmpeg (branch release/8.1, `--enable-version3`) | LGPL-3.0-or-later | https://github.com/FFmpeg/FFmpeg | see release notes |
| LAME (libmp3lame) | LGPL-2.0-or-later | https://svn.code.sf.net/p/lame/svn/trunk/lame | svn r7113 |
| GNU libiconv | LGPL-2.1-or-later | https://git.savannah.gnu.org/git/libiconv.git | b5a1735e02bf43ee6e490fcf9395e8abc8d32432 |
| gnulib (used by libiconv) | LGPL-2.1-or-later / GPL (build-time files) | https://git.savannah.gnu.org/git/gnulib.git | 5df606bbd0ef54a8f150c3303c870b9381a661f0 |
| zlib | zlib | https://github.com/madler/zlib | 9d314c341b2ce16e01ae44e27ec3dd2f32aa58fd |
| libvpx | BSD-3-Clause | https://chromium.googlesource.com/webm/libvpx | 900b2a52b69e9d4ab72eb855c365da1100c50eb1 |
| Opus (libopus) | BSD-3-Clause | https://github.com/xiph/opus | a8b2545eec71e0f53ecead2d583e7b6baa42684d |
| dav1d | BSD-2-Clause | https://code.videolan.org/videolan/dav1d | b8b2d726b4b78a2fb174cb45baff441b5969672c |
| AMD AMF headers | MIT | https://github.com/GPUOpen-LibrariesAndSDKs/AMF | 57ee0cfb0e1a08d9041f77435653794c1b012be0 |
| nv-codec-headers (branch sdk/13.0, used for FFmpeg 8.1) | MIT | https://github.com/FFmpeg/nv-codec-headers | ced4f8eba3ba5dd431932cba17928f0dffdaeb2b |
| Intel libvpl | MIT | https://github.com/intel/libvpl | 674d015bcb294bc39fa276e99a652ea045423e82 |
| mingw-w64 (CRT, winpthreads) | ZPL-2.1 / MIT / public domain | https://git.code.sf.net/p/mingw-w64/mingw-w64.git | 7213d719fe344553aa24fef7cc7dedee4940d594 |
| mingw-std-threads | BSD-2-Clause | https://github.com/meganz/mingw-std-threads | c931bac289dd431f1dd30fc4a5d1a7be36668073 |

The GCC cross-compiler used (built with crosstool-NG, see `images/base-win64/`) contributes its runtime
libraries (libgcc, libstdc++) under the GCC Runtime Library Exception.

Replacing the binaries: Grapheo 3D lets you replace `ffmpeg.exe` and `ffprobe.exe` with your own
interface-compatible build (see the "Replacing LibVLC and FFmpeg" section of its legal notices page).
