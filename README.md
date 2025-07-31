This is the repository for the "Learning when the PDE is wrong" paper. The repository contains 2 main experiments:

## Experiment 1:
The experimental setup is outlined in Section 6.2 and Figures 3 and 4. The code is provided in "Experiment 1 (Fig 3, 4).ipynb". Results are provided in the corresponding ".png" files. In particular, a visualization of the prediction as a consequence of solving the transformed problem is given, as requested by Reviewer 3. Note that the loss curves shown differ slightly from those in the paper, only because the simulations were run for fewer iterations as a result of time constraints.

## Experiment 2:
This experiment is new, in accordance with the Reviewers' request. This experiment consistutes a **time-dependent, nonlinear PDE** and involves thousands of datapoints, in order to demonstrate the generality and scalability of the proposed method. In this experiment, we study Burgers' equation

$$\frac{\partial u}{\partial t} + u\frac{\partial u}{\partial x} = \nu \frac{\partial^2 u}{\partial x^2}$$

for fixed $\nu=0.01/\pi$. This is a very common PDE studied by many PINN papers, in accordance with the Reviewers' request.

The task we consider is the following: We generate 1,000 datapoints from the solution to the equation on the domain $(x,t)\in[-1,1]\times[0,1]$ (the initial and boundary conditions are sin(x) and 0, respectively), and perturb them by some amount of noise. This is an extremely common setup in PINN papers.

After this, we test the consistency of these noisy datapoints with the given equation using our method. 
