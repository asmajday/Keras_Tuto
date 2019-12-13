<a href="https://keras.io/"><img src="https://www.actuia.com/wp-content/uploads/2018/05/keras.png" title="Keras" alt="Keras"></a>

# Keras_Tuto

> In this tutorial, you will discover how to create your first deep learning neural network model in Python using Keras.

> Keras, tensorflow, neural network, AI, deep learning.

**The steps you are going to cover in this tutorial are as follows:**

- Load Data
- Define Keras Model
- Compile Keras Model
- Fit Keras Model
- Evaluate Keras Model
- Make a Prediction

***Requierements***

- python 3.6.5
- keras 2.3.1
- tensorflow 2.0.0
- numpy 1.17.4

## Load Data
In this Keras tutorial, we are going to use the Pima Indians onset of diabetes dataset.
The dataset us available from <a href="https://raw.githubusercontent.com/jbrownlee/Datasets/master/pima-indians-diabetes.data.csv">here</a>: 
```python

# load the dataset
dataset = loadtxt('pima-indians-diabetes.csv', delimiter=',')
```

---

## Define Keras Model
In this Keras Tutorial, we are going to define a sequence Model of layers.
```python
# define the keras model
model = Sequential()
model.add(Dense(12, input_dim=8, activation='relu'))
model.add(Dense(8, activation='relu'))
model.add(Dense(1, activation='sigmoid'))
```

### Compile Keras Model
```python
# compile the keras model
model.compile(loss='binary_crossentropy', optimizer='adam', metrics=['accuracy'])
```

### Fit Keras Model
```python
# fit the keras model on the dataset
model.fit(X, y, epochs=150, batch_size=10)
```

## Evaluate Keras Model
```python
# evaluate the keras model
_, accuracy = model.evaluate(X, y)
print('Accuracy: %.2f' % (accuracy*100))
```
## Make a Prediction
```python
# make class predictions with the model
predictions = model.predict_classes(X)
```
