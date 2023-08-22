# Passive Fault Tolerant-Augmented Neural Lyapunov Control  

This repository contains the results of different control laws designed to stabilise an inverted pendulum with a redundant actuators set.
  
The redundant inverted pendulum system is illustrated hereby:  
<p align="center">
    <img src="https://github.com/grande-dev/pFT-ANLC/blob/master/results/inverted_pendulum_redundant.png" width=20% height=20%>
</p>

with its dynamics described as follows:

$$
\begin{cases}
\dot{x}_1 = x_2 \\
\dot{x}_2 = (m L^2)^{-1}(m g L \sin{x_1} - b x_2 + h_1 u_1 - h_2 u_2 )\\
\end{cases}
$$

where $u_1$ and $u_2$ represents two control signals, and $h_1$ and $h_2$ the health status of the actuators.

## 1) Redundant Inverted Pendulum results
Hereby the comparison of three control laws: a *Linear Quadratic Regulator* (LQR), a *vanilla Augmented Neural Lyapunov Control* (vANLC) and a *passive Fault Tolerant-Augmented Neural Lyapunov Control* (pFT-ANLC). 

### Nominal case
As expected, all the control law work in the nominal scenario (no faults):


LQR                        |  vANLC                    | pFT-ANLC
:-------------------------:|:-------------------------:|:-------------------------:
![](results/animations/animationLQR(nominal).gif) | ![](results/animations/animationvANLC(nominal).gif) | ![](results/animations/animationpFT-ANLC(nominal).gif)


### Fault affecting the first actuator
LQR                        |  vANLC                    | pFT-ANLC
:-------------------------:|:-------------------------:|:-------------------------:
![](results/animations/animationLQR(fault_1).gif) | ![](results/animations/animationvANLC(fault_1).gif) | ![](results/animations/animationpFT-ANLC(fault_1).gif)



### Fault affecting the second actuator
LQR                        |  vANLC                    | pFT-ANLC
:-------------------------:|:-------------------------:|:-------------------------:
![](results/animations/animationLQR(fault_2).gif) | ![](results/animations/animationvANLC(fault_2).gif) | ![](results/animations/animationpFT-ANLC(fault_2).gif)


## 2) Code
The code used to generate the results of this publication will soon be released open-source. Stay tuned.


## 3) Reference

The related manuscript will be available in the Proceedings of the IEEE CDC Conference (estimated date: January 2024).  
  
```bibtex
@inproceedings{
    title={Systematic synthesis of passive Fault-Tolerant Augmented Neural Lyapunov Control laws for overactuated systems},
    author={Davide Grande, Davide Fenucci, Andrea Peruffo, Enrico Anderlini, Alexander B. Phillips, Giles Thomas, Georgios Salavasidis},
    booktitle={62nd IEEE Conference on Decision and Control},
    year={2023}
}
```


