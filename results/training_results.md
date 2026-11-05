# Training and Evaluation Results

## Experiment

- Task: SO101 black-box pick-and-place into a bowl
- Dataset: [kushaldatta96/so101-pick-place-combined](https://huggingface.co/datasets/kushaldatta96/so101-pick-place-combined)
- Dataset size: 30 episodes, 18,471 frames
- Policy: ACT
- Training steps: 10,000

## Training loss

| Step | Total loss |
|---:|---:|
| 6,000 | 0.145 |
| 7,000 | 0.130 |
| 8,000 | 0.119 |
| 9,000 | 0.115 |
| 10,000 | 0.106 |

## Final reported metrics

| Metric | Value |
|---|---:|
| Total loss | 0.106 |
| L1 loss | 0.089 |
| KL loss | 0.002 |

## Checkpoint

- Hugging Face repository: `kushaldatta96/act_2026-11-03_12-09-21`
- Checkpoint: `checkpoint_010000`
- Visibility: Private

The checkpoint was used for physical evaluation. Model weights are not included in this repository.

## Physical evaluation

| Metric | Result |
|---|---:|
| Total trials | 5 |
| Successful trials | 4 |
| Failed trials | 1 |
| Observed success rate | 80% |

In one trial, the black box slipped during grasping. Grasp position, gripper closure, and object contact conditions are possible areas for investigation. This five-trial evaluation is preliminary and not statistically conclusive.

## Key outcomes

- Combined 30 teleoperation demonstrations.
- Trained an ACT policy for 10,000 steps.
- Reached a final reported training loss of 0.106.
- Executed the trained checkpoint on the physical SO101.
- Completed four out of five initial trials successfully.
- Identified grasp stability as an area for improvement.
