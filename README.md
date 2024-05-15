# Image-generation-

Experiments
❖ Model 1 : Plain LSTM
❖ Model 2 : CNN + LSTM
❖ Model 3 : CNN + LSTM + hyperparameter tuning
❖ Model 4 : CNN + LSTM + hyperparameter tuning + Regularisation



Model 1
❖ Activation ‘ReLU’ is used in the first dense layer.
❖ Activation ‘Sigmoid’ is used in the second dense
layer.
❖ While training this model we directly used the
data that has been converted into sequences
instead of splitting it.
❖ Epochs = 100, batch_size = 32
❖ Loss = 0.0793

Model: "sequential"
_________________________________________________________________
Layer (type) Output Shape Param #
=================================================================
lstm (LSTM) (None, None, 256) 201589760
dense (Dense) (None, None, 256) 65792
dense_1 (Dense) (None, None, 196608) 50528256
reshape (Reshape) (None, 196608) 0
=================================================================
Total params: 252,183,808
Trainable params: 252,183,808
Non-trainable params: 0
_________________________________________________________________


Model 2
❖ In this model I have used CNN first and then
LSTM.
❖ Added additional LSTM layers and Dense layers.
❖ Learning rate = 0.0001
❖ Epochs = 100, batch_size = 64
❖ Loss = 0.2811, Val_loss = 0.2792

Generated image
Model: "sequential"
_________________________________________________________________
Layer (type) Output Shape Param #
=================================================================
conv2d (Conv2D) (None, 256, 256, 64) 1792
max_pooling2d (MaxPooling2D (None, 128, 128, 64) 0
)
conv2d_1 (Conv2D) (None, 128, 128, 128) 73856
max_pooling2d_1 (MaxPooling (None, 64, 64, 128) 0
2D)
conv2d_2 (Conv2D) (None, 64, 64, 32) 36896
max_pooling2d_2 (MaxPooling (None, 32, 32, 32) 0
2D)
conv2d_3 (Conv2D) (None, 32, 32, 64) 18496
max_pooling2d_3 (MaxPooling (None, 16, 16, 64) 0
2D)
flatten (Flatten) (None, 16384) 0
...
Total params: 68,487,904
Trainable params: 68,487,904
Non-trainable params: 0


Model 3
Added additional CNN layers and LSTM layers
with dropout rate = 0.4.
❖ Learning rate = 0.0001, epochs = 100, batch_size = 32
❖ Loss = 0.0393, Val_loss = 0.0368

Generated image
Model: "sequential_1"
_________________________________________________________________
Layer (type) Output Shape Param #
=================================================================
conv2d_4 (Conv2D) (None, 256, 256, 64) 1792
max_pooling2d_4 (MaxPooling (None, 128, 128, 64) 0
2D)
conv2d_5 (Conv2D) (None, 128, 128, 128) 73856
max_pooling2d_5 (MaxPooling (None, 64, 64, 128) 0
2D)
conv2d_6 (Conv2D) (None, 64, 64, 32) 36896
max_pooling2d_6 (MaxPooling (None, 32, 32, 32) 0
2D)
conv2d_7 (Conv2D) (None, 32, 32, 64) 18496
max_pooling2d_7 (MaxPooling (None, 16, 16, 64) 0
2D)
flatten_1 (Flatten) (None, 16384) 0
...
Total params: 69,668,576
Trainable params: 69,668,576
Non-trainable params: 0
_________________________________________________________________


Model 4
❖ Added l2 regularisation.
❖ With dropout rate = 0.3
❖ Epochs = 250, batch_size = 32
❖ Learning rate = 0.0001
❖ Loss = 0.0798, Val_loss = 0.0767

Generated image
Model: "model"
_________________________________________________________________
Layer (type) Output Shape Param #
=================================================================
input_1 (InputLayer) [(None, 256, 256, 3)] 0
conv2d (Conv2D) (None, 256, 256, 64) 1792
max_pooling2d (MaxPooling2D (None, 128, 128, 64) 0
)
conv2d_1 (Conv2D) (None, 128, 128, 128) 73856
max_pooling2d_1 (MaxPooling (None, 64, 64, 128) 0
2D)
conv2d_2 (Conv2D) (None, 64, 64, 32) 36896
max_pooling2d_2 (MaxPooling (None, 32, 32, 32) 0
2D)
conv2d_3 (Conv2D) (None, 32, 32, 64) 18496
max_pooling2d_3 (MaxPooling (None, 16, 16, 64) 0
2D)
...
Total params: 69,668,576
Trainable params: 69,668,576
Non-trainable params: 0
_________________________________________________________________
