# Deep Generative Replay 
### Mimicking Human Continual Learning in a Neural Network

A project built around the framework proposed in: [Continual Learning with Deep Generative Replay](https://arxiv.org/pdf/1705.08690.pdf). The goal of this approach is to develop a single model that can achieve high accuracy on two independent tasks.



In this project, the first task is image classification on the MNIST dataset and the second task is image classification on the SVHN (Street View House Numbers) dataset.

A full breakdown of this project, how it works, and the intuition behind it is available in the [article](https://aahaanmaini.medium.com/mimicking-human-continual-learning-in-a-neural-network-c15e1ae11d70)

## Pipeline
First Scholar (MNIST Classification):
1. Train the Generator on the MNIST dataset &rarr; `mnist_generator.ipynb`
2. Load the trained Generator to output 30k fake MNIST images &rarr; `generated_mnist_dataset.ipynb`
3. Train the Solver on the MNIST dataset &rarr; `mnist_solver.ipynb`
4. Use the trained Solver to output image labels for the 30k fake MNIST images &rarr; `mnist_solver.ipynb`

Second Scholar (SHVN + MNIST Classification):  
1. Train the Generator, 50% on the SHVN dataset and 50% on the 30k fake MNIST images &rarr; `shvn_generator.ipynb`
2. Train the Solver, 50% on the SHVN dataset and 50% on the fake MNIST dataset (images + labels) &rarr; `shvn_solver.ipynb`

## Results
The final CNN (Second Solver) achieved an accuracy of about 90% when tested on both MNIST and SHVN images. 
