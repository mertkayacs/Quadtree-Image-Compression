<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/brand/svg/quadtree-compression-logo-on-dark.svg">
    <img src="docs/brand/svg/quadtree-compression-logo-on-light.svg" alt="Quadtree Image Compression" width="260">
  </picture>
</p>

<h1 align="center">Split the image. Merge what looks alike.</h1>

<p align="center">
  Archived university coursework in Java, 2019.<br>
  <b>Square PPM images in. Eight levels of detail out.</b>
</p>

<p align="center">
  <img alt="Status: archived" src="https://img.shields.io/badge/status-archived-2E4A7D?style=flat-square">
  <img alt="Written in 2019" src="https://img.shields.io/badge/written-2019-1E2A38?style=flat-square">
  <img alt="Java" src="https://img.shields.io/badge/Java-JDK-ED8B00?style=flat-square&logo=openjdk&logoColor=white">
  <img alt="Eight output levels" src="https://img.shields.io/badge/output%20levels-8-1E2A38?style=flat-square">
  <a href="https://github.com/mertkayacs/Quadtree-Image-Compression"><img alt="GitHub stars" src="https://img.shields.io/github/stars/mertkayacs/Quadtree-Image-Compression?style=flat-square&logo=github&color=C4A772"></a>
</p>

<p align="center">
  <a href="#quick-start"><img alt="Run it" src="https://img.shields.io/badge/Run%20it-2E4A7D?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjI0IiBoZWlnaHQ9IjI0Ij48ZyBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIj48cGF0aCBkPSJNMTIgMTloOCIvPjxwYXRoIGQ9Im00IDE3IDYtNi02LTYiLz48L2c%2BPC9zdmc%2B&logoColor=white"></a>
  <a href="Main.java"><img alt="Source" src="https://img.shields.io/badge/Source-1E2A38?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjI0IiBoZWlnaHQ9IjI0Ij48ZyBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIj48cGF0aCBkPSJtMTYgMTggNi02LTYtNiIvPjxwYXRoIGQ9Im04IDYtNiA2IDYgNiIvPjwvZz48L3N2Zz4%3D&logoColor=white"></a>
  <a href="https://mertkayacs.com/?utm_source=github&utm_medium=readme&utm_campaign=Quadtree-Image-Compression-repo&utm_content=portfolio-badge"><img alt="Portfolio" src="https://img.shields.io/badge/Portfolio-1E2A38?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjI0IiBoZWlnaHQ9IjI0Ij48ZyBmaWxsPSJub25lIiBzdHJva2U9IiNmZmZmZmYiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIj48Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIvPjxwYXRoIGQ9Ik0xMiAyYTE0LjUgMTQuNSAwIDAgMCAwIDIwYTE0LjUgMTQuNSAwIDAgMCAwLTIwTTIgMTJoMjAiLz48L2c%2BPC9zdmc%2B&logoColor=white"></a>
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/assets/readme/hero-dark.webp">
    <img src="docs/assets/readme/hero-light.webp" alt="The test image on the left and level 4 of the quadtree output on the right, built from visible blocks" width="960">
  </picture>
</p>

Quadtree Image Compression reads a square PPM image, builds a quadtree from its pixels and writes eight versions of the image. Each version merges regions whose colours differ by less than a threshold, from large coarse blocks to the full-detail image. The tree is written by hand with no libraries. It was coursework from 2019.

---

## Why Quadtree Image Compression

A single run produces the whole range from coarse to fine.

|  |  |
|---|---|
| <img src="docs/assets/readme/icons/layers.svg" width="18" height="18" alt=""> **Eight thresholds per run** | [Main.java](Main.java) builds eight trees with thresholds from 14300 down to 0.000001 and writes the results as name-1.ppm to name-8.ppm, coarsest first. |
| <img src="docs/assets/readme/icons/network.svg" width="18" height="18" alt=""> **A hand-written tree** | [QuadTree.java](QuadTree.java) is a tree ADT in which each node has 0 to 4 children. |
| <img src="docs/assets/readme/icons/triangle-alert.svg" width="18" height="18" alt=""> **Limits stated up front** | The original notes say it works best on images with high detail and colour differences, reads only PPM files and reads only square images. |

## A quick tour

<table>
  <tr>
    <td width="50%" valign="top">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="docs/assets/readme/tour/coarse-dark.webp">
        <img src="docs/assets/readme/tour/coarse-light.webp" alt="Test image beside level 2 of the output, made of large blocks">
      </picture>
      <h3>Coarse level</h3>
      Level 2 of 8 merges regions into large blocks. The shapes are drawn for this tour.
    </td>
    <td width="50%" valign="top">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="docs/assets/readme/tour/middle-dark.webp">
        <img src="docs/assets/readme/tour/middle-light.webp" alt="Test image beside level 4 of the output">
      </picture>
      <h3>Middle level</h3>
      Level 4 keeps the circle and the triangle recognisable, with visible block edges.
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="docs/assets/readme/tour/fine-dark.webp">
        <img src="docs/assets/readme/tour/fine-light.webp" alt="Test image beside level 6 of the output">
      </picture>
      <h3>Fine level</h3>
      Level 6 is close to the input, with small blocks left along curved edges.
    </td>
    <td width="50%" valign="top">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="docs/assets/readme/tour/split-dark.webp">
        <img src="docs/assets/readme/tour/split-light.webp" alt="Code card showing the error calculation and the four-way split in Main.java">
      </picture>
      <h3>Splitting rule</h3>
      A region is averaged, its error is measured, and it splits into four children when the error is above the threshold.
    </td>
  </tr>
</table>

<p align="center"><sub>Each image pair shows the test image on the left and one output level on the right. The test image was drawn for this tour. The code card shows Main.java as it is in the repository.</sub></p>

## Features

**Input and output**

- Reads square PPM images in the ASCII P3 format.
- Writes eight PPM files per run.

**Code**

- Main.java reads the image, builds the trees and writes the files.
- QuadTree.java, Position.java and Colour.java hold the tree and the colour values.

## Quick start

```sh
javac Colour.java Position.java QuadTree.java Main.java
java Main -i input.ppm -o out
```

The flags can come in either order. The run writes `out-1.ppm` to `out-8.ppm`. To make a P3 file from another image with ImageMagick:

```sh
convert photo.jpg -resize 512x512! -compress none input.ppm
```

### Requirements

- A Java JDK. The repository does not pin a version.
- ImageMagick, only to convert images to PPM.

## FAQ

<details>
<summary><b>Which images work?</b></summary>

Square PPM files in the ASCII P3 format. Other sizes and formats are not supported.
</details>

<details>
<summary><b>What do the eight outputs mean?</b></summary>

They use eight thresholds from coarse to fine. The first merges the most regions and the last keeps every pixel.
</details>

<details>
<summary><b>Do the outputs take less space?</b></summary>

No. The outputs are plain PPM files again, so they are about the same size as the input. The program shows what each quadtree approximation looks like and does not write a compact file.
</details>

If Quadtree Image Compression is useful to you, a ⭐ helps other people find it.

Photos behind the screenshots are credited in [docs/assets/readme/CREDITS.md](docs/assets/readme/CREDITS.md).

[![views](https://hits.sh/github.com/mertkayacs/Quadtree-Image-Compression.svg?view=today-total&style=flat-square&label=views&color=2E4A7D&labelColor=1E2A38)](https://github.com/mertkayacs/Quadtree-Image-Compression)
