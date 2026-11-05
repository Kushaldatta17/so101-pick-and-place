# ACT Policy Training

## Dataset

The ACT policy was trained using the combined SO101 pick-and-place demonstration dataset:

[kushaldatta96/so101-pick-place-combined](https://huggingface.co/datasets/kushaldatta96/so101-pick-place-combined)

## Training configuration summary

| Parameter | Value |
|---|---:|
| Policy | ACT |
| Training steps | 10,000 |
| Batch size | 32 |
| Optimizer | AdamW |
| Learning rate | 1e-5 |
| Weight decay | 1e-4 |
| Gradient clipping | 10 |
| Vision backbone | ResNet-18 |
| Model dimension | 512 |
| Attention heads | 8 |
| Encoder layers | 4 |
| Decoder layers | 1 |
| Chunk size | 100 |
| Observation steps | 1 |
| Device | CUDA |
| Random seed | 1000 |

Refer to the original files in `configs/` for the complete run configuration.

## Reported training metrics

| Step | Total loss |
|---:|---:|
| 6,000 | 0.145 |
| 7,000 | 0.130 |
| 8,000 | 0.119 |
| 9,000 | 0.115 |
| 10,000 | 0.106 |

Final reported metrics:

| Metric | Value |
|---|---:|
| Total loss | 0.106 |
| L1 loss | 0.089 |
| KL loss | 0.002 |

Training loss alone does not establish real-world task success or generalization.

## Checkpoint

- Hugging Face repository: `kushaldatta96/act_2026-11-03_12-09-21`
- Checkpoint: `checkpoint_010000`
- Training steps: 10,000
- Repository visibility: Private

The checkpoint was used for physical evaluation. Model weights are not included in this GitHub repository.
