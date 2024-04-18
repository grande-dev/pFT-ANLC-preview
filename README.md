# Passive Fault Tolerant-Augmented Neural Lyapunov Control  

This repository contains the comparison of different control laws designed to stabilise an inverted pendulum system with a redundant actuators set. A new Fault Tolerant Control method named *passive Fault Tolerant-Augmented Neural Lyapunov Control* is devised: the control law is synthesised via an automatic learning approach, with the closed-loop stability guaranteed via a Control Lyapunov Function. The correctness of the solution over the reals is *formally certified* via formal methods. 
    
The associated publication is available at this [link](https://ieeexplore.ieee.org/document/10383378).  
   

## 1) Example: redundant inverted pendulum

The redundant inverted pendulum system used in the manuscript is illustrated hereby:  
<p align="center">
    <img src="https://github.com/grande-dev/pFT-ANLC-preview/blob/master/results/inverted_pendulum_redundant.png" width=20% height=20%>
</p>

with its dynamics described as follows:
  
$$
\begin{cases}
\dot{x}_1 = x_2 \\
\dot{x}_2 = (m L^2)^{-1}(m g L \sin{x_1} - b x_2 + h_1 u_1 - h_2 u_2 )\\
\end{cases}
$$

where $u_1$ and $u_2$ represent two control signals, and $h_1$ and $h_2$ the health status of the actuators. 


In this test case, the aim is to stabilise the pendulum in its upright position, starting from the configuration with the pendulum hanging down and no angular velocity. Hereby, the comparison of three control laws is provided: a *Linear Quadratic Regulator* (LQR), a *vanilla Augmented Neural Lyapunov Control* (vANLC) and a *passive Fault Tolerant-Augmented Neural Lyapunov Control* (pFT-ANLC). 

### Nominal case
As expected, all the control laws work correctly in the nominal scenario (no faults):
  
LQR                        |  vANLC                    | pFT-ANLC
:-------------------------:|:-------------------------:|:-------------------------:
![](results/animations/animationLQR(nominal).gif) | ![](results/animations/animationvANLC(nominal).gif) | ![](results/animations/animationpFT-ANLC(nominal).gif)


### Fault affecting the first actuator
The control laws might also work when a fault occurr, e.g. in the case of fault on the first actuator as shown hereby, albeit there is no theoretical a-priori guarantee that they are capable to do so:  
  
LQR                        |  vANLC                    | pFT-ANLC
:-------------------------:|:-------------------------:|:-------------------------:
![](results/animations/animationLQR(fault_1).gif) | ![](results/animations/animationvANLC(fault_1).gif) | ![](results/animations/animationpFT-ANLC(fault_1).gif)



### Fault affecting the second actuator
In this case study, when a fault is injected on the second actuator, both the LQR and the vANLC fail to drive the pendulum towards the desired equilibrium position, whilst the pFT-ANLC retains the stabilising capability:    
  
LQR                        |  vANLC                    | pFT-ANLC
:-------------------------:|:-------------------------:|:-------------------------:
![](results/animations/animationLQR(fault_2).gif) | ![](results/animations/animationvANLC(fault_2).gif) | ![](results/animations/animationpFT-ANLC(fault_2).gif)


## 2) Code
The code used to generate the results of this publication will soon be released open-source in a dedicated follow-up publication. The software tool will be available within the following repository [Passive-Fault-Tolerant-Augmented-Neural-Lyapunov-Control](https://github.com/grande-dev/pFT-ANLC).  
Stay tuned.  
  

## 3) Contacts
The authors can be contacted for feedback, clarifications or requests of support at:  
`grande.rdev@gmail.com`  
  

## 4) Reference

The related manuscript is available within the Proceedings of the IEEE CDC Conference as:  
  
```bibtex
@inproceedings{grande2023systematic,
  title={Systematic Synthesis of Passive Fault-Tolerant Augmented Neural Lyapunov Control Laws for Nonlinear Systems},
  author={Grande, Davide and Fenucci, Davide and Peruffo, Andrea and Anderlini, Enrico and Phillips, Alexander B and Thomas, Giles and Salavasidis, Georgios},
  booktitle={2023 62nd IEEE Conference on Decision and Control (CDC)},
  pages={5851--5856},
  year={2023},
  organization={IEEE}
}
```


