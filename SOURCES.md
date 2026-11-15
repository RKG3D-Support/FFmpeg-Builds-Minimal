# Corresponding source — Grapheo 3D FFmpeg build

This repository is a fork of [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds) (MIT License),
reduced to a minimal LGPL build of FFmpeg for Windows x64, built with GitHub Actions
(workflow "Build FFmpeg (Grapheo 3D minimal LGPL)", variant `lgpl 8.1`).

The exact build recipe is in `scripts.d/` and `variants/`. Every library below is pinned to a fixed
commit by its script. FFmpeg itself is taken from the `release/8.1` branch at build time: the exact
FFmpeg version and commit of each release are written in that release's description.

| Component | Licence | Source | Pinned revision |
|---|---|---|---|
| FFmpeg (branch release/8.1, `--enable-version3`) | LGPL-3.0-or-later | https://github.com/FFmpeg/FFmpeg | see release notes |
| LAME (libmp3lame) | LGPL-2.0-or-later | https://svn.code.sf.net/p/lame/svn/trunk/lame | svn r6531 |
| GNU libiconv | LGPL-2.1-or-later | https://git.savannah.gnu.org/git/libiconv.git | 9d19c66d0a1768cffcf497b2db70bf4018b578d7 |
| gnulib (used by libiconv) | LGPL-2.1-or-later / GPL (build-time files) | https://git.savannah.gnu.org/git/gnulib.git | b84e952538c2bad5940715a55bcb054907a60541 |
| zlib | zlib | https://github.com/madler/zlib | f9dd6009be3ed32415edf1e89d1bc38380ecb95d |
| libvpx | BSD-3-Clause | https://chromium.googlesource.com/webm/libvpx | b1f431c1ebdd386d227599c712d0a7b68fcfc8d0 |
| Opus (libopus) | BSD-3-Clause | https://github.com/xiph/opus | 788cc89ce4f2c42025d8c70ec1b4457dc89cd50f |
| dav1d | BSD-2-Clause | https://code.videolan.org/videolan/dav1d | aa4504729c82420cde1791101722788d6ed7cbf6 |
| AMD AMF headers | MIT | https://github.com/GPUOpen-LibrariesAndSDKs/AMF | d0b3e6dd544a5f207bb6a12a1ecb98532491176a |
| nv-codec-headers | MIT | https://github.com/FFmpeg/nv-codec-headers | 33a9ede8d9914299d9262539c576a15bd0a19621 |
| Intel libvpl | MIT | https://github.com/intel/libvpl | 778a66d6c6537f08eabb91955dbbf1bce3812894 |
| mingw-w64 (CRT, winpthreads) | ZPL-2.1 / MIT / public domain | https://git.code.sf.net/p/mingw-w64/mingw-w64.git | 01f73779bff47496dfee1598ebc267b0a47b2fce |
| mingw-std-threads | BSD-2-Clause | https://github.com/meganz/mingw-std-threads | c931bac289dd431f1dd30fc4a5d1a7be36668073 |

The GCC cross-compiler used (built with crosstool-NG, see `images/base-win64/`) contributes its runtime
libraries (libgcc, libstdc++) under the GCC Runtime Library Exception.

Replacing the binaries: Grapheo 3D lets you replace `ffmpeg.exe` and `ffprobe.exe` with your own
interface-compatible build (see the "Replacing LibVLC and FFmpeg" section of its legal notices page).
