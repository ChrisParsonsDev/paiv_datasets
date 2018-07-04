# PowerAI Vision demo with Beer

## Accessing PowerAI Vision
It is easy (and free) to get a running instance of AI Vision on the SuperVessel service. You can sign up and start using this immediately at: [https://ny1.ptopenlab.com/AIVision/index.html](https://ny1.ptopenlab.com/AIVision/index.html).
There are some limitations to this service, so it is advised to use it only for simple demos and test workloads, and not for any production use cases. For instance, there are limits on the amount of data that you can work with, and many of the APIs generated will be time limited.

## Building a classification model
In advance, create a new data set for classification. In that data set, create the following categories:
* Becks
* Corona
* Guinness
* Peroni
* San Miguel
* Stella Artois

Upload the contents of each of the relevant folders for each category. There are a few hundred images of bottles of each type of beer, with four copies of each picture, as the images have been rotated to increase the data set size, and therefore the accuracy of the final model. This is one method of data augmentation. Other methods are also possible, and these processes will be automated and included in future releases of AI Vision.
During the event, show the data set and start a training model for classification using this data set. Use the time this will take (~5 minutes) to explain what is going on under the covers:
* The images are resized to ensure consistency.
* The images are split into train and test data sets.
* The model is primed with random weights and biases.
* The model is trained using the train subset of images multiple times.
* At regular intervals, the result is tested against the test data set, and corrections are made in the next training iterations.
* After the total number of iterations, we get a model with the lowest loss, and highest accuracy.

Then you can show how simple it is to convert that trained model into a webAPI, and start testing images to show the result. You can test with the provided images for Becks, Guinness, and San Miguel (which are not in the training set), or you can provide your own images. You can also test an image of a bottle of beer that is not included in the data set, to show that this will not be correctly classified as the model has not been trained with that brand.

## Implementation
This data set has been used to train a model which is the back end service for a beer recognition application. This is a mobile app, available for iOS and Android, and is called BeerAI. This can be installed on a mobile device, and used to demonstrate how the models from AI Vision can be implemented into a real sorld application quickly and easily.
There are some limitations to the application, primarily that it has only been trained on the 6 bottles of beer in the training data set.
