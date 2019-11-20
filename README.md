# YOLO Object Detection Service

Dockerized object detection service using [YOLO](https://pjreddie.com/darknet/yolo/) based on [AlexeyAB's darknet fork](https://github.com/AlexeyAB/darknet) and
exposed as a REST API using [connexion](https://github.com/zalando/connexion). 

## Prerequisites

### Docker on MacOS

You can install docker for MacOS [here](https://docs.docker.com/docker-for-mac/install/)


### Docker on Windows

You can install docker for Windows [here](https://docs.docker.com/docker-for-windows/install/)

To Check if your docker is installed run command `docker --version` or `docker info` and check if your version is higher than 18.0.0


## Starting the YOLO Service

Clone this repo, open up terminal or command prompt from the **cloned repo folder** and run this command below

```
docker build -t yolo_final .
```

After the image has been built, you should see something like this 

```
$: Successfully built c461cf0beba0
$: Successfully tagged yolo_final:latest
```

Congrats, you have completed the docker file build, you are now able to run the service. Run this command to setup the yolo service to access it in your localhost:8080

```
docker run -d --rm --name yolo_final_service -p 8080:8080 yolo_final
```

This will expose a single endpoint `detect` that accepts GET and POST requests where the former takes a URL of an image and the latter lets you upload an image for detection.
The service provides a user interface via swagger UI at [localhost:8080/ui](http://localhost:8080/ui) where the endpoint can be tested and the details of the input parameters are listed.



### Authors
Team 01
- Low Qing En (Backend), 1701410 
- Lim Jun Jie (Backend), 1700356 
- Tan Jia Cong Desmond (Backend), 1700623 
- Teng Fu Hong Ryan (React), 1701567
- Muhammad Hadee (Yolo), 1700048
- Nur Iffahizzati Bte Mahmood (React), 1602024

