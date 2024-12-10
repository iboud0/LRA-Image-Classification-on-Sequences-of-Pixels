---

# LRA Image Classification on Sequences of Pixels

## Overview

This repository showcases the implementation and benchmarking of various machine learning models for **image classification** on the **CIFAR-10 dataset**. The focus of this project is inspired by the **Long Range Arena (LRA)** benchmark, where images are processed as sequences of pixels rather than as grids.

The primary goal is to evaluate how well sequence-processing models can handle image-based tasks, and to explore their potential advantages and limitations compared to traditional image-processing architectures.

---

## Motivation

Traditional image classification models rely on convolutional neural networks (CNNs), which exploit the spatial structure of images. In this project, we explore **sequence-based approaches**:
- Treating each pixel as part of a sequence.
- Evaluating the capability of sequence models to handle image data.

The **CIFAR-10 dataset**:
- **60,000 images**, each of size 32x32 pixels with 3 color channels (RGB).
- Divided into **10 classes**, with 6,000 images per class.

This task aligns with the LRA benchmark's objective of testing models on long-range dependency tasks.

---

## Included Models

The following sequence-based models were benchmarked and some were implemented from scratch:

1. **TrellisNet**:
   - Sequence modeling architecture combining features from recurrent and convolutional networks.
   - Key Features:
     - Weight tying across time and layers.
     - Uses temporal convolutions for hierarchical feature learning.
   - Performance:
     - **Paper Accuracy**: 73.42%
     - **Our Work**: 37%

2. **LipschitzRNN**:
   - Enforces Lipschitz constraints for stability in training.
   - Performance:
     - **Paper Accuracy**: 64.2%
     - **Our Work**: 40.5%

3. **Pixel Transformer (PiT)**:
   - Treats each pixel as a token, avoiding locality inductive biases.
   - Architecture:
     - Linear projection of RGB values.
     - Transformer Encoder with Multihead Self-Attention.
   - Performance:
     - **Paper Accuracy**: 85.1% (on CIFAR-100)
     - **Our Work**: 42.16%

4. **Nyströmformer**:
   - Transformer variant that approximates self-attention using the Nyström method.
   - Performance:
     - **Paper Accuracy**: 41.58%
     - **Our Work**: 23.09% (15.05% in individual implementation)

5. **FNet**:
   - Replaces self-attention with Fourier Transform for faster token mixing.
   - Performance:
     - **Paper Accuracy**: Not Available
     - **Our Work**: 46.02%

---

## Repository Structure

Here is an overview of the repository:
Each model directory contains:
- **Implementation scripts**: For training and evaluation.
- **Preprocessing details**: Steps for preparing the CIFAR-10 dataset.
- **Guidelines**: Specific instructions to reproduce results.

---

## How to Use

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/iboud/LRA-Image-Classification-on-Sequences-of-Pixels.git
   cd LRA-Image-Classification-on-Sequences-of-Pixels
   ```

Note: No required dependencies:

### Running Models
Each model folder contains details explaining:
- Dataset preparation.
- Training and evaluation steps.
- Hyperparameter configurations.

---

## Results and Benchmarking

The following table summarizes the experimental results for each model:

| Model          | Paper Accuracy | Our Accuracy |
|----------------|----------------|--------------|
| TrellisNet     | 73.42%         | 37%          |
| LipschitzRNN   | 64.2%          | 40.5%        |
| PiT            | 85.1% (C100)  | 42.16%       |
| Nyströmformer  | 41.58%         | 23.09%       |
| FNet           | NA             | 46.02%       |

---

## Challenges and Limitations

1. **Resource Constraints**:
   - Limited GPU memory restricted model size and batch processing.
   - High computational demands, especially for models like PiT and Nyströmformer.

2. **Accuracy Gaps**:
   - Some models showed significant differences from reported paper accuracies, likely due to hardware and training duration limitations.

3. **Dataset Representation**:
   - Processing CIFAR-10 as pixel sequences increases sequence lengths, adding complexity for transformer-based models.

---

## Learnings and Takeaways

- Sequence models can handle image classification but face challenges with long sequence lengths (e.g., **PiT**, **Nyströmformer**).
- Trade-offs exist between computational efficiency and accuracy for different architectures.
- Fine-tuning hyperparameters and leveraging larger datasets could further improve results.

---

## References

1. [TrellisNet Paper](https://arxiv.org/pdf/1810.06682v2)
2. [LipschitzRNN Paper](https://arxiv.org/pdf/2006.12070v3)
3. [PiT Paper](https://arxiv.org/abs/2406.09415)
4. [Nyströmformer Paper](https://arxiv.org/pdf/2102.03902)
5. [FNet Paper](https://arxiv.org/pdf/2105.03824)
6. [LRA Benchmark Paper](https://arxiv.org/abs/2011.04006)

---

## Contributors

This project was carried out by:
- **Imane Rahali**
- **Amine Idrissi**
- **Ilyas Boudhaine**

Supervised by:
- **Hamza Alami**
- **Issam Ait Yahia**

---
