<p align="center">
  This is a fork of <a href="https://github.com/ONdraid/reve/tree/main">reve by ONdraid<br/><br/>
  <img src="reve-cli/assets/logo.png" height=120>
</p>

## <div align="center"><b><a href="https://github.com/xinntao/Real-ESRGAN">Real-ESRGAN</a> <a href="https://github.com/ONdraid/reve">Video Enhance</a></b></div>

<div align="center">

[![download](https://img.shields.io/github/downloads/ONdraid/reve/total)](https://github.com/ONdraid/reve/releases)
[![support](https://img.shields.io/badge/Support-Windows%20x64-blue?logo=Windows)](https://support.microsoft.com/en-us/windows/32-bit-and-64-bit-windows-frequently-asked-questions-c6ca9541-8dce-4d48-0415-94a3faa2e13d)
[![license](https://img.shields.io/github/license/ONdraid/reve.svg)](https://github.com/ONdraid/reve/blob/main/LICENSE)

</div>

<div align="justify">

REVE (Real-ESRGAN Video Enhance) is a small, fast application written in Rust that is used for upscaling animated video content. It utilizes [Real-ESRGAN-ncnn-vulkan](https://github.com/xinntao/Real-ESRGAN-ncnn-vulkan), [FFmpeg](https://ffmpeg.org/about.html) and [MediaInfo](https://mediaarea.net/en/MediaInfo) under the hood. REVE employs a segment-based approach to video upscaling, allowing it to simultaneously upscale and encode videos. This results in a notable enhancement in performance and enables the feature of resumability.

</div>

---

### 📖 Real-ESRGAN: Training Real-World Blind Super-Resolution with Pure Synthetic Data

> [[Paper](https://arxiv.org/abs/2107.10833)] &emsp; [[YouTube Video](https://www.youtube.com/watch?v=fxHWoDSSvSc)] &emsp; [[B站讲解](https://www.bilibili.com/video/BV1H34y1m7sS/)] &emsp; [[Poster](https://xinntao.github.io/projects/RealESRGAN_src/RealESRGAN_poster.pdf)] &emsp; [[PPT slides](https://docs.google.com/presentation/d/1QtW6Iy8rm8rGLsJ0Ldti6kP-7Qyzy6XL/edit?usp=sharing&ouid=109799856763657548160&rtpof=true&sd=true)]<br>
> [Xintao Wang](https://xinntao.github.io/), Liangbin Xie, [Chao Dong](https://scholar.google.com.hk/citations?user=OSDCB0UAAAAJ), [Ying Shan](https://scholar.google.com/citations?user=4oXBp9UAAAAJ&hl=en) <br>
> [Tencent ARC Lab](https://arc.tencent.com/en/ai-demos/imgRestore); Shenzhen Institutes of Advanced Technology, Chinese Academy of Sciences

## ⚡ Quick Usage

### Portable executable file (REVE)

You can download [Windows](https://github.com/ONdraid/reve/releases/latest/download/reve-ncnn-vulkan-windows.zip) **executable file for Intel/AMD/Nvidia GPU**.

This executable file is **portable** and includes all the binaries and models required. No CUDA or PyTorch environment is needed.<br>

You can simply run the following command:

```bash
./reve.exe -i onepiece_demo.mp4 -s 2 output.mp4
```

Currently only provided model:
1. [realesr-animevideov3 (animation video)](https://github.com/xinntao/Real-ESRGAN/blob/master/docs/anime_video_model.md)

#### Usage of portable executable file

```console
USAGE:
    reve.exe [OPTIONS] --inputpath <INPUTPATH> --scale <SCALE> <OUTPUTPATH>

ARGS:
    <OUTPUTPATH>    output video path (mp4/mkv)

OPTIONS:
    -c, --crf <CRF>                    video constant rate factor (crf: 51-0) [default: 15]
    -h, --help                         Print help information
    -i, --inputpath <INPUTPATH>        input video path (mp4/mkv)
    -p, --preset <PRESET>              video encoding preset [default: slow]
    -P, --segmentsize <SEGMENTSIZE>    segment size (in frames) [default: 1000]
    -s, --scale <SCALE>                upscale ratio (2, 3, 4)
    -x, --x265params <X265PARAMS>      x265 encoding parameters [default:
                                       psy-rd=2:aq-strength=1:deblock=0,0:bframes=8]
```

