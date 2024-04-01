# Towards Long Term SLAM on Thermal Imagery
This is the repository for the thermal imagery dataset presented in ["Towards Long Term SLAM on Thermal Imagery"](https://arxiv.org/abs/2403.19885) submitted to IROS 2024. The goal of the dataset is to provide training data, and to provide a baseline for testing day to night, and night to day relocalization on IR imagery for SLAM. The dataset format is described below. In the paper we use a fork of DBoW2 which can be found [here](https://github.com/c-keil/DBoW2), and a fork of Gluestick which can be found [here](https://github.com/c-keil/GlueStick). We are not realeasing the SLAM code at this time due to some overlap with currently unpublished work.

The dataset is currently hosted [HERE](https://drive.google.com/drive/folders/1icfFiF5_Dr6Gu2h0CgKb51CQRqeyWsMX?usp=drive_link).

## Dataset Summary
The dataset has three main parts:
1. 24 hour timelapses of static scenes
2. Paired day-night stereo trajectories collected in the same location with an RTK GPS position ground truth
3. Simple thermal image sequences that can be used for training BoW vocabularies, or other unsupervised SLAM tasks
All imagery is presented in a 640x512 16bit raw format collected with FLIR Boson ADK cameras with a 75 degree horizontal field of view.

## Timelapse Sets

## Paired Trajectories

## Unsupervised Training Data

### CLAHE
In our work we preprocess images with the Matlab implementation of CLAHE with the following settings:
```
adapthisteq(im(:,:,1), 'clipLimit', 0.4, 'NBins', 2^16, 'Distribution', 'rayleigh');
```
