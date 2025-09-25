# Neural ODE Control (NODEC)

**Paper:** [Neural ODE Control: A Neural ODE Based Method for Controlling Unknown Dynamical Systems](https://arxiv.org/abs/2401.01836)

## Overview

Neural ODE Control (NODEC) is a novel approach for controlling unknown dynamical systems that combines dynamics identification and optimal control learning using a coupled neural ODE architecture. Through an intriguing interplay between two neural networks in the coupled structure, our model concurrently learns both system dynamics and optimal controls that guide the system towards target states. Our experiments demonstrate the effectiveness of NODEC for learning optimal control of unknown dynamical systems.

## Architecture

The neural ODE structure we use is illustrated below: 

![Screenshot 2024-04-22 122106](https://github.com/chichengmessi/neural_ode_control/assets/43145509/d199d0f6-5ff2-44b4-a16d-2fd50bd17897)

We can obtain the predicted trajectory under the current controller as shown below:

![Screenshot 2024-04-22 122106](https://github.com/chichengmessi/neural_ode_control/assets/43145509/5ca3be0b-31b9-42c3-94d8-2b0777a1d509)

## Training Algorithm

The training process for NODEC follows the algorithm illustrated below:

![Training Algorithm](assets/algorithm.png)

## Loss Function

From the architecture, we can build our loss function by minimizing two key components:

- **Control Objective Loss**: Distance between the final state X_T and target states
- **Trajectory Fitting Loss**: Deviations between real trajectories in the environment (using the current controller) and the predicted trajectories

## Learning Process

The following animation demonstrates the learning process of NODEC on simple dynamics, showing the rollout in learned dynamics versus ground truth dynamics.

**Animation Layout:**
- **Left side**: Rollout diagram showing trajectory evolution
- **Right side**: Control signal used during that rollout

The rollouts with the same controller being trained are performed in both:
- **Learned dynamics (g)**: The neural network's approximation of the system
- **Ground truth dynamics (f)**: The actual system dynamics

**Key Observations as Training Progresses:**

- The learned dynamics becomes increasingly accurate compared to the ground truth (rollout lines converge)
- The control quality improves as the system gets closer to the target state
- Through mutual supervision between the dynamics learner and controller networks, the model simultaneously learns optimal control and system dynamics

![Learning Process](assets/learning_process.gif)
