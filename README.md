# SO101 Robotic Arm – ACT-Based Pick-and-Place

A physical robot-learning project using a **SO101 leader–follower robotic arm** and **Hugging Face LeRobot**. The objective is to pick up a black box and place it inside a bowl.

The project follows an imitation-learning workflow: collect human demonstrations, prepare a dataset, train an Action Chunking with Transformers (ACT) policy, and evaluate the trained policy on the physical robot.

## Project Results

| Item | Result |
|---|---|
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

**Evaluation note:** The five-trial result is a small preliminary evaluation, not a statistically conclusive performance estimate. One trial failed when the box slipped during grasping.

## Physical Demonstration

A video of the trained ACT policy executing the pick-and-place task on the physical SO101 arm is available below.

[**Watch the physical pick-and-place demonstration**](

https://github.com/user-attachments/assets/c3684f3b-69d2-4262-b630-b0155ec5631f

)

## Dataset

The combined demonstration dataset is hosted on Hugging Face:

[**kushaldatta96/so101-pick-place-combined**](https://huggingface.co/datasets/kushaldatta96/so101-pick-place-combined)

Dataset details:
- 30 demonstration episodes
- 18,471 frames
- 30 FPS
- One camera
- Image resolution: 640 × 480
- Approximate dataset size: 257 MB

## Model and Training

The project uses **Action Chunking with Transformers (ACT)**, an imitation-learning policy that predicts sequences of robot actions from observations.

| Parameter | Value |
|---|---|
| Policy | ACT |
| Vision backbone | ResNet-18 |
| Training steps | 10,000 |
| Batch size | 32 |
| Optimizer | AdamW |
| Learning rate | 1e-5 |
| Weight decay | 1e-4 |
| Gradient clipping | 10 |
| Training device | CUDA |

### Final Training Metrics

| Metric | Value |
|---|---:|
| Total loss | 0.106 |
| L1 loss | 0.089 |
| KL loss | 0.002 |

Training loss alone does not establish real-world success or generalization. Physical evaluation is therefore included separately.

### Model Checkpoint

The trained checkpoint is stored in a private Hugging Face model repository:

- Repository: `kushaldatta96/act_2026-11-03_12-09-21`
- Checkpoint: `checkpoint_010000`

The model weights are not included in this GitHub repository. The Hugging Face repository is private, so visitors may not be able to access the checkpoint.

## Physical Evaluation

The trained 10,000-step checkpoint was executed on the physical SO101 arm for five trials.

- Successful trials: 4
- Failed trials: 1
- Observed success rate: 80%

The failed attempt involved the black box slipping during grasping. Grasp alignment, gripper closure, and object contact conditions are possible areas to investigate, but the root cause has not been confirmed.

The five trials are an initial physical evaluation and should not be treated as a definitive measure of policy performance.

## Repository Structure

```text
so101-pick-and-place/
├── configs/
│   ├── README.md
│   ├── config.json
│   └── train_config.json
├── docs/
│   ├── hardware_setup.md
│   ├── data_collection.md
│   ├── training.md
│   └── evaluation.md
├── media/
│   ├── README.md
│   └── pick-and-placemp4.mp4
├── results/
│   └── training_results.md
├── scripts/
│   └── README.md
├── .gitignore
└── README.md
```

**Note:** The `scripts/` folder currently contains documentation, not the original executable project scripts. Verified scripts from the actual experiment can be added later.

## Documentation

- [Hardware Setup](docs/hardware_setup.md)
- [Data Collection](docs/data_collection.md)
- [Training](docs/training.md)
- [Physical Evaluation](docs/evaluation.md)
- [Training Results](results/training_results.md)
- [Configuration Notes](configs/README.md)
- [Scripts Notes](scripts/README.md)
- [Media Notes](media/README.md)

## Limitations and Future Work

The current physical evaluation consists of only five trials. Further work should focus on:

- Collecting additional demonstration episodes.
- Running more physical evaluation trials.
- Improving grasp reliability.
- Testing the policy with variations in object position.
- Documenting repeatable setup, training, and execution commands.
- Adding verified executable scripts to the repository.

## Technologies Used

- Python
- Hugging Face LeRobot
- Action Chunking with Transformers (ACT)
- PyTorch
- SO101 robotic arm
- Feetech servo motors
- CUDA

---

**Project focus:** Physical robot learning, imitation learning, ACT policy training, and real-world robotic manipulation.
