## DeepDetect : Open Source Deep Learning Server & API

[![Join the chat at https://gitter.im/beniz/deepdetect](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/beniz/deepdetect?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) [![Build Status](https://travis-ci.org/beniz/deepdetect.png)](https://travis-ci.org/beniz/deepdetect)

DeepDetect (http://www.deepdetect.com/) is a machine learning API and server written in C++11. It makes state of the art machine learning easy to work with and integrate into existing applications.

DeepDetect relies on external machine learning libraries through a very generic and flexible API. At the moment it has support for:

- the deep learning library [Caffe](https://github.com/BVLC/caffe)
- distributed gradient boosting library [XGBoost](https://github.com/dmlc/xgboost)
- the deep learning and other usages library [Tensorflow](https://tensorflow.org)
- clustering with [T-SNE](https://github.com/DmitryUlyanov/Multicore-TSNE)

##### Examples

- List of examples, from MLP for data, text, multi-target regression to CNN and GoogleNet, finetuning, etc...:
http://www.deepdetect.com/overview/examples/

##### Models

|                          | Caffe | Tensorflow | Source        | Top-1 Accuracy (ImageNet) |
|--------------------------|-------|------------|---------------|---------------------------|
| AlexNet                  | Y     | N          | BVLC          |          57.1%                 |
| SqueezeNet               | Y     | N          | DeepScale              |       59.5%                    | 
| Inception v1 / GoogleNet | [Y](https://deepdetect.com/models/ggnet/bvlc_googlenet.caffemodel)     | [Y](https://deepdetect.com/models/tf/inception_v1.pb)          | BVLC / Google |             67.9%              |
| Inception v2             | N     | [Y](https://deepdetect.com/models/tf/inception_v2.pb)          | Google        |     72.2%                      |
| Inception v3             | N     | [Y](https://deepdetect.com/models/tf/inception_v3.pb)          | Google        |         76.9%                  |
| Inception v4             | N     | [Y](https://deepdetect.com/models/tf/inception_v4.pb)          | Google        |         80.2%                  |
| ResNet 50                | [Y](https://deepdetect.com/models/resnet/ResNet-50-model.caffemodel)     | [Y](https://deepdetect.com/models/tf/resnet_v1_50/resnet_v1_50.pb)          | MSR           |      75.3%                     |
| ResNet 101               | [Y](https://deepdetect.com/models/resnet/ResNet-101-model.caffemodel)     | [Y](https://deepdetect.com/models/tf/resnet_v1_101/resnet_v1_101.pb)          | MSR           |        76.4%                   |
| ResNet 152               | [Y](https://deepdetect.com/models/resnet/ResNet-152-model.caffemodel)     | [Y](https://deepdetect.com/models/tf/resnet_v1_152/resnet_v1_152.pb)         | MSR           |               77%            |
| Inception-ResNet-v2      | N     | [Y](https://deepdetect.com/models/tf/inception_resnet_v2.pb)          | Google        |       79.79%                    |
| VGG-16                   | [Y](https://deepdetect.com/models/vgg_16/VGG_ILSVRC_16_layers.caffemodel)     | [Y](https://deepdetect.com/models/tf/vgg_16/vgg_16.pb)          | Oxford        |               70.5%            |
| VGG-19                   | [Y](https://deepdetect.com/models/vgg_19/VGG_ILSVRC_19_layers.caffemodel)     | [Y](https://deepdetect.com/models/tf/vgg_19/vgg_19.pb)          | Oxford        |               71.3%            |
| ResNext 50                | [Y](https://deepdetect.com/models/resnext/resnext_50)     | N          | https://github.com/terrychenism/ResNeXt           |      76.9%                     |
| ResNext 101                | [Y](https://deepdetect.com/models/resnext/resnext_101)     | N          | https://github.com/terrychenism/ResNeXt           |      77.9%                     |
| ResNext 152               | [Y](https://deepdetect.com/models/resnext/resnext_152)     | N          | https://github.com/terrychenism/ResNeXt           |      78.7%                     |
| DenseNet-121                   | [Y](https://deepdetect.com/models/densenet/densenet_121_32/)     | N          | https://github.com/shicai/DenseNet-Caffe        |               74.9%            |
| DenseNet-161                   | [Y](https://deepdetect.com/models/densenet/densenet_161_48/)     | N          | https://github.com/shicai/DenseNet-Caffe        |               77.6%            |
| DenseNet-169                   | [Y](https://deepdetect.com/models/densenet/densenet_169_32/)     | N          | https://github.com/shicai/DenseNet-Caffe        |               76.1%            |
| DenseNet-201                   | [Y](https://deepdetect.com/models/densenet/densenet_201_32/)     | N          | https://github.com/shicai/DenseNet-Caffe        |               77.3%            |
| SE-BN-Inception                   | [Y](https://deepdetect.com/models/senets/se_bn_inception/)     | N          | https://github.com/hujie-frank/SENet        |               76.38%            |
| SE-ResNet-50                   | [Y](https://deepdetect.com/models/senets/se_resnet_50/)     | N          | https://github.com/hujie-frank/SENet        |               77.63%            |
| SE-ResNet-101                   | [Y](https://deepdetect.com/models/senets/se_resnet_101/)     | N          | https://github.com/hujie-frank/SENet        |               78.25%            |
| SE-ResNet-152                   | [Y](https://deepdetect.com/models/senets/se_resnet_152/)     | N          | https://github.com/hujie-frank/SENet        |               78.66%            |
| SE-ResNext-50                   | [Y](https://deepdetect.com/models/senets/se_resnext_50/)     | N          | https://github.com/hujie-frank/SENet        |               79.03%            |
| SE-ResNext-101                   | [Y](https://deepdetect.com/models/senets/se_resnext_101/)     | N          | https://github.com/hujie-frank/SENet        |               80.19%            |
| SENet                   | [Y](https://deepdetect.com/models/senets/se_net/)     | N          | https://github.com/hujie-frank/SENet        |               81.32%            |
| VOC0712 (object detection) | [Y](https://deepdetect.com/models/voc0712_dd.tar.gz) | N | https://github.com/weiliu89/caffe/tree/ssd | 71.2 mAP |

More models:

- List of free, even for commercial use, deep neural nets for image classification, and character-based convolutional nets for text classification: http://www.deepdetect.com/applications/list_models/

#### Templates

DeepDetect comes with a built-in system of neural network templates (Caffe backend only at the moment). This allows the creation of custom networks based on recognized architectures, for images, text and data, and with much simplicity.

Usage:
- specify `template` to use, from `mlp`, `convnet` and `resnet`
- specify the architecture with the `layers` parameter:
  - for `mlp`, e.g. `[300,100,10]`
  - for `convnet`, e.g. `["1CR64","1CR128","2CR256","1024","512"], where the main pattern is `xCRy` where `y` is the number of outputs (feature maps), `CR` stands for Convolution + Activation (with `relu` as default), and `x` specifies the number of chained `CR` blocks without pooling. Pooling is applied between all `xCRy`
- for `resnets`:
   - with images, e.g. `["Res50"]` where the main pattern is `ResX` with X the depth of the Resnet
   - with character-based models (text), use the `xCRy` pattern of convnets instead, with the main difference that `x` now specifies the number of chained `CR` blocks within a resnet block
   - for Resnets applied to CSV or SVM (sparse data), use the `mlp` pattern. In this latter case, at the moment, the `resnet` is built with blocks made of two layers for each specified layer after the first one. Here is an example: `[300,100,10]` means that a first hidden layer of size `300` is applied followed by a `resnet` block made of two `100` fully connected layer, and another block of two `10` fully connected layers. This is subjected to future changes and more control.

### Authors
DeepDetect is designed and implemented by Emmanuel Benazera <beniz@droidnik.fr>.
