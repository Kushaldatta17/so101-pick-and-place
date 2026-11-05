# Project Scripts

## Overview

This directory is reserved for the executable scripts used in the SO101 ACT pick-and-place project.

The project workflow involves:

1. Robot connection and calibration.
2. Demonstration collection.
3. Dataset preparation.
4. ACT policy training.
5. Physical policy execution.
6. Evaluation and result recording.

## Script Availability

The original executable scripts used in the successful experiment have not yet been added to this repository.

They should only be added after verifying that they correspond to the actual experiment.

## Recommended Organization

```text
scripts/
├── README.md
├── record_episodes.py
├── train_act.py
├── evaluate_policy.py
└── run_policy.py
```

These are suggested filenames and organization, not verified original scripts.

## Reproducibility

Before adding scripts, verify:

- LeRobot version and command arguments.
- Dataset repository and configuration.
- ACT training settings.
- Checkpoint path.
- Robot connection and camera settings.
- Physical execution procedure.

Do not treat the suggested filenames as executable files until the actual scripts have been added and tested.
