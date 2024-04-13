# **NYU-DL-Cerberus**

Our project aims to create a ResNet model from scratch using less than 5 million parameters. 

Our model is a variant of the widely-implemented [ResNet model](https://github.com/kuangliu/pytorch-cifar) that comprises basic building blocks called BasicBlocks, each consisting of two convolutional layers with batch normalization and ReLU activation. It consists of multiple layers of these blocks, with each of these block layers having the same channel size. We changed the ResNet() function so that it can create models of 3 block layers and 4 block layers. After experimenting with various model configs and hyperparameters, the final details of our model are as follows:

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
**Logs**

This file contains the logs for each of the configuration that was run to finalise on the best model for the project. 

| Model       | Params   | N (#Layers) | B (#Blocks) | C (#Channels)       | Log File Name          |
|-------------|----------|-------------|-------------|---------------------|------------------------|
| ResNet-26   | 4771146  | 3           | 5, 4, 3     | 64, 128, 256        | dl-mini-resnet26.log   |
| ResNet-24   | 4918602  | 3           | 3, 5, 3     | 64, 128, 256        | dl-mini-proj-final.log |
| ResNet-30   | 4919114  | 3           | 7, 4, 3     | 64, 128, 256        | dl-mini-resnet30.log   |
| ResNet-90   | 4947402  | 3           | 16, 16, 12  | 32, 64, 128         | dl-mini-resnet90.log   |
| ResNet-32   | 4754218  | 4           | 4, 4, 4, 3  | 32, 64, 128, 256    | dl-mini-resnet32.log   |
| ResNet-10   | 4903242  | 4           | 1, 1, 1, 1  | 64, 128, 256, 512   | dl-mini-resnet10.log   |
| ResNet-12   | 4977226  | 4           | 2, 1, 1, 1  | 64, 128, 256, 512   | dl-mini-resnet12.log   |
| ResNet-56   | 4989194  | 4           | 16, 4, 4, 3 | 32, 64, 128, 256    | dl-mini-resnet56.log   |


---

## **Documentation**

1. Project report can be found at [docs/project_report.pdf](https://github.com/itskavyagupta/NYU-DL-Cerberus/blob/main/docs/Report.pdf)
2. All Model Experiments using [WandB](https://api.wandb.ai/links/classical/vhpf97st)
3. Data Augmentation Strategy Experimentation using [WandB](https://api.wandb.ai/links/classical/r30pm7oh)
4. Output logs for different and final configurations [logs](https://github.com/itskavyagupta/NYU-DL-Cerberus/tree/main/logs)

> This Project was part of graduate level Deep Learning course at New York University
