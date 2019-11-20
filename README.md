# YOLO Object Detection Service

Dockerized object detection service using [YOLO](https://pjreddie.com/darknet/yolo/) based on [AlexeyAB's darknet fork](https://github.com/AlexeyAB/darknet) and
exposed as a REST API using [connexion](https://github.com/zalando/connexion). 

## Quick start

Clone this repo, open up terminal or command prompt from your repo folder and run this command below
Note: Make sure to have Docker installed.

```
docker build -t yolo_final .
```

After the image has been built, you should see something like this 

```
Successfully built c461cf0beba0
Successfully tagged yolo_final:latest
```

Congrats, you have completed the docker file build, you are now able to run the service. Run this command to setup the yolo service to access it in your localhost:8080

```
docker run -d --rm --name yolo_final_service -p 8080:8080 yolo_final
```

This will expose a single endpoint `detect` that accepts GET and POST requests where the former takes a URL of an image and the latter lets you upload an image for detection.
The service provides a user interface via swagger UI at [localhost:8080/ui](http://localhost:8080/ui) where the endpoint can be tested and the details of the input parameters are listed.
