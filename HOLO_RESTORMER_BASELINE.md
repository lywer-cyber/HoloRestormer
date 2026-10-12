# HoloRestormer baseline

This repository contains the digital-holography HoloRestormer baseline built
on the Restormer training framework.

## Frozen configuration

- `configs/holo/experiment_config_v7.txt` is the machine-readable v7
  experiment configuration.
- `configs/holo/全息超分-实验协议-冻结版-v7.md` is the accompanying frozen
  protocol.
- The HoloRestormer-specific dataset, metric, determinism, AMP, accumulation,
  EMA, checkpoint, and evaluation code lives under `basicsr/`.

SwinIR comparison files are intentionally not part of this baseline branch.
Datasets, generated LR images, checkpoints, and model weights are also not
tracked in Git.

## Branch workflow

`baseline/v7` is the immutable starting point for the HoloRestormer baseline.
Create every future HoloRestormer module change from that branch (or from the
latest reviewed HoloRestormer feature branch), for example:

```bash
git switch baseline/v7
git switch -c feature/<short-description>
```

Keep protocol/config changes separate from architecture changes and open a
pull request back to the baseline branch for review.
