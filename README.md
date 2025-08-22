This repository implements EnhancedMobileNetV2, a lightweight CNN that augments MobileNetV2 with Channel Attention and an ATTRUS module to improve accuracy while keeping the parameter count and compute cost low. Baseline MobileNetV1/V2, ResNet50, DenseNet121, and VGG16 were trained for comparison.

Architecture (High level)

Backbone: MobileNetV2

Enhancements:

Channel Attention: re-weights feature channels to emphasize informative responses.

ATTRUS module: lightweight refinement block to suppress redundant features and enhance discriminative ones.

Goal: better accuracy–vs–compute trade-off than plain MobileNetV2.