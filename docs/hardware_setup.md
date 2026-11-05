# Hardware Setup

## Project Hardware

This project uses a physical SO101 leader–follower robotic arm setup for imitation-learning-based pick-and-place manipulation.

### Hardware Components

| Component | Purpose |
|---|---|
| SO101 Leader Arm | Human-operated demonstration input |
| SO101 Follower Arm | Executes the learned robot actions |
| Feetech Servo Motors | Control the robot joints |
| Camera | Captures visual observations |
| Computer with CUDA support | Runs model training and inference |

## Software Environment

The project uses:

- Python
- Hugging Face LeRobot
- PyTorch
- ACT (Action Chunking with Transformers)
- CUDA for GPU training

## Robot Configuration

The ACT policy uses the following observation and action features:

| Feature | Shape |
|---|---|
| Robot state | 6 |
| Camera image | 3 × 480 × 640 |
| Robot action | 6 |

The six-dimensional state and action representations correspond to the features configured for this experiment.

## Hardware Setup Workflow

1. Connect the leader and follower arms.
2. Connect the camera used for visual observations.
3. Verify that the robot and camera are detected by the computer.
4. Check the robot calibration and communication.
5. Confirm that the follower can execute commands safely.
6. Prepare the environment for demonstration collection.

## Important Notes

- Verify servo power requirements before connecting the robot.
- Confirm the correct serial ports before running LeRobot commands.
- Check motor calibration before physical execution.
- Keep hands and objects clear of the robot's movement area during testing.

The exact wiring diagram, power-supply specification and serial-port assignments should be documented using the actual hardware setup used in the experiment.
