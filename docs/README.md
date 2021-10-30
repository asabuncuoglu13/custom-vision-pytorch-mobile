In this tutorial and demo application, we will create a custom classification model using TorchVision’s pre-trained MobileNet-v3 and deploy this custom model to an Android device to control a simple game.

Utilizing custom vision models on mobile devices is a key practical use of AI. Such systems can help a visually-impaired person to understand the physical environment, a factory laborer to record the entries, or an environmental scientist to note the observations. In this work, I share the code and tutorial for developing high-performance/small-size custom models and using these models on Android devices. 

We used MobileNet-v3, which is released with TorchVision’s version 0.9. It is a series of new mobile-friendly models that can be used for classification, object detection, and semantic segmentation. The MobileNet architecture is designed for high performance using limited space and power. 

[Here](https://pytorch.org/blog/torchvision-mobilenet-v3-implementation/), you can see the detailed benchmarks in PyTorch’s post, between new and selected previous models. As you can see MobileNetV3-Large is a viable replacement of ResNet50 while sacrificing a bit of accuracy for a roughly 6 times speed-up.

To create our custom object classifier, we will freeze the weights for all of the network except that of the final fully connected layer. This last fully connected layer is replaced with a new one with random weights and only this layer is trained. In this approach, using only a few examples we can achieve ~0.95 accuracy depending on the dataset quality.

We updated [PyTorch’s official transfer learning tutorial](https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html) with MobileNet-v3 architecture and added interactive data collection and mobile optimization tasks to the same notebook.

Using the notebook, you can add new samples to your custom dataset. This kind of setup is especially useful for personal customized models such as having a custom accessibility issue.

After the training is complete, we optimized the code for mobile. With the latest Torch 1.9 release, you can use the .ptl format, but notice that .ptl is compatible with torch mobile 1.9’s Lite Interpreter.

Then, you can copy your custom model in the Android app’s assets folder. In our demo app’s assets folder, you will also see the updated .ptl versions of pre-trained models with ImageNet.

This Android demo application is a modified version of PyTorch’s demo app. You can follow our list of changes to adapt your own version. You can create games, applications, and services using your custom models. To keep things simple, we controlled Chrome’s T-Rex Runner game with our up/down classifier model. We controlled this web application by simulating key-press when the model recognizes the up and down categories.

In summary, we keep this work simple, so others can easily copy this repo and adapt their own custom applications, You can get more inspiration from Experiments with Google, PyTorch Mobile Demos, AllenAI Demos, and use computer vision to help others!
