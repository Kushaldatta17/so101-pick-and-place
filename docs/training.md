# ACT Policy Training

## Overview

The project uses Action Chunking with Transformers (ACT), an imitation-learning approach that learns robot actions from human demonstrations.

The policy was trained using the SO101 pick-and-place demonstration dataset hosted on Hugging Face.

## Training Dataset

Dataset repository:

`kushaldatta96/so101-pick-place-combined`

| Parameter | Value |
|---|---|
| Episodes | 30 |
| Frames | 18,471 |
| FPS | 30 |
| Camera | 1 |
| Image resolution | 640 × 480 |

## ACT Architecture

The training configuration specifies the following architecture:

| Parameter | Value |
|---|---|
| Policy | ACT |
| Vision backbone | ResNet-18 |
| Model dimension | 512 |
| Attention heads | 8 |
| Feedforward dimension | 3200 |
| Encoder layers | 4 |
| Decoder layers | 1 |
| Chunk size | 100 |
| Observation steps | 1 |
| Action steps | 100 |
| Latent dimension | 32 |
| VAE | Enabled |
| Dropout | 0.1 |
| KL weight | 10.0 |

## Training Hyperparameters

| Parameter | Value |
|---|---|
| Training steps | 10,000 |
| Batch size | 32 |
| Optimizer | AdamW |
| Learning rate | 0.00001 |
| Weight decay | 0.0001 |
| Gradient clipping norm | 10 |
| Random seed | 1000 |
| Device | CUDA |
| Mixed precision | Disabled |

## Training Configuration

The experiment used the following settings:

- Dataset repository: `kushaldatta96/so101-pick-place-combined`
- Policy type: ACT
- Checkpoint saving: Enabled
- Checkpoint interval: Every 1,000 steps
- Checkpoint format: Safetensors
- Model repository: `kushaldatta96/act_2026-11-03_12-09-21`

The full configuration is documented in:

- `configs/config.json`
- `configs/train_config.json`

## Training Results

The reported final metrics were:

| Metric | Value |
|---|---:|
| Total loss | 0.106 |
| L1 loss | 0.089 |
| KL loss | 0.002 |

These are training metrics and should not be interpreted as direct measurements of physical task success.

## Checkpoint

The trained checkpoint is:

`checkpoint_010000`

It is stored in a private Hugging Face model repository. The model weights are not included in this GitHub repository.

## Important Notes

The configuration files document the reported experiment. Exact reproduction also requires the original software environment, compatible LeRobot version, dataset, hardware and execution scripts.
