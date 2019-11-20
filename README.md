# YOLO Object Detection Service

Dockerized object detection service using [YOLO](https://pjreddie.com/darknet/yolo/) based on [AlexeyAB's darknet fork](https://github.com/AlexeyAB/darknet) and
exposed as a REST API using [connexion](https://github.com/zalando/connexion). 

## Quick start

Pull the image from [Docker Hub](https://hub.docker.com/r/johannestang/yolo_service) and spin up a container:
```
docker run -d --rm --name yolo_service -p 8080:8080 ---- insert here -----
```

This will expose a single endpoint `detect` that accepts GET and POST requests where the former takes a URL of an image and the latter lets you upload an image for detection.
The service provides a user interface at [localhost:8080/ui](http://localhost:8080/ui) where the endpoint can be tested and the details of the input parameters are listed.
