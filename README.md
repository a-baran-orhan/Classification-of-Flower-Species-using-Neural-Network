# Classification of Flower Species using Neural Network
 Implemented a single layer and convolutional neural network architecture to classify the examples in the Flower Species Dataset

| Experiment 	| Input Size 	| Model 	| Activation Function 	| Number of Layers 	| Hidden Layer Size 	| Learning Rate 	| Batch Size 	| Epoch 	| Accuracy(%) 	|
|------------	|------------	|:-----:	|---------------------	|------------------	|-------------------	|---------------	|------------	|-------	|-------------	|
| 1          	| 64x64x1    	| MLP   	| RELU                	| 3                	| 250               	| 0,1           	| 64         	| 3     	| 14,42       	|
| 2          	| 32x32x1    	| MLP   	| RELU                	| 3                	| 50                	| 0,01          	| 64         	| 3     	| 25,28       	|
| 3          	| 32x32x1    	| MLP   	| RELU                	| 4                	| 200-100           	| 0,001         	| 32         	| 3     	| 30,69       	|
| 4          	| 32z32x1    	| MLP   	| SIGMOID             	| 3                	| 250               	| 0,001         	| 16         	| 3     	| 30,88       	|
| 5          	| 32x32x1    	| MLP   	| RELU                	| 3                	| 250               	| 0,001         	| 16         	| 10    	| 32,67       	|
| 6          	| 64x64x3    	| CNN   	| RELU                	| 2                	| No hidden layer   	| 0,1           	| 64         	| 3     	| 16,71       	|
| 7          	| 32x32x3    	| CNN   	| SIGMOID             	| 4                	| 128-7             	| 0,001         	| 16         	| 3     	| 48,96       	|
| 8          	| 32x32x3    	| CNN   	| SIGMOID             	| 4                	| 64-7              	| 0,1           	| 16         	| 3     	| 14,20       	|

I tried to experience every possible combinations to get higher accuracies. 
Since I have limited computational power and limited ram for free usage of Colabs I limited the Epochs at 3. It would be better to try different epoch numbers but for this problem I interested in more layers, functions, learning rate effects. For the MLP interestingly our network gives better results for the lower resolutions.

There can be several reasons to get better accuracy for low image size in MLP.
- Reduced complexity: By using smaller images, make the model easier to train, as it has fewer parameters to optimize
- More efficient training: By using smaller images, model be able to fit more examples in a single batch, which can make training more efficient.
- Overfitting: Using larger images might result in overfitting, especially with limited data.

For calculating accuracies I add the each accuracy for epoch and take the average.
As you can see for the MLP accuracy is going higher every experiment since I tried to get better result each time. 
Comparing the CNN and MLP we get very bad result for the last experiment maybe because of the Learning rate. When lr=0,1 we also get bad accuracy for the MLP.

I understand that learning rate is more important than the batch sizes from above experiments.

Changing the batch size and hidden layer size with different activation function changes little amount of accuracy meanwhile increasing the hidden layer size with lower learning rate gives significant result for the experiment 2-3

Below figure is misclassified from model and I investigated the reasons behind the misclassifications in neural networks.

- Poor quality data: If the training data is of poor quality, it might be difficult for the CNN to learn accurate features and patterns. This can lead to misclassifications.

- Insufficient data: If the training data is not diverse enough or there is not enough of it, the CNN might not have learned enough about the different classes it is trying to classify. This can also lead to misclassifications. And I think our data is not big enough for the models to predict since there is many diversion of the flower and flower types. 

- I THINK main reason is Poorly designed architecture, If the CNN architecture is not well-suited to the task, it might struggle to learn the features and patterns needed to classify the images accurately.

Since my CNN is not pretrained or got from some research paper, it is created randomly. Maybe some CNN architecture for this spesific task give better results.

And other reason for misclassification is all the models are poorly designed having very few layer and neuron

For first figure below Unbalanced classes can be the reason for bellflower and sunflower misclassification. If the sunflower and bellflower classes are unbalanced in the data, the model might have difficulty learning to distinguish between them. This can lead to misclassifications.
