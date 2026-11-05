# Configuration files

This directory contains the configuration files used for the SO101 ACT pick-and-place experiment.

Expected files:
- `config.json` — ACT policy/model configuration.
- `train_config.json` — dataset, optimizer, and training configuration.

**Important:** Keep the original `config.json` and `train_config.json` from the successful 10,000-step training run. They are experiment artifacts and should not be recreated from a summary or replaced with guessed values. This replacement package intentionally does not include reconstructed JSON files because the complete original contents have not been independently verified.
