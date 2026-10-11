# 📖 MRI Brain Tumor Detection Program

> An image processing program engineered in Python with vibe coding to evaluate signal intensity anomalies in brain MRI scans, inspired by my interest in understanding early diagnostic imaging.

<a href="https://happyjasondev.github.io/mri-brain-tumor-detection-program/">
<img src="real_mri_result.png" width="75%" alt="Sample Image Demo" />
</a>

## 🔬 Visual Output

**View the sample processing output:** [https://happyjasondev.github.io/mri-brain-tumor-detection-program/](https://happyjasondev.github.io/mri-brain-tumor-detection-program/)

## 📝 Known Limitations & Future Roadmap

* **Sensitivity to High-Intensity Non-Tumor Structures:**  
  * **Current Limitation:** Bright anatomical features (such as skull bones or fat tissue) can sometimes trigger false positives under simple intensity thresholding, as demonstrated in the image.
  * **Planned Improvement:** Implement skull-stripping algorithms (e.g., Brain Extraction Tool / BET) to isolate brain tissue prior to segmentation.

* **Lack of Spatial & Volumetric Context:**  
  * **Current Limitation:** Evaluates 2D slice intensity in isolation without analyzing 3D spatial continuity or texture patterns.
  * **Planned Improvement:** Transition from classical image processing to a Convolutional Neural Network (e.g., U-Net architecture) trained on multi-modal clinical datasets (BRATS).

## 🛠️ Key Features & Technical Architecture

* **Modular Image Processing Pipeline:** Structured reusable functional workflows across `mri_pipeline.py` to isolate signal acquisition, noise mitigation, and feature isolation stages.
* **Signal Denoising & Contrast Optimization:** Applied `scipy.ndimage` and `skimage.filters` to calculate noise variance ($\sigma$), remove high-frequency artifacts, and enhance tissue contrast gradients.
* **Threshold-Based Lesion Segmentation:** Utilized morphological operations (`skimage.morphology`) and connected-component labeling (`skimage.measure`) to isolate hyperintense region clusters representing potential pathological structures.
* **Multi-Stage Computer Vision Visualization:** Built a modular rendering grid using `matplotlib.pyplot` and `PIL` to map raw input DICOM/image arrays through denoising, contrast scaling, and automated lesion boundary annotation.

## 💻 Tech Stack & Dependencies

| Category | Technology / Library |
| :--- | :--- |
| **Language** | Python 3.x |
| **Scientific Computing** | `NumPy`, `SciPy` (`ndimage`) |
| **Computer Vision / Processing** | `skiimage` (`img_as_float`, `morphology`, `filters`, `measure`), `PIL` |
| **Data Visualization** | `Matplotlib` |
| **Image Enhancement** | `mri_pipeline` (`denoise_image`, `enhance_contrast`, `estimate_noise_sigma`) |

## ⚠️ Disclaimer

This software demonstrates algorithmic image processing techniques (isolating high-signal intensity regions) for educational and portfolio demonstration purposes only. It does not constitute a medical diagnosis. Clinical interpretation must be performed by a qualified physician.
