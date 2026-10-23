# EnhancedMobileNetV2

A lightweight CNN for plant disease classification. It extends MobileNetV2 with channel attention and ATTRUS refinement blocks, and is benchmarked against five standard architectures.

## Architecture

- **Backbone:** MobileNetV2, ImageNet weights, two-phase transfer learning: train the new head with the backbone frozen, then fine-tune.
- **Channel attention:** a squeeze-and-excitation block that re-weights feature channels to emphasise informative responses.
- **ATTRUS block:** a residual channel-reweighting block (`x + x * attention(x)`) that sharpens discriminative features without discarding the original signal.

## Dataset

38 classes of healthy and diseased crop leaves: 70,295 training images and 17,572 held-out validation images.

## Results

Evaluated on the 17,572 held-out images.

| Model | Accuracy | F1 | Saved model size |
| --- | --- | --- | --- |
| ResNet50 | 98.82% | 0.988 | 98 MB |
| **EnhancedMobileNetV2 (ours)** | **98.54%** | **0.985** | **39 MB** |
| DenseNet121 | 97.77% | 0.978 | 31 MB |
| MobileNetV1 | 97.66% | 0.977 | 15 MB |
| VGG16 | 96.84% | 0.968 | 60 MB |
| MobileNetV2 | 96.23% | 0.963 | 11 MB |

The attention and ATTRUS additions improve plain MobileNetV2 by 2.3 points. The model comes within 0.3 points of ResNet50 at 40% of its saved size.

Training curves, confusion matrices and ROC curves are in `results/`.

## Stack

Python · TensorFlow / Keras · NumPy · scikit-learn · Matplotlib
