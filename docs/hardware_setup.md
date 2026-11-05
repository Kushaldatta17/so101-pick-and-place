# Hardware Setup

## Task

The project uses a physical SO101 robotic arm to pick up a black box and place it inside a bowl.

## Hardware components

| Component | Role |
|---|---|
| SO101 leader arm | Human-operated input for demonstrations |
| SO101 follower arm | Executes the demonstrated movements |
| Feetech servos | Actuate the robot joints |
| Camera | Captures visual observations |
| USB/serial connection | Connects the robot control interface to the computer |
| Power supply | Supplies the servo system |

## Software environment

| Component | Used environment |
|---|---|
| Host operating system | Windows 11 |
| Linux environment | Ubuntu 22.04 through WSL 2 |
| Robotics framework | Hugging Face LeRobot |
| Programming language | Python |
| ML framework | PyTorch |
| Policy | ACT |

## Leader–follower workflow

1. Connect and calibrate the leader and follower arms.
2. Verify the camera feed and robot connection.
3. Use the leader arm to demonstrate the pick-and-place task.
4. Record the follower observations and actions through LeRobot.

Use the exact port names, calibration files, and power requirements from the working hardware setup. They are intentionally not hard-coded here because device paths and hardware revisions can differ.
