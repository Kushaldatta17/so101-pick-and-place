# SO101 Robotic Arm – ACT-Based Pick-and-Place

A physical robot-learning project using a **SO101 leader–follower robotic arm** and **Hugging Face LeRobot**. The objective is a single manipulation task: pick up a black box and place it inside a bowl.

The project follows an imitation-learning workflow: collect human demonstrations, prepare a dataset, train an Action Chunking with Transformers (ACT) policy, and evaluate the trained policy on the physical robot.

## Project results

| Item | Result |
|---|---:|
| Task | Pick up a black box and place it inside a bowl |
| Demonstrations | 30 episodes |
| Dataset frames | 18,471 |
| Recording rate | 30 FPS |
| Camera count | 1 |
| Image resolution | 640 × 480 |
| ACT training steps | 10,000 |
| Final reported training loss | 0.106 |
| Physical evaluation | 4 successful trials / 5 |
| Observed success rate | 80% (preliminary; five trials) |

The five-trial result is a small preliminary evaluation, not a statistically conclusive performance estimate. One trial failed when the box slipped during grasping.

## Physical demonstration

A physical execution video belongs in [`media/`](media/). Add the video file to that folder and update the link below to its exact filename.

<!-- Example after uploading: [Watch the physical pick-and-place demonstration](media/pick-and-place-demo.mp4) -->

## Dataset

The combined demonstration dataset is hosted on Hugging Face:

[**kushaldatta96/so101-pick-place-combined**](https://huggingface.co/datasets/kushaldatta96/so101-pick-place-combined)

Dataset details: 30 episodes, 18,471 frames, 30 FPS, one camera at 640 × 480 resolution. The dataset is approximately 257 MB.

## Model and training

- Policy: Action Chunking with Transformers (ACT)
- Vision backbone: ResNet-18
- Training steps: 10,000
- Batch size: 32
- Optimizer: AdamW
- Learning rate: 1e-5
- Weight decay: 1e-4
- Gradient clipping: 10
- Device: CUDA

The reported final metrics were total loss 0.106, L1 loss 0.089, and KL loss 0.002. Training loss alone does not establish real-world success or generalization.

The trained checkpoint is stored in a **private** Hugging Face model repository: `kushaldatta96/act_2026-11-03_12-09-21`, checkpoint `checkpoint_010000`. The model weights are not included in this GitHub repository, and the private checkpoint may not be accessible to visitors.

## Physical evaluation

The trained checkpoint was executed on the physical SO101 arm for five trials:

- 4 successful pick-and-place trials
- 1 failed trial
- Observed success rate: 80%

The failed attempt involved the black box slipping during grasping. Grasp alignment, gripper closure, and object contact conditions are possible areas to investigate; they have not been confirmed as root causes.

## Repository structure

```text
so101-pick-and-place/
├── configs/       # ACT and training configuration files
├── docs/          # Hardware, data collection, training, evaluation
├── media/         # Physical demonstration video
├── results/       # Training and evaluation summary
└── scripts/       # Verified project scripts (add when available)
```

## Documentation

- [Hardware setup](docs/hardware_setup.md)
- [Data collection](docs/data_collection.md)
- [Training](docs/training.md)
- [Physical evaluation](docs/evaluation.md)
- [Training results](results/training_results.md)
- [Configuration notes](configs/README.md)
- [Scripts notes](scripts/README.md)
- [Media notes](media/README.md)

## Limitations and future work

The physical evaluation currently contains only five trials. Further work should collect more demonstrations, run more evaluation trials, improve grasp reliability, test object-position variation, and document repeatable setup and execution commands.

## Technologies

Python · Hugging Face LeRobot · ACT · PyTorch · SO101 · CUDA
