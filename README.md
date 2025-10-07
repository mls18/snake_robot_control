# Planar Snake Robot with Game Theory Control

A 4-link planar snake robot simulation in Simscape Multibody, controlled using a PD controller for lateral undulation locomotion.

## Overview

This project demonstrates:
- Multi-body dynamics modeling in Simscape Multibody
- Control for underactuated systems
- Contact dynamics and friction modeling for snake locomotion
- CAD integration with Simulink

## Features

- **4-link serial chain** with 3 actuated revolute joints
- **Planar motion constraint** (X-Y plane)
- **Ground contact forces** with stick-slip friction model
- **PD controller** for coordinated joint actuation
- **Real-time visualization** in Mechanics Explorer

## Demo

![Simulink Model](demo/snake_robot_demo.mov)

## Requirements

- MATLAB R2024a or later (adjust based on your version)
- Simscape Multibody toolbox
- Simulink

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/snake-robot-controller.git
   cd snake-robot-controller
2. Open MATLAB and navigate to the project directory.
3. Run the model (for example, open the Simulink model file and press Run).

## Model Structure

Physical System
Links: 4 identical segments (mass: 0.042 kg each)
Joints: 3 revolute joints (Z-axis rotation)
Base: Planar joint (X-Y translation + Z rotation)
Ground contact: Spatial contact forces on each link

## Control Architecture

Input: Joint angles and velocities (θ₁, θ₂, θ₃, ω₁, ω₂, ω₃)
Output: Joint torques (τ₁, τ₂, τ₃)

## Key Parameters
```matlab
% Link properties
link_mass = 0.042;              % kg
link_length = 0.072;            % m (2 × 0.036)

% Contact parameters
friction_static = 1.2;
friction_dynamic = 0.8;
stiffness = 1e6;                % N/m
damping = 1e3;                  % N/(m/s)

% Control parameters
amplitude = 0.5;                % rad
frequency = 1.0;                % Hz
phase_shift = pi/3;             % rad
```
## Results

The snake robot successfully exhibits:
- Lateral undulation gait
- Forward locomotion on flat terrain
- Stable planar motion (no out-of-plane deviation)
- Smooth joint trajectories

## Project Background

This project was developed to demonstrate:

Multi-body system modelling capabilities in Simscape Multibody
Advanced control theory implementation 
CAD integration with simulation tools



## CAD Model Credits

The link geometry (TEST_SNAKE_BRACKET) is from:
[CAD file](https://grabcad.com/library/multibracket-snake-robot-1)

## License

This project is licensed under the MIT License - see the LICENSE
 file for details.

## Author

Maria Luisa Scarpa
PhD in Control Theory (Dynamical Systems, Optimal Control, Game Theory)
Background: Aeronautical Engineering
LinkedIn: [My profile](https://www.linkedin.com/in/maria-luisa-scarpa-2000/)
Email: [scarpa.mari@gmail.com/ mls18@ic.ac.uk]

## Acknowledgments

CAD model from [CAD file](https://grabcad.com/library/multibracket-snake-robot-1)
Simscape Multibody documentation and examples

