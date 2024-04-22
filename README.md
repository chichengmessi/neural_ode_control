## Codes for neural ode control

Paper: https://arxiv.org/abs/2401.01836

Neural ODE Control is a neural ODE based method for controlling unknown dynamical systems,  which combines dynamics identification and optimal control learning using a coupled neural ODE. Through an intriguing interplay between the two neural networks in coupled neural ODE structure, our model concurrently learns system dynamics as well as optimal controls that guides towards target states. Our experiments demonstrate the effectiveness of our model for learning optimal control of unknown dynamical systems.

Basically, the neural ODE strcuture that we use is \dot{x} =  {g}_{\gamma}(x, {h}_{\theta}(x, t), t) \\ 
