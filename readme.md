# Transfer Learning

If we take a look at CNNs it has many layers and are really good at understanding patterns in Images. There are CNNs like Alex Net, Res Net, VGG etc.. which are trained on Image Net dataset which consist of millions of images and thousands of class. What if we can use the knowledge that these images have and apply it to our dataset. Remember ResNet, VGG etc.. where trained on high end GPU's for weeks and hence they are really accurate. Yes we can use the knowlege that these datasets have to train with out own dataset to get a very good model this process is called transfer learning.


#### Useful layers

If you have very good knowledge about CNNs you might be wondering how can we use data sets like VGG that is trained on Image Net to work with our dataset, well to begine with as we know a CNN concist of layers that are arranged in a hirarchy, it might contain convolutional and pooling layers, the first layer might be undertanding edges and shapes, the second might be looking for colors and so on. So these layers can be classified as feature extractors and they work for our usecase. We just have too customise the end layers of the network to work with our prediction for this we will remove the excisting one and implement our own which should work for us. One thing to note here is the success of our prediction depends upon how big our dataset is and how much similarity it shares with the imagenet dataset.
