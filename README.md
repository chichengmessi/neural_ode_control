## Codes for neural ode control

Paper: https://arxiv.org/abs/2401.01836

Neural ODE Control is a neural ODE based method for controlling unknown dynamical systems,  which combines dynamics identification and optimal control learning using a coupled neural ODE. Through an intriguing interplay between the two neural networks in coupled neural ODE structure, our model concurrently learns system dynamics as well as optimal controls that guides towards target states. Our experiments demonstrate the effectiveness of our model for learning optimal control of unknown dynamical systems.

Basically, the neural ODE strcuture that we use is 

![Screenshot 2024-04-22 122106](https://github.com/chichengmessi/neural_ode_control/assets/43145509/d199d0f6-5ff2-44b4-a16d-2fd50bd17897)

And we can get the trajectory - which is the predicted trajectory under the current controller via

![Screenshot 2024-04-22 122106](https://github.com/chichengmessi/neural_ode_control/assets/43145509/5ca3be0b-31b9-42c3-94d8-2b0777a1d509)

From which we can build our loss function: minimize the control objective loss (e.g. distance between XT and some target states) and the trajectory fitting loss (e.g. deviations between real trajectories in the environment using current controller and the predicted trajectories)
