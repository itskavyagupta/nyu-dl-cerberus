# **NYU-DL-Cerberus**

Our project aims to create a ResNet model from scratch using less than 5 million parameters. 

Our model is a variant of the widely-implemented [ResNet model] (https://github.com/kuangliu/pytorch-cifar) that comprises basic building blocks called BasicBlocks, each consisting of two convolutional layers with batch normalization and ReLU activation. It consists of multiple layers of these blocks, with each of these block layers having the same channel size. We changed the ResNet() function so that it can create models of 3 block layers and 4 block layers. After experimenting with various model configs and hyperparameters, the final details of our model are as follows:

- B: [3, 5, 3]
- C: [64, 128, 256]
- F:  3x3
- K:  3x3
- P:  8x8
- optimizer: sgd
- Learning rate: 0.01
- Learning rate Cosine annealing with step decay

> Best Train Accuracy: **99.01%**
> Best Test Accuracy: **95.01%**

> Parameters: **4,918,602**

---

## **Documentation**

1. Project report can be found at [docs/project_report.pdf](https://github.com/itskavyagupta/NYU-DL-Cerberus/blob/main/docs/Report.pdf)
2. All Model Experiments using [WandB](https://api.wandb.ai/links/classical/vhpf97st)
3. Data Augmentation Strategy Experimentation using [WandB](https://api.wandb.ai/links/classical/r30pm7oh)

> This Project was part of graduate level Deep Learning course at New York University
