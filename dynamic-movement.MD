# Dynamic Movement Primitives in Robotics
Biological systems, including human beings, have the innate ability to perform complex tasks in versatile and agile
manner. These biological systems are then able to combine basic units into more complex task, leading to the formulation os the motor primitives theory.  
In this respect, the **Dynamic Movement Primitives (DMP)** are an excellent mathematical formulation of these motor primitives as a stable Dyanamical Systems, and are used to generate commands for robots.  

## How do Biological Systems move?
The research in neurobiology motor control, led to the formulation of the *Motion Primitive Theory* This explains the exceution of the complex movements with sequencing of primitive actions, which can be directly implemented in robotic systems.  

DMPs are thus the first to attempt to answer the question. 
> How artificial systems, like (humanoid) robots, can execute complex movements in a versatile and creative manner?

Other properties of DMP are: 
* simple and elegant formulation
* guarantee convergence to a given target
* are sufficiently flexible to create complex behaviors
* are capable of reacting to external perturbations in real-time
* and can be learned from data using efficient algorithms.

Thus establishing as a prominent tool for learning and generation of motor commands.

# Formulation of DMPs types
## Discrete DMP
The discrete DMP is used to encode a point-to-point motion
into a stable dynamical system.
### Classical DMP
The classical discrete DMPs were first introduced by Ijspeert.  
A DMP for a single DoF trajectory y of a discrete movement (point-to-point) is defined by the following set of nonlinear differential equations:
$$
\tau\dot{z} = α_z (β_z (g − y) − z) + f (x)
$$
$$
\tau\dot{y} = z
$$
$$
\tau\dot{x} = \alpha_x x
$$
where $\tau$ = time modulation parameter , $\alpha, \beta$ sre the gain coefficient, $g$ is the attractor(goal) and $y,z$ are the governing equation in one dimension split into two single order system, and $x$ is the phase variable.  
$f(x)$ is chosen in such a manner that it is defines as the weighted linear combination of $N$ nonlinear Radial Basis Functions (RBFs) , which enables the robot to follow
any smooth trajectory from the initial position $y_0$ to the final
configuration $g$.
For each DOF the weight should be adjusted, so that the desired behivour is achieeved.  
For controlling a robotic system with more than one DoF, we will represent its own equation system, but sync them with a common phase equation.

