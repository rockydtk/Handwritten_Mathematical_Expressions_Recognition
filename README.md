# Handwritten Mathematical Expressions Recognition
### Khiem T. Do, Phuong T.M. Chu & Santhos

This is the project that we finished after the 8th week of studying **Machine Learning** from scratch.
<p align="center">
  <img width="860" height="400" src="https://cdn.discordapp.com/attachments/603841721222037505/620517992186249226/unknown.png">
</p>

## INTRODUCTION
### 1. Handwritten Mathematical Expressions Recognition
If you've ever had to typeset mathematical expressions, you might have thought: wouldn’t it be great if I could just take a picture of a handwritten expression and have it be recognized automatically? Can you use computer vision to recognize handwritten mathematical expressions? In this project, we will prove that we can!

### 2. Project goals
- Building models to classify **Handwritten Mathematical Expressions** (Numbers and Operators) images.

- Making a **Web Flask application** so user can upload the images and perform calculation.

### 3. Project plan
Main steps:
1. Build Handwritten Equation Solver locally on OpenCV
2. Make Handwritten Equation Solver Flask App

|Task|Progress|
|:-----------------------------|:------------:|
|Data collection |✔|
|Data preprocessing |✔|
|Building Model|✔|
|Building Flask App|✔|
|Deployment to Google Cloud|✔|

## COLLECTING DATA
### 1. The Handwritten math symbols dataset
[The Kaggle Dataset](https://www.kaggle.com/xainano/handwrittenmathsymbols) consists of `jpg` files (45x45). It includes:
- Basic Greek alphabet symbols like: `alpha`, `beta`, `gamma`, `mu`, `sigma`, `phi` and `theta`
- English alphanumeric symbols
- All math operators and set operators
- Basic pre-defined math functions like: `log`, `lim`, `cos`, `sin`, `tan`
- Math symbols like: `\int`, `\sum`, `\sqrt`, `\delta` and more.

For simplicity, in this project, we only take into account 4 math operators: `plus`,`minus`,`addition`, and `division`.

### 2. Data Collection process 
During the data cleanning process, we can see that it is biased for some of the digits/symbols, as it contains 12000 images for some symbol and 3000 images for others. To remove this bias, reduce the number of images in each folder to approximately 4000.

## BUILDING MODELS
### Dataset
**Extracting Features**
We can use contour extraction to obtain features.
Invert the image and then convert it to a binary image because contour extraction gives the best result when the object is white, and surrounding is black.
To find contours use ‘findContour’ function. For features, obtain the bounding rectangle of contour using ‘boundingRect’ function (Bounding rectangle is the smallest horizontal rectangle enclosing the entire contour).
Since each image in our dataset contains only one symbol/digit, we only need the bounding rectangle of maximum size. For this purpose, we calculate the area of the bounding rectangle of each contour and select the rectangle with maximum area.
Now, resize the maximum area bounding rectangle to 28 by 28. Reshape it to 784 by 1. So there will be now 784-pixel values or features. Now, give the corresponding label to it (For e.g., for 0–9 images same label as their digit, for – assign label 10, for + assign label 11, for times assign label 12). So now our dataset contains 784 features column and one label column. After extracting features, save the data to a CSV file.
### Model performance summary


## BUILDING THE FLASK APP
<p align="center">
  <img width="860" height="400" src="https://cdn.discordapp.com/attachments/603841721222037505/620526625297137664/unknown.png">
</p>

### How to run the Flask App locally
```
virtualenv env
source env/bin/activate

# For window
set FLASK_APP=app.py
set FLASK_ENV=development
export FLASK_DEBUG=1
flask run

# For Ubuntu
export FLASK_APP=app.py
export FLASK_ENV=development
export FLASK_DEBUG=1
flask run
```
### Deploy the App to Google Cloud Platform

```
gcloud app deploy
```

## CONCLUSION
We successfully built 2 models which are used together to classify **Handwritten Mathematical Expressions** (Numbers and Operators) images with high accuracy of **97%** (for predicting numbers) and accuracy of **94.88%** (for predicting math operators).

In addition, we also **built a Flask application** so user user can upload the images and perform calculation.
