# Data Collection

## Task

Collect demonstrations of the SO101 arm picking up a black box and placing it inside a bowl.

## Dataset

Hugging Face dataset: [kushaldatta96/so101-pick-place-combined](https://huggingface.co/datasets/kushaldatta96/so101-pick-place-combined)

| Parameter | Value |
|---|---:|
| Episodes | 30 |
| Frames | 18,471 |
| Recording rate | 30 FPS |
| Cameras | 1 |
| Image resolution | 640 × 480 |
| Approximate dataset size | 257 MB |

## Collection workflow

1. Connect and calibrate the SO101 leader and follower arms.
2. Position the black box and bowl within the robot's working area.
3. Start the camera and verify the visual feed.
4. Use the leader arm to demonstrate the task.
5. Record the follower observations and actions.
6. Repeat until the demonstration set is collected.
7. Combine the demonstrations into the final dataset.

An episode is one recorded demonstration. The combined dataset used for training contains 30 episodes and 18,471 frames, with visual observations from one camera and robot state/action information.

## Collection considerations

- Keep camera positioning consistent.
- Keep the task objects visible.
- Avoid unnecessary interruptions.
- Record complete attempts.
- Verify robot calibration before collection.
