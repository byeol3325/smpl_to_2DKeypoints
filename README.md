# SMPL to 2D Keypoints

This project demonstrates how to generate 2D keypoints from a 3D SMPL model using pre-trained SMPL or SMPL-X models. It includes visualization of the 3D body mesh and projection of 3D keypoints onto a 2D plane for human pose estimation.

## Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
  - [Download Pretrained SMPL Models](#download-pretrained-smpl-models)
  - [Running the Code](#running-the-code)
- [Explanation of Code](#explanation-of-code)
- [References](#references)

## Introduction
SMPL (Skinned Multi-Person Linear) is a 3D body model designed for human shape representation, widely used in computer vision and animation tasks. This project leverages either SMPL or SMPL-X models to generate 3D meshes and project them onto a 2D plane to extract keypoints, which are commonly used for:
- Human pose estimation
- Animation and motion capture
- Computer vision tasks like body tracking and action recognition

The projection of 3D joints onto 2D helps simulate how a camera captures a person's skeletal structure.

## Installation

1. Clone this repository and navigate to the project directory:
    ```bash
    git clone https://github.com/your-repo-url/smpl-to-2dkeypoints.git
    cd smpl-to-2dkeypoints
    ```
2. Activate the environment using the provided `environment.yml` file (if you have [Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html).):
    ```bash
    conda env create -f environment.yml
    conda activate smpl_env
    pip install mmhuman3d --no-deps
    ```

    or use requirements.txt
   ```bash
   pip install -r requirements.txt
   pip install mmhuman3d --no-deps
   ```

## Usage

### Download Pretrained SMPL Models
To run this project, you need to download the SMPL or SMPL-X pre-trained models:

- [Download SMPL models](https://smpl.is.tue.mpg.de/index.html)
- [Download SMPL-X models](https://smpl-x.is.tue.mpg.de/)

After downloading, place the `.pkl` model files in an appropriate directory (e.g., `pretrained_model/`) and update the path in your code.

### Running the Code

Once the environment is set up and the pretrained models are downloaded, you can run the code to visualize the 2D projections and 3D meshes:

1. Load the SMPL model and pass the necessary parameters (like betas, pose, etc.):
   ```python
   smpl_model = SMPL(model_path='path_to_smpl_model.pkl', gender='neutral', batch_size=1)


### Explanation of Code
smpl_model: Loads the SMPL model and provides the structure for generating 3D human body meshes.
project_3d_to_2d: Projects the 3D vertices and joints onto a 2D plane using simple pinhole camera projection.
plot_keypoints_2d: Visualizes the projected 2D keypoints on a plane.
The projection helps simulate a camera's view of the person, showing how 3D body keypoints are mapped to 2D image space.


### References
SMPL Model
SMPL-X Model
MMHuman3D for SMPL implementation and keypoint mapping.
