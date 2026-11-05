# Physical Evaluation

## Objective

The objective of physical evaluation was to test whether the trained ACT policy could execute the demonstrated pick-and-place task on the physical SO101 robotic arm.

The task was to pick up a black box and place it inside a bowl.

## Evaluation Setup

- Robot: SO101 follower arm
- Policy: ACT
- Training checkpoint: `checkpoint_010000`
- Training steps: 10,000
- Execution: Physical robot

The trained checkpoint was executed on the physical robot.

## Evaluation Results

A total of five physical trials were performed.

| Metric | Result |
|---|---:|
| Total trials | 5 |
| Successful trials | 4 |
| Failed trials | 1 |
| Observed success rate | 80% |

## Failure Observation

In one trial, the black box slipped during grasping.

Possible areas to investigate include:

- Grasp alignment
- Gripper closure
- Object contact conditions

These are possible investigation areas, not confirmed root causes.

## Interpretation

The robot successfully completed the task in four out of five observed trials.

The observed 80% success rate is preliminary because the evaluation involved only five trials. A larger number of trials is required to estimate performance more reliably.

## Future Evaluation

Further evaluation should include:

1. More physical execution trials.
2. Repeated testing under the same initial conditions.
3. Testing with different object positions.
4. Investigation of grasp failures.
5. Evaluation of consistency across repeated executions.

## Conclusion

The experiment demonstrates physical execution of a trained ACT policy on the SO101 robotic arm, with four successful pick-and-place trials out of five observed attempts.
