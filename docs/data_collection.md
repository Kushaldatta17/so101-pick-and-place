# Data Collection

## Objective

The objective of data collection was to record human demonstrations of a pick-and-place task using the SO101 leader–follower robotic arm.

The task involved picking up a black box and placing it inside a bowl.

## Demonstration Collection

The human operator controlled the leader arm, while the follower arm performed the corresponding movements.

LeRobot was used to record the demonstrations and create the dataset used for ACT policy training.

## Dataset Information

| Parameter | Value |
|---|---|
| Dataset | `kushaldatta96/so101-pick-place-combined` |
| Total episodes | 30 |
| Total frames | 18,471 |
| Recording frequency | 30 FPS |
| Camera count | 1 |
| Image resolution | 640 × 480 |
| Approximate dataset size | 257 MB |

## Observation and Action Features

The training configuration specifies:

### Robot State

```text
observation.state
Shape: [6]
```

### Camera Observation

```text
observation.images.k
Shape: [3, 480, 640]
```

### Robot Action

```text
action
Shape: [6]
```

## Dataset Hosting

The combined dataset is hosted on Hugging Face:

[SO101 Pick-and-Place Combined Dataset](https://huggingface.co/datasets/kushaldatta96/so101-pick-place-combined)

## Data Collection Workflow

1. Set up and calibrate the SO101 leader and follower arms.
2. Position the black box and bowl in the workspace.
3. Operate the leader arm to demonstrate the task.
4. Record the robot observations, camera images and actions.
5. Collect and organize the demonstration episodes.
6. Combine the recorded episodes into the training dataset.
7. Verify the dataset before training.

## Notes

The dataset contains 30 demonstration episodes. The same combined dataset was used for the reported ACT training experiment.

The training configuration specifies `eval_split: 0.0`, so no separate dataset evaluation split was configured in that experiment.
