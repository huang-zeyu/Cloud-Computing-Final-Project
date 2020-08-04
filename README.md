# mnist_on_the_cloud
Final project of Cloud Computing
## Group Members
* [Zeyu Huang][1]
* [Tian Tan][2]
* [Xiaozhu Yu][3]

[1]: https://github.com/Asterion98k
[2]: https://github.com/TT159
[3]: https://github.com/martino27

## What is our project
What we have accomplished is a Digit Recognition Cloud Application based on Google Cloud Platform (GCP). When our cloud app is running, you will find a url of this app, and of course every one in the world can visit it. In this webpage, you can upload a image of a hand-written digit. Once it is received, our cloud app will analyze what number it contains using the pretrained CNN model and will return the result immediatly on the webpage where you upload the image.

## About our project

### About machine learning part
We built a convolutional neural network using tensorflow. The network contains 2 conv layers. To train the model, just run backward.py and the trained model will be automatically stored in the directory. If we want to predict a hand-written digit,  we should restore the model and input the image, then the predicted result will be given.

### About cloud application
We added app.yaml and Dockerfile and configured the env vars on the GCP. Then we built a docker image and stored it in container registry. After that, our app can be deployed using the Google App Engine which expose an url of our cloud application.

### About load testing
We used Locust for load testing. Firstly, we deployed Kubernetes clusters on GKE. Then, we deployed locust master and workers to perform requests to our cloud app. After we entered the webpage of locust, we input the total number of users we wanted to simulate and rate of generating users and we started swarming and observed the graph of the performance of our cloud app when dealing with heavy loads of traffic.

---
## Reference
About configurations and instructions used to run this project, you can refer to [Distributed Load Testing Using Kubernetes](https://www.qwiklabs.com/focuses/967?catalog_rank=%7B%22rank%22%3A1%2C%22num_filters%22%3A0%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=6297126 "With a Title")
