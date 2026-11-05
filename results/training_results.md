# Training and Evaluation Results

## Experiment Summary

This experiment trained an ACT policy using demonstrations collected with a physical SO101 leader–follower robotic arm.

The objective was to pick up a black box and place it inside a bowl.

## Dataset

| Parameter | Result |
|---|---|
| Dataset repository | `kushaldatta96/so101-pick-place-combined` |
| Episodes | 30 |
| Frames | 18,471 |
| FPS | 30 |
| Camera count | 1 |
| Resolution | 640 × 480 |
| Approximate size | 257 MB |

## Training Configuration

| Parameter | Value |
|---|---|
| Policy | ACT |
| Training steps | 10,000 |
| Batch size | 32 |
| Optimizer | AdamW |
| Learning rate | 1e-5 |
| Weight decay | 1e-4 |
| Gradient clipping | 10 |
| Backbone | ResNet-18 |
| Model dimension | 512 |
| Attention heads | 8 |
| Encoder layers | 4 |
| Decoder layers | 1 |
| Chunk size | 100 |
| Device | CUDA |

## Training Loss

Reported loss progression:

| Training step | Total loss |
|---:|---:|
| 6,000 | 0.145 |
| 7,000 | 0.130 |
| 8,000 | 0.119 |
| 9,000 | 0.115 |
| 10,000 | 0.106 |

### Final Metrics

| Metric | Value |
|---|---:|
| Total loss | 0.106 |
| L1 loss | 0.089 |
| KL loss | 0.002 |

The loss values describe the training run and do not independently establish real-world task performance.

## Physical Robot Evaluation

The trained 10,000-step checkpoint was tested on the physical SO101 arm.

| Evaluation metric | Result |
|---|---:|
| Total trials | 5 |
| Successful trials | 4 |
| Failed trials | 1 |
| Observed success rate | 80% |

One failed trial involved the box slipping during grasping.

This five-trial result is preliminary and is not a statistically conclusive performance estimate.

## Checkpoint Information

- Model repository: `kushaldatta96/act_2026-11-03_12-09-21`
- Checkpoint: `checkpoint_010000`
- Repository visibility: Private
- Model weights: Not included in this GitHub repository

## Key Findings

- The ACT policy completed physical pick-and-place execution.
- Four of the five observed trials were successful.
- One trial failed during grasping.
- Additional physical trials are needed to evaluate reliability.

## Future Improvements

- Increase demonstration dataset size.
- Improve grasp reliability.
- Test different object positions.
- Perform more physical evaluation trials.
- Publish verified execution scripts and reproducibility instructions.
