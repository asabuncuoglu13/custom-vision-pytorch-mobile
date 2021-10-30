# Custom Vision with PyTorch Mobile

This repo contains the code for training a custom classifier using transfer learning on [mobilenet-v3](https://pytorch.org/blog/torchvision-mobilenet-v3-implementation/) and using this model on PyTorch Mobile demo app.

We used the mobilenet-v3 pre-trained model as the base architecture for the custom classification task. We modified PyTorch's official Transfer Learning tutorial to train this custom model. Our modification includes a live data collection step, integrating the mobilenet-v3, and optimizing it for mobile devices. Then we updated PyTorch's official Android demo app with the latest build, deploy our model and define new tasks to test the model on the device.

**Notebook:** [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1AQWCBXmhccr4TbpYDXcLQhtG_JXQlawj?usp=sharing) or [📓 See the Notebook](./torch_transfer_learning_mobilenet3.ipynb)

**Android App:** [See the Code](./PyTorchDemoApp/) or [Download the APK]()


## Base

1. The Transfer Learning Code Basis: [PyTorch Official Tutorial](https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html)
2. Android Demo App Basis: [PyTorch Official Demo](https://github.com/pytorch/android-demo-app/tree/master/PyTorchDemoApp)
3. Chrome's T-Rex Runner: [@wayou's extracted code](https://github.com/wayou/t-rex-runner)


