# **NYU-DL-Cerberus**

Our project aims to create a ResNet model from scratch using less than 5 million parameters. 


Our model is a variant of the widely-implemented [ResNet model](https://github.com/kuangliu/pytorch-cifar) that comprises basic building blocks called BasicBlocks, each consisting of two convolutional layers with batch normalization and ReLU activation. It consists of multiple layers of these blocks, with each of these block layers having the same channel size. We changed the ResNet() function so that it can create models of 3 block layers and 4 block layers. We created and trained multiple models which are variants of the above explained model implementation on the CIFAR − 10 dataset to classify images. Our best model achieves the test accuracy of 95.01% for **ResNet-24** with 4,918,602 parameters. After experimenting with various model configs and hyperparameters, the final details of our model are as follows:

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

| Model       | Params   | N (#Layers) | B (#Blocks) | C (#Channels)       | Log File Name                 |
|-------------|----------|-------------|-------------|---------------------|-------------------------------|
| ResNet-26   | 4771146  | 3           | 5, 4, 3     | 64, 128, 256        | dl-mini-resnet26.log          |
| ResNet-24   | 4918602  | 3           | 3, 5, 3     | 64, 128, 256        | dl-mini-proj-final.log        |
| ResNet-30   | 4919114  | 3           | 7, 4, 3     | 64, 128, 256        | dl-mini-resnet30.log          |
| ResNet-90   | 4947402  | 3           | 16, 16, 12  | 32, 64, 128         | dl-mini-resnet90.log          |
| ResNet-32   | 4754218  | 4           | 4, 4, 4, 3  | 32, 64, 128, 256    | dl-mini-resnet32.log          |
| ResNet-10   | 4903242  | 4           | 1, 1, 1, 1  | 64, 128, 256, 512   | dl-mini-resnet10.log          |
| ResNet-12   | 4977226  | 4           | 2, 1, 1, 1  | 64, 128, 256, 512   | dl-mini-resnet12.log          |
| ResNet-56   | 4989194  | 4           | 16, 4, 4, 3 | 32, 64, 128, 256    | dl-mini-resnet56.log          |
| ResNet-24   | 4918602  | 3           | 3, 5, 3     | 64, 128, 256        | dl-mini-proj-cutmix.log       |
| ResNet-24   | 4918602  | 3           | 3, 5, 3     | 64, 128, 256        | dl-mini-proj-cutout-mixup.log |


---

# **Process**
Apart from using transformations, we also used additional data augmentation techniques. The visualisations for the same are linked below. 

- Cutout: Masks square regions of input images, setting pixel values to zero during training. We used one 8x8 hole.

- Mixup: Blends pairs of input samples and labels to create synthetic samples. We set the parameter alpha to 0.5, skewing the distribution towards 0 and 1.

- Cutout and Mixup Combination: Integrating both techniques improves regularization and generalization performance, better than Mixup alone but not as good as Cutout.

- CutMix: Randomly selects patches from two images, blending them to create new mixed images. We used alpha to make the Beta distribution uniform across [0, 1], ensuring random mixing behavior.

In our model evaluation, we scrutinized 10 models with three different optimizers: AdaDelta, SGD, and AdaDelta with Gradient Clipping, chosen based on initial trials where Adam and AdaGrad yielded unsatisfactory results.

- SGD: Updates model parameters using gradients of the loss function.
- AdaDelta: Dynamically adjusts learning rate during training, eliminating the need for manual tuning.
- AdaDelta with Gradient Clipping: Addresses vanishing/exploding gradient issues by clipping larger gradients.

We experimented with learning rates of 0.1 and 0.01, alongside a learning rate decay strategy reducing the rate by a factor of 10 every 80 epochs, refining the model's optimization over time.

To prevent overfitting, we implemented annealing with a 50-epoch cycle, allowing periodic adjustments to the learning rate, promoting stable convergence and better generalization.

Additionally, we employed weight decay (0.0005) and momentum (0.9) to optimize each configuration, ensuring effective training and enhanced predictive capabilities.

---

## **Documentation**

1. Project report can be found at [docs/project_report.pdf](https://github.com/itskavyagupta/NYU-DL-Cerberus/blob/main/docs/Report.pdf)
2. All Model Experiments using [WandB](https://api.wandb.ai/links/classical/vhpf97st)
3. Data Augmentation Strategy Experimentation using [WandB](https://api.wandb.ai/links/classical/r30pm7oh)
4. Output logs for different and final configurations [logs](https://github.com/itskavyagupta/NYU-DL-Cerberus/tree/main/logs)

> This Project was part of graduate level Deep Learning course at New York University
