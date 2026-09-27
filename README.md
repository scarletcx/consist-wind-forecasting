# CONSIST-WIND: Fast Probabilistic Wind Power Forecasting

This repository accompanies the manuscript:

> **Fast Probabilistic Wind Power Forecasting via One-Step Consistency Distillation and Memory-Efficient CRPS Optimization**
>
> *Submitted to Mathematics, Special Issue: High-Performance Computing-Driven AI Learning and Optimization*

## Code availability

**The code will be released here upon publication of the manuscript.**

It will include the full implementation of CONSIST-WIND, the reproduction code
for every baseline, the training and evaluation configuration files, and the
scripts that regenerate every table and figure in the paper.

## Abstract

Grid operators scheduling wind power act on the width of the predicted
distribution, and diffusion-based forecasters have reported strong accuracy on
wind benchmarks. That accuracy can come from a sampling chain of a hundred or
more evaluations per member, while a one-step student distilled from such a
chain can concentrate its members into a spread narrower than its own error.
CONSIST-WIND is a one-step probabilistic wind power forecaster. A frozen point
backbone supplies the conditioning context; a teacher diffusion model on
numerical weather prediction residuals is distilled into a one-step consistency
student, one function evaluation per member, and a stabilized shifted-logit warp
maps generated members to the physical power range. A fourth phase calibrates
the student by training its ensemble against the continuous ranked probability
score, which recovers the spread and raises the accuracy of the one-step
forecast. The sorted-rank form of the CRPS gives a quasilinear-time, linear-memory
calibration objective, and query-chunked attention keeps the backbone inside the
kernel launch limit, so the whole pipeline trains and runs on a single device
with limited compute.

## Datasets

All experiments use publicly available datasets:

- **GEFCom2014-W**: 10 wind power zones at hourly resolution
- **GEFCom2012-W**: 7 wind farms at hourly resolution
- **SDWPF (KDD Cup 2022)**: 134 turbines at 10-minute resolution

## Citation

If you refer to this work, please cite:

```bibtex
@article{he2027consistwind,
  title={Fast Probabilistic Wind Power Forecasting via One-Step Consistency
         Distillation and Memory-Efficient CRPS Optimization},
  author={He, Chao and Zhou, Fangqi and Wang, Yu and Huang, Hao and
          Wang, Zijian and Zheng, Jianbo},
  journal={Mathematics},
  year={2027},
  note={Under review}
}
```

## Contact

- **Corresponding author**: Jianbo Zheng (zhengjianbo1995@163.com)
