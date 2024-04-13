# **NYU-DL-Cerberus**

Our project aims to create a ResNet model from scratch using less than 5 million parameters. 

Our model is a variant of the ResNet model that comprises of basic building blocks called BasicBlocks, each consisting of two convolutional layers with batch normalization and ReLU activation. It consists of multiple layers of these blocks, with the number of blocks per layer specified by the num\_blocks parameter.

The final parameters and hyper parameters in our model are:
- Ci: [64, 128, 256]
- Fi: 3x3
- Ki: 3x3
- P: 8x8
- Blocks: [3, 5, 3]

> Best Accuracy: **95.01%**

> Parameters: **4,918,602**

---

## **Documentation**

1. Project report can be found at [docs/project_report.pdf](tbd)
2. Hyper parameter variations [Wandb](https://wandb.ai/classical/DL_All_Model_Experiments)

> This Project was part of graduate level Deep Learning course at New York University
