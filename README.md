# Intel Unnati - Image Sharpening using knowledge distillation
This project aims to improve the quality of images through deblurring (sharpening) of blurred images through a deep learning process driven by Knowledge Distillation (KD). A teacher deep U-Net model is initially trained and its knowledge is then distilled in a smaller student model performing effective deblurring for deployment in real-time systems. 


To clone this repositary
```
git clone https://github.com/Suj93s/Intel-Unnati
```

## Tools Used
- Pytorch : Deep learning framework used to build and train both teacher and student CNN architectures.
- Torchvision: Used for common image transformation utilities and handling datasets.
- NumPy: For efficient numerical computations and tensor manipulation.
- Pillow (PIL): Image loading, filtering (Gaussian blur), and augmentation.
- scikit-image: Computation of evaluation metrics such as PSNR and SSIM to measure image quality.
- Matplotlib: For visualizing results, including side-by-side comparisons of blurred, predicted, and ground truth images.

## Dataset
We use the GoPro Dataset consisting of paired sharp and blurred images for training our model.
For Downloading the data set
```
https://www.dropbox.com/s/u842yorwmap7xij/GOPRO_Large.zip?dl=1
```

## Outcomes
Designed a two-stage image deblurring system:
A teacher U-Net with residual blocks model trained on synthetically blurred GoPro data.
A student model trained via Knowledge Distillation (KD) to mimic the teacher's behavior.

Obtained high-quality restored images using orders of magnitude fewer parameters in the student model.

Achieved high-quality image restoration while drastically reducing the model size.

Showed that deep learning can reversely correct blur artifacts given enough paired training data.

### Quantitative Results:

Blurred Input: PSNR = 24.98 dB, SSIM = 0.7622

Teacher Model: PSNR = 31.83 dB, SSIM = 0.948

Student Model: PSNR = 31.61 dB, SSIM = 0.9325

The model provides cutting-edge performance with a significant cut in inference time, and it is best suited for real-time use cases like:

- Surveillance systems

- Drone cameras

- Video conferencing tools

- Embedded IoT devices


## Limitations
- Synthetic blur generation using Gaussian filters may not capture the diversity of real-world blur patterns (e.g., motion, defocus).

- The student model, though fast and efficient, can sacrifice subtle structural information in intricate textures.

- Generalization to novel datasets (e.g., real dynamic scenes) is not comprehensively confirmed.

- Although the student model is fast during inference, the two-stage training process (teacher then student) can be time-intensive.

## Future Scopes

- Adaptive Deblurring: Incorporate a blur estimation component that varies the model response based on input image type or amount of blur.

- Real-World Blur Treatment: Extend training to cover a broad variety of real-world types of blur (e.g., defocus, motion, low-light noise) by using mixed or unpaired datasets.

- On-Device Optimization: Compress and quantize the student model even more to be deployable on ultra-low-power devices such as mobile phones, Raspberry Pi, or microcontrollers.

- Self-Supervised Learning: Integrate semi-supervised or self-supervised techniques to decrease reliance on paired datasets, particularly for domain adaptation.

- Benchmarking on Diverse Datasets: Test and optimize the model on other public datasets (e.g., RealBlur, REDS) for enhancing generalization.


## Team FALCONS

- [Sujith S](https://github.com/Suj93s)
- [Daison K Daniel](https://github.com/dais-x)
- [Athira Adiparambil Anil](https://github.com/athira-anil2327)
