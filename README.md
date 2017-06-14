
## Tnesorboard Installation and how to configure it with Keras
 
Tensorboard is a tool to visualise the nodes and training process of neural network. Basiclly, it helps to understand better how this black box -CNN- is working or if sometimes you stock somewhere, or your training is not improving then you can see the Tensorboard to find the issues. You can install Tensorboard using pip the python package manager:

```ruby
pip install Tensorboard
```
The following code, run for some number of epochs and it has received the data to feed into the ntework. 
s
```ruby
from keras.models import Sequential
from keras.layers import Dense, Activation
model = Sequential()
model.add(Dense(10, input_shape=(784,)))
model.add(Activation('softmax'))
model.compile(optimizer='sgd', loss='categorical_cross_entropy')
model.fit(x_train, y_train, verbose=1)
```
The question is that can understand from above code that trining is running well, well here Tensorboard can help solve this problem. For this you need to modify the code, first you need to import Tensorboard from callabcks class and added as an arugment to callackas parameter of fit function:

```ruby
from time import time
from keras.models import Sequential
from keras.layers import Dense, Activation
from keras.callbacks import TensorBoard
model = Sequential()
model.add(Dense(10, input_shape=(784,)))
model.add(Activation('softmax'))
model.compile(optimizer='sgd', loss='categorical_crossentropy')
tensorboard = TensorBoard(log_dir="logs/{}".format(time()))
model.fit(x_train, y_train, verbose=1, callbacks=[tensorboard])
```
No to monito the training process, you need to run the following line in commandline:
```ruby
tensorboard --logdir=logs/
```
After running the command, you will see webpage in your browser similar as blow:

![Image of Yaktocat](https://www.tensorflow.org/images/mnist_tensorboard.png)
