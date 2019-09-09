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
### Model performance summary
![](https://i.imgur.com/pSWkopG.png)
## BUILDING THE FLASK APP
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
We successfully builts 2 models to classify **Handwritten Mathematical Expressions** (Numbers and Operators) images with high accuracy of **97%** (for predicting numbers) and accuracy of **94.88%** (for predicting math operators).

In addition, we also **built a Flask application** so user user can upload the images and perform calculation.
