# SO101 Pick-and-Place – Project Architecture

## System Workflow

The project follows a complete robot learning workflow, starting with physical demonstrations and ending with real-world execution using a trained ACT policy.

```text
┌──────────────────────────────┐
│     SO101 Leader-Follower    │
│       Teleoperation          │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│       Data Collection        │
│      30 Demonstrations       │
│       18,471 Frames          │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│     LeRobot Dataset          │
│   Camera + Robot States      │
│       + Action Data          │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│       ACT Policy Training    │
│       10,000 Training Steps  │
│       ResNet-18 Backbone     │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│       Trained Checkpoint     │
│       ACT Policy             │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│      LeLab Execution         │
│  Load Policy and Run Robot   │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│    Physical SO101 Robot      │
│       Pick-and-Place         │
└──────────────────────────────┘
```

## Workflow Explanation

1. **Teleoperation:** Demonstrations were collected using the SO101 leader-follower robotic arm setup.
2. **Data Collection:** 30 demonstrations containing 18,471 frames were recorded.
3. **Dataset:** The demonstrations were organized into a LeRobot-compatible dataset containing camera observations, robot states, and action data.
4. **Policy Training:** An Action Chunking with Transformers (ACT) policy was trained for 10,000 steps using the collected dataset.
5. **Checkpoint:** The trained ACT model checkpoint was saved.
6. **Physical Execution:** The trained policy was loaded and executed on the physical SO101 robot through the LeLab graphical interface.

## Implementation Note

Both model training and physical policy execution were launched through the LeLab graphical interface. This repository documents the workflow and configuration; it does not claim custom standalone training or inference scripts.
