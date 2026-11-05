# Training and Execution Workflow

## Overview

The SO101 pick-and-place project was trained and physically evaluated using the LeLab interface built around Hugging Face LeRobot.

Both training and physical policy execution were launched through the LeLab graphical interface rather than custom standalone Python scripts.

## 1. ACT Training

The ACT policy was trained using the combined demonstration dataset.

| Parameter | Value |
|---|---|
| Dataset | `kushaldatta96/so101-pick-place-combined` |
| Policy | ACT |
| Training steps | 10,000 |
| Batch size | 32 |
| Optimizer | AdamW |
| Learning rate | 1e-5 |
| Weight decay | 1e-4 |
| Device | CUDA |

The complete experiment configuration is documented in the `configs/` directory.

## 2. Physical Policy Execution

After training, the saved ACT checkpoint was loaded through the LeLab interface and executed on the physical SO101 robotic arm.

The robot performed the black-box pick-and-place task using its visual and robot-state observations.

Checkpoint: `checkpoint_010000`

## 3. Physical Evaluation

Five physical execution trials were performed:

- Successful trials: 4
- Failed trials: 1
- Observed success rate: 80%

## 4. Script Availability

The original experiment was launched through the LeLab graphical interface. The exact underlying executable scripts have not been independently recovered.

This repository therefore documents the actual workflow and configuration rather than presenting newly created scripts as original experiment files.
