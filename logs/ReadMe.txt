**Runtime Logs**


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

