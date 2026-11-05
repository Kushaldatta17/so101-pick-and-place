# Configuration Files

This folder contains the configuration files used for the SO101 ACT pick-and-place training experiment.

## Files

### `config.json`

Contains the ACT policy configuration:

- Policy type: ACT
- Observation state: 6 dimensions
- Visual input: 3 × 480 × 640
- Action output: 6 dimensions
- Vision backbone: ResNet-18
- Model dimension: 512
- Attention heads: 8
- Encoder layers: 4
- Decoder layers: 1
- Action chunk size: 100
- Observation steps: 1
- VAE enabled

### `train_config.json`

Contains the complete training configuration:

- Dataset: `kushaldatta96/so101-pick-place-combined`
- Training steps: 10,000
- Batch size: 32
- Optimizer: AdamW
- Learning rate: 0.00001
- Weight decay: 0.0001
- Gradient clipping norm: 10
- Random seed: 1000
- Device: CUDA
- Checkpoint saving enabled
- Checkpoint interval: 1,000 steps

## Experiment

These configurations document the ACT training experiment that produced the 10,000-step checkpoint.

**Important:** The model weights are not included in this GitHub repository. The referenced Hugging Face model repository is private.

The configuration files describe the experiment settings; they do not independently guarantee that the training environment or checkpoint can be reproduced without the required dataset, software versions, hardware and execution scripts.
