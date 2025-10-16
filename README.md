## About
This project presents a reversible and secure method to embed hidden messages inside grayscale images while preserving their visual quality.
It extends the concept of wavelet-based color-to-gray conversion by introducing a key-dependent pixel-domain embedding strategy that allows secure message storage and recovery without perceptible distortion.

## Objectives
- Convert color images to textured grayscale using Discrete Wavelet Transform (DWT).
- Embed secret messages securely within the grayscale image using key-based pixel selection.
- Ensure reversible color and message recovery from the grayscale carrier.
- Evaluate reconstruction fidelity using PSNR and SSIM metrics.

## Methodology
### Color-to-Gray Conversion (Wavelet Domain)
- Convert RGB image to YCbCr color space.
- Apply single-level DWT on the luminance (Y) channel → obtain LL, LH, HL, HH subbands.
- Embed chrominance components (Cb, Cr) into high-frequency subbands (LH, HL).
- Perform Inverse DWT to generate a textured grayscale image preserving hidden color information.

### Secure Message Embedding (Pixel Domain)
- Generate a pseudorandom pixel sequence using a secret key.
- Embed binary message bits into the Least Significant Bits (LSBs) of the selected pixels.
- This key-dependent embedding ensures security and tamper resistance.

### Message & Color Recovery
- Use the same secret key to locate and extract embedded bits → reconstruct the message.
- Apply inverse DWT to recover chrominance data and reconstruct the original color image.

### Evaluation Metrics
- Peak Signal-to-Noise Ratio (PSNR): Measures image fidelity.
- Structural Similarity Index (SSIM): Evaluates perceptual similarity.

## Key Features
- Reversible color recovery from grayscale
- Secure key-based message embedding
- Robust to rounding and quantization errors
- Objective evaluation using PSNR & SSIM

## Original Image
![Balloon](https://github.com/user-attachments/assets/93ef284a-ad10-48da-a0c2-790fb52cd7ea)

## Textured Gray Image
<img width="603" height="386" alt="textured_gray" src="https://github.com/user-attachments/assets/979210db-d430-493f-8e26-a8d1aa5d6f42" />

## Recovered Image
<img width="595" height="385" alt="recovered" src="https://github.com/user-attachments/assets/ae705a1f-8a81-4ead-8f90-33d3161afd44" />

## Mesage retrieved via a secure key
<img width="541" height="48" alt="correct" src="https://github.com/user-attachments/assets/4f872b87-1301-44a4-bdaf-bebd4ac879f1" />


