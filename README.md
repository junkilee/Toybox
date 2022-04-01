# The Reinforcement Learning Toybox ![CI](https://github.com/toybox-rs/Toybox/workflows/CI/badge.svg)

A set of games designed for testing deep RL agents. This repo contains Python wrappers and an intervention API for Toybox games. Python wrappers for the Atari games are constructed to mock the Arcade Learning Environment and subclass the gym.envs.atari.AtariEnv wrapper. [ToyboxBaseEnv](https://github.com/toybox-rs/Toybox/blob/main/toybox/envs/atari/base.py) may be a good entry point for the gym wrappers.

If you use this code, or otherwise are inspired by our white-box testing approach, please cite our [NeurIPS workshop paper](https://arxiv.org/abs/1812.02850):

```
@inproceedings{foley2018toybox,
  title={{Toybox: Better Atari Environments for Testing Reinforcement Learning Agents}},
  author={Foley, John and Tosch, Emma and Clary, Kaleigh and Jensen, David},
  booktitle={{NeurIPS 2018 Workshop on Systems for ML}},
  year={2018}
}
```

We have a lenghtier paper on [ArXiV](https://arxiv.org/pdf/1905.02825.pdf) and can provide a draft of a non-public paper on our acceptance testing framework by request (email at etosch at cs dot umass dot edu).

## How accurate are your games?

[Watch four minutes of agents playing each game](https://www.youtube.com/watch?v=spx_YQQW1Lw). Both ALE implementations and Toybox implementations have their idiosyncracies, but the core gameplay and concepts have been captured. Pull requests always welcome to improve fidelity.

## Where is the actual Rust code?

The rust implementations of the games have moved to a different repository: [toybox-rs/toybox-rs](https://github.com/toybox-rs/toybox-rs)

## Installation
1. Create a virtual environment using your python3 installation: `${python} -m venv venv`
   * **OSX** 
      * On OSX `${python}`, this is likely `python3`: thus, your command will be `python3 -m venv venv`
      * If you are not sure of your version, run `python --version`
   * **Windows** (_not fully tested!_)
      * If you are on Windows, your command will likely be: `{python}`
2. Activate your virtual environment:
   * **BSD-ish**: `source venv/bin/activate`
   * **Windows**: `venv/Scripts/activate`
4. Install Toybox:

```    
pip install ctoybox
pip install git+https://github.com/toybox-rs/Toybox
```
_Note: if you are trying to run from Windows, you will need to build from source. See instructions for [building](https://github.com/toybox-rs/toybox-rs/blob/main/docs/new-game-help.md) here._
4. Install requirements: run `pip install -r REQUIREMENTS.txt`
5. Run `python setup.py install`


## Play the games (using pygame)

    pip install ctoybox pygame
    python -m ctoybox.human_play breakout
    python -m ctoybox.human_play amidar
    python -m ctoybox.human_play space_invaders

## Run the tests

Sample behavioral tests developed with Toybox are frozen and [available here](https://github.com/toybox-rs/openai-baselines-envs). These tests are featured with an OpenAI baselines integration to facilitate off-the-shelf model training.


## Python

Tensorflow, OpenAI Gym, OpenCV, and other libraries may or may not break with various Python versions. We have confirmed that the code in this repository will work with the following Python versions:

* 3.6, 3.7

## Get starting images for reference from ALE / atari_py

`./scripts/utils/start_images --help` 
