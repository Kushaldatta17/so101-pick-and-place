# Physical Robot Evaluation

## Overview

After training the ACT policy for 10,000 steps, the saved checkpoint was tested on the physical SO101 robotic arm. The task was to pick up a black box and place it inside a bowl.

## Evaluation setup

| Parameter | Configuration |
|---|---|
| Robot | SO101 robotic arm |
| Policy | ACT |
| Checkpoint | `checkpoint_010000` |
| Training steps | 10,000 |
| Input | Camera observation and robot state |
| Output | Predicted robot actions |
| Environment | Physical robot |

## Results

| Metric | Result |
|---|---:|
| Total trials | 5 |
| Successful trials | 4 |
| Failed trials | 1 |
| Observed success rate | 80% |

Observed success rate = (4 successful trials / 5 total trials) × 100 = 80%.

## Failure observation

In one trial, the black box slipped during grasping. Grasp position/alignment, gripper closure, gripping force, and object contact surface are possible factors to investigate. These are possible contributing factors, not confirmed root causes.

## Interpretation and limitations

The policy completed the task in four out of five initial physical trials. Five trials are a small sample; the observed 80% rate is preliminary and not statistically conclusive. This result should not be presented as a guaranteed success rate or evidence of broad generalization.

## Future work

- Collect more demonstrations.
- Increase the number of physical evaluation trials.
- Improve and evaluate grasp stability.
- Test object-position variation.
- Record and analyse additional failure cases.
