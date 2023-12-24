# Image Recognition Waiter
#source https://towardsai.net/p/machine-learning/build-and-deploy-custom-docker-images-for-object-recognition
# Modifying for Podman and OpenShift use 
# Updating Images for RH dog images

This application *serves* a deep learning image classification model that recognizes what object is present in an image. It accepts images from the user, makes request to an API endpoint that makes a prediction, and shows results in a frontend UI. 

It demonstrates use-cases of different tools such as `PyTorch`, `FastAPI`, `Gradio` and `Docker`.
<p align="left">
  <a href="#"><img src="./frontend/test1.jpeg" width="200"></a> <br />
  <em> 
  Model Output Lakeland Terrier 29%
  </em>
</p>

Output Example
<p align="left">
  <a href="#"><img src="./frontend/sample.jpeg" width="200"></a> <br />
  <em> 
  Model Output Lakeland Terrier 29%
  </em>
</p>

### Usage Docker
To launch the application, run for docker:
```
git clone https://github.com/hasibzunair/imagercg-waiter
sh deploy.sh 
```

### Usage Podman
To launch the application, run for docker:
```
git clone https://github.com/hasibzunair/imagercg-waiter
sh deploy.sh 
```

The app is live in `http://0.0.0.0:7860`. Upload images to make a prediction, or simply use the examples! For details on how the `frontend` and `backend` components were built, see respective folders. 

### Note
I did this project after completing [Docker for the Absolute Beginner - Hands On - DevOps](https://www.udemy.com/course/learn-docker/).

#### Todos
* Google cloud run for backend
* Docker compose
* Kubernetes (make some pods lol!)

### References
Also see [learn-docker](https://github.com/hasibzunair/learn-docker).
