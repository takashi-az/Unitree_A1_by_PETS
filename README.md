# PETS for Unitree-A1
This repo contains a pytorch implementation of the wonderful model-based Reinforcement Learning algorithms proposed in [Deep Reinforcement Learning in a Handful of Trials using Probabilistic Dynamics Models](https://arxiv.org/abs/1805.12114).

As of now, the repo only supports the most high-performing variant: probabilistic ensemble for the learned dynamics model, TSinf trajectory sampling and Cross Entropy method for action optimization.

The code is structured with the same levels of abstraction as the original TF implementation, with the exception that the TF dynamics model is replaced by a Pytorch dynamics model.

## Requirements

1. The requirements in the original [TF implementation](https://github.com/kchua/handful-of-trials)
2. Pytorch 1.0.0

For specific requirements, please take a look at the pip dependency file `requirements.txt` and conda dependency file `environments.yml`.

## Running Experiments

Experiments for a particular environment can be run using:

```
python3 mbexp.py -ca model-type PE -ca prop-type TSinf -ca opt-type CEM
```

```
{
    "observations": NumPy array of shape
        [num_train_iters * nrollouts_per_iter + ninit_rollouts, trial_lengths, obs_dim]
    "actions": NumPy array of shape
        [num_train_iters * nrollouts_per_iter + ninit_rollouts, trial_lengths, ac_dim]
    "rewards": NumPy array of shape
        [num_train_iters * nrollouts_per_iter + ninit_rollouts, trial_lengths, 1]
    "returns": Numpy array of shape [1, num_train_iters * neval]
}
```

## results
![sample](movie.gif)
