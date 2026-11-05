# Training and Execution Scripts

## Training Workflow

The ACT policy was trained using the LeLab interface built around Hugging Face LeRobot.

Training was configured through the LeLab interface rather than a custom standalone Python training script.

### Training Configuration

- Dataset: `kushaldatta96/so101-pick-place-combined`
- Policy: ACT (Action Chunking with Transformers)
- Training steps: 10,000
- Batch size: 32
- Optimizer: AdamW
- Learning rate: `1e-5`
- Weight decay: `1e-4`
- Compute device: CUDA

The complete configuration files are available in the [`configs/`](../configs/) directory.

## Physical Policy Execution

The trained checkpoint was evaluated on the physical SO101 leader–follower robotic arm.

The execution workflow used the trained ACT policy and the robot's camera and state observations to generate actions.

## Script Availability

Custom training and physical execution scripts are not included because the experiment was launched through the LeLab interface and the exact original executable files have not yet been recovered.

The repository documents the experiment and its configuration without presenting unverified scripts as original project code.
