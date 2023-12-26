#Deep Learning Image Recognition Inference for using ResNet-18 based app 

Forked from this project: https://github.com/hasibzunair/imagercg-waiter
ResNet18 https://www.mathworks.com/help/deeplearning/ref/resnet18.html

This application *serves* a deep learning image classification model that recognizes what object is present in an image. It accepts images from the user, makes request to an API endpoint that makes a prediction, and shows results in a frontend UI. This workshop demonstrates use-cases of different tools such as `PyTorch`, `FastAPI`, `Gradio` and `Docker`.
It can be run via API backend with Curl or a Web Front End. 

Currently: 
Updating images, converting to Podman and run on OpenShift and ROSA AWS OpenShift Managed Service 

Sample Backend Input Image: 
<p align="left">
  <a href="#"><img src="./frontend/test1.jpeg" width="200"></a> <br />
  <em> 
  </em>
</p>

Sample Text Output for Backend:

{"success":true,"predictions":[{"label":"black-and-tan coonhound","probability":0.5641617774963379},{"label":"Doberman","probability":0.3869141638278961},{"label":"bluetick","probability":0.012455757707357407},{"label":"Rottweiler","probability":0.007904204539954662},{"label":"Gordon setter","probability":0.006333122029900551}]}%


Sample Web FrontEnd Output:
<p align="left">
  <a href="#"><img src="./frontend/sample.jpeg" width="200"></a> <br />
  <em> 
  </em>
</p>

### Usage Docker
To Build and run the application Clone the source files. 

#git clone https://github.com/emcon33/emcon33-waiter

#cd<path>/backend

#docker build -t classification_model_serving .

#docker run -p 8000:80 classification_model_serving

#curl -X POST -F image=@test2.jpeg "http://0.0.0.0:8000/api/predict"

#Alternative Backend Method 
#If you have issues with the build the pre-built image for the backend is avaialble here.

#docker pull /andrewwg/classification_model_serving

#docker run -p 8000:80 classification_model_serving

#curl -X POST -F image=@test2.jpeg "http://0.0.0.0:8000/api/predict"


#Web Front End Build and Deploy (current error on vartiable error)

#cd<path>/frontend

#docker build -t frontend_serving .

#docker run -p 7860:7860 --add-host host.docker.internal:host-gateway frontend_serving

The app is live in `http://0.0.0.0:7860`. Upload images to make a prediction via Curl or Web Front End. 

<Gradio won't import on my system>
Broken with this message 
(base) agrimes@andys-mbp frontend % docker run -p 7860:7860 --add-host host.docker.internal:host-gateway andrewwg/frontend_serving 
Traceback (most recent call last):
  File "/app/main.py", line 32, in <module>
    inputs = gr.inputs.Image(type='filepath')
AttributeError: module 'gradio' has no attribute 'inputs'


#Direct Front End Pre-Built Image 

#docker pull hasibzunair/frontend_serving

#docker run -p 7860:7860 --add-host host.docker.internal:host-gateway /hasibzunair/frontend_serving





#Alternative Usage Podman Deployment

#Backend
#podman build -t classification_model_serving .

#podman run -p 8000:80 --name cls-serve classification_model_serving

#curl -X POST -F image=@test2.jpeg "http://0.0.0.0:8000/api/predict"


Frontend 
<see error above> gradio import issue on Gradio

#OpenShift/ROSA Deployment

#ArgoCD/Tekton Pipeline 


#### Todos
* Build Frontend (Gradio/Python version issue) 
* Port to Podman 
* Port to OpenShift/ROSA
* Rebuild as Workshop for AWS ROSA

### References
Original source https://towardsai.net/p/machine-learning/build-and-deploy-custom-docker-images-for-object-recognition
Forked from this github https://github.com/hasibzunair/imagercg-waiter
