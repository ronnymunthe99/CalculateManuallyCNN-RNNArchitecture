> ## Calculate Manually CNN-RNN Architecture Using Excel
Image classification is the process of grouping pixels in digital images into certain categories based on certain features possessed by these pixels. 
* Calculate manually image classification using CNN to perform feature extraction and RNN to perform classification
* Transfer learning using the Inception v3 Model is used in performing feature extraction (Encoder)
* GRU layer is used in performing classification

>> ### Inception v3 Model
Inception v3 is an image recognition model that has been shown to attain greater than 78.1% accuracy on the ImageNet dataset. To perform transfer learning keras is used [Keras Inception v3 Model](https://keras.io/api/applications/inceptionv3/). In the first layer, the Inception v3 model extracts basic features from the image using convolution. Convolution is a mathematical operation used to extract spatial features from images using kernels or filters. After the basic features are extracted, the Inception v3 model uses a layer called "inception module" to extract features at a larger scale. Inception modules consist of multiple convolutions that are applied at different scales and then summed back up to form more complex features. 

With all layers, manual calculations will be carried out layer by layer
>>> #### Architecture Inception v3 

| No | Code | Operation |  
|-----------|:-----------:|-----------:|  
| 1.|	input = keras.Input(shape=(224,224,3))	|Input|
| 2.|	x = keras.layers.Conv2D(64,(3,3),strides=(2,2))	|Konvolusi|
| 3.|	x = keras.layers.BatchNormalization()(x)	|Batch Normalization|
| 4.|	x = keras.layers.Activation(‘relu’)(x)	|ReLU|
| 5.|	pool = keras.layers.AveragePooling2D((3,3), strides=(1,1), padding=’same’)(x)	|Average-Pooling|
| 6.| conv1= = keras.layers.Conv2D(32,(1,1),padding=’same’)	|Konvolusi|
| 7.|	conv1 = keras.layers.BatchNormalization()	|Batch Normalization|
| 8.|	conv1 = keras.layers.Activation(‘relu’)	|ReLU|
| 9.|	conv2 = keras.layers.Conv2D(64,(1,1),padding=’same’)	|Konvolusi|
| 10.| conv2 = keras.layers.BatchNormalization()	|Batch Normalization|
| 11.| conv2 = keras.layers.Activation(‘relu’)	|ReLU|
| 12.| conv3 = keras.layers.Conv2D(96,(1,1),padding=’same’)	|Konvolusi|
| 13.| conv3 = keras.layers.BatchNormalization()	|Batch Normalization|
| 14.|	conv3 = keras.layers.Activation(‘relu’)	|ReLU|
| 15.|conv4 = keras.layers.Conv2D(48,(3,3),padding=’same’)	|Konvolusi|
| 16.|conv4 = keras.layers.BatchNormalization()	|Batch Normalization|
| 17.|conv4 = keras.layers.Activation(‘relu’)	|ReLU|
| 18.|	conv5 = keras.layers.Conv2D(64,(1,1),padding=’same’)	|Konvolusi|
| 19.|	conv5 = keras.layers.BatchNormalization()	|Batch Normalization|
| 20.|	conv5 = keras.layers.Activation(‘relu’)	|ReLU|
| 21.|	conv6 = keras.layers.Conv2D(64,(3,3))	|Konvolusi|
| 22.|	conv6 = keras.layers.BatchNormalization()	|Batch Normalization|
| 23.|	conv6 = keras.layers.Activation(‘relu’)	|ReLU|
| 24.|	conv7 = keras.layers.Conv2D(64,(1,1),padding=’same’)	|Konvolusi|
| 25.|	conv7 = keras.layers.BatchNormalization()	|Batch Normalization|
| 26.|	conv7 = keras.layers.Activation(‘relu’)	|ReLU|
| 27.|	Output=keras.layers.Concatenate ([conv1,conv4,conv6,conv8])	|Konkatenasi|
| 28.|	Output=keras.layers.Flatten()	|Flatten|
| 29.|	Output=keras.layers.Dense(3,activation=’softmax’)	|Dense|

>> ## Gated Recurrent Unit (GRU)
Gated recurrent units (GRUs) are a gating mechanism in recurrent neural networks.The GRU is like a long short-term memory (LSTM) with a forget gate, but has fewer parameters than LSTM, as it lacks an output gate. GRU's performance on certain tasks of polyphonic music modeling, speech signal modeling and natural language processing was found to be similar to that of LSTM.

Architecture Gated Recurrent Unit (GRU)
![gru](https://user-images.githubusercontent.com/93511026/221629474-a61f3510-5f01-4107-99b8-d93b0579c017.png)

