# Image Recognition Waiter
# Original source https://towardsai.net/p/machine-learning/build-and-deploy-custom-docker-images-for-object-recognition

# Forked from this project: https://github.com/hasibzunair/imagercg-waiter
Updating images, converting to Podman and run on OpenShift and ROSA AWS OpenShift Managed Service 

This application *serves* a deep learning image classification model that recognizes what object is present in an image. It accepts images from the user, makes request to an API endpoint that makes a prediction, and shows results in a frontend UI. 

It demonstrates use-cases of different tools such as `PyTorch`, `FastAPI`, `Gradio` and `Docker`.
<p align="left">
  <a href="#"><img src="./frontend/test1.jpeg" width="200"></a> <br />
  <em> 
  Model Input 
  </em>
</p>
Output Example

<p align="left">
  <a href="#"><img src="./frontend/sample.jpeg" width="200"></a> <br />
  <em> 
  Model Output 
  </em>
</p>

### Usage Docker
To launch the application, run for docker: (pulls pre-built containers) 
```
git clone https://github.com/hasibzunair/imagercg-waiter
sh deploy.sh 
```

### Usage Podman
To launch the application, run for Podman:
```
git clone https://github.com/emcon33/emcon33-waiter
sh deploypodman.sh 
```

The app is live in `http://0.0.0.0:7860`. Upload images to make a prediction, or simply use the examples! For details on how the `frontend` and `backend` components were built, see respective folders. 

#### Todos
* Port to Podman
* Port to OpenShift/ROSA
* Rebuild as Workshop for AWS ROSA

### References
Forked from this github https://github.com/hasibzunair/imagercg-waiter
