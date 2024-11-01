# Melanin and Skin Tone Analysis — Digital Image Processing

A digital image processing study comparing colour space representations for melanin quantification and skin tone classification. Built as part of a DIP course at VIT Chennai.

## The Idea

Standard RGB doesn't separate colour and brightness well — which matters a lot when you're trying to isolate melanin-heavy regions in skin images. This project tests whether switching colour spaces gives you cleaner segmentation, and compares threshold-based vs. clustering-based approaches for region extraction.

## Colour Spaces Compared

| Colour Space | Channels | Effectiveness for Melanin |
|---|---|---|
| RGB | Red, Green, Blue | Baseline — limited separation |
| HSV | Hue, Saturation, Value | Better — saturation channel isolates melanin regions |
| LAB | Lightness, A (green-red), B (blue-yellow) | Best — luminance and chroma decouple cleanly |
| YCbCr | Luma, Cb (blue-difference), Cr (red-difference) | Good — commonly used in video processing |

**Finding:** LAB colour space consistently gave the cleanest melanin isolation. The luminance channel (L) and chroma channels (A, B) separate more usefully than HSV or RGB for this task.

## Segmentation Techniques

**Threshold Segmentation**  
Applies a fixed or Otsu-computed threshold to the target channel. Fast but sensitive to lighting variation.

**K-means Segmentation**  
Clusters pixels into N groups based on colour similarity in the chosen space. More robust to uneven illumination, better results than threshold-based on varied input images.

**Histogram Analysis**  
Used throughout to visualise channel distributions and understand how each colour space spreads melanin-related pixel values.

## Repository Contents

| File | Description |
|---|---|
| `21BCE5148_21BCE1409_21BCE1950_DA3(DIP).pdf` | Final DIP assignment report (DA3) |
| `21BCE1409_21BCE1950_21BCE5148_DA-1(DIP).pdf` | Initial analysis report (DA1) |

## Stack

Python · OpenCV · NumPy · Matplotlib · scikit-learn
