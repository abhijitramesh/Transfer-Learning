# Transfer Learning

If we take a look at CNNs it has many layers and are really good at understanding patterns in Images. There are CNNs like Alex Net, Res Net, VGG etc.. which are trained on Image Net dataset which consist of millions of images and thousands of class. What if we can use the knowledge that these images have and apply it to our dataset. Remember ResNet, VGG etc.. where trained on high end GPU's for weeks and hence they are really accurate. Yes we can use the knowlege that these datasets have to train with out own dataset to get a very good model this process is called transfer learning.


#### Useful layers

If you have very good knowledge about CNNs you might be wondering how can we use data sets like VGG that is trained on Image Net to work with our dataset, well to begine with as we know a CNN concist of layers that are arranged in a hirarchy, it might contain convolutional and pooling layers, the first layer might be undertanding edges and shapes, the second might be looking for colors and so on. So these layers can be classified as feature extractors and they work for our usecase. We just have too customise the end layers of the network to work with our prediction for this we will remove the excisting one and implement our own which should work for us. One thing to note here is the success of our prediction depends upon how big our dataset is and how much similarity it shares with the imagenet dataset.


#### Fine tuning

Transfer learning is a very powerfull tool but depending upon the data that the network that it was trained with initaly and depending upon the dataset that we currently have we might have to decide which part of the model we have to customize and which part we need to freeze weights and train the model again or even we might have to retrain the whole model with a new dataset this process is called Fine tuning.

Depending upon different cases we might have to follow different statery to do our tranfser learning

_Case 1_ : The data we have is small but it is similat to that of which the inital dataset was trained.

* Silce of the fully connected layers of the model at the end.
* Create new fully connected layers that matches the number of classes that we want in out network.
* randomize the weights for this new fully connected network and freeze the weights for the pre-trained network.
* train the network and update the weights for the fully connected layers part.

_Case 2_ : The new dataset is small but it is different from the once the model was intiallt trained on.

* Silce of all the layers towards the begining of the network but preserving some of it.
* Create new fully connected layers that matches the number of classes that we want in out network.
* randomize the weights for the new fully connected network and freeze the weights for the pre-trained network.
* train the network and update the weights for the new fully connected network.

_Case 3_ : New dataset is large but similar to the once that the model was trained initally.

* Slice of the fully connected layers to the end of the network.
* Create new fully connected network that matches the number of classes that we want in out network.
* randomize the weights for the fully connected network.
* initialise the weights for the rest of the netowrk.
* retrain the entire network.

_Case 4_ : New dataset is large but different from the intial mode.

* Slice of the end of the network.
* Add new fully connected layers to the end of the network
* Randomize the weights for the entire network and retrain the whole mode.

*Alternatively* we can follow the same steps for _Case 3_

[Click here](https://github.com/abhijitramesh/Transfer-Learning/blob/master/Transfer_Learning_Exercise.ipynb) to find about transfer learning in flower dataset using VGG 16.