# Keras

## Installing Tensorboard
 
Tensorboard is a tool to visualise the nodes and training process of neural network. Basiclly, it helps to understand better how this black box -CNN- is working or if sometimes you stock somewhere, or your training is not improving then you can see the Tensorboard to find the issues. You can install Tensorboard using pip the python package manager:

```ruby
pip install Tensorboard
```
Collecting run data from your Keras program

With Tensorboard installed you can start collecting data from your Keras program. For example, if you have the following network defined:

```ruby
from keras.models import Sequential
from keras.layers import Dense, Activation
model = Sequential()
model.add(Dense(10, input_shape=(784,)))
model.add(Activation('softmax'))
model.compile(optimizer='sgd', loss='categorical_cross_entropy')
model.fit(x_train, y_train, verbose=1)
```
