# YOLO Object Detection Service
This project is a collaboration between SIT and an industry partner (confidential) that aims to provide a Single Page Application with image recognition capabilities. The main feature involves sending an image uploaded by the frontend user interface to the backend services for image recognition processing. Thereafter, the object within the image shall be recognized by an image detection algorithm before having the bounding box coordinates and its corresponding confidence score returned to the frontend for drawing of results. This project consists of the following repositories:

1. [Frontend Service](https://github.com/saiwoon/Team1-ICT3102-FrontEnd)
2. [API Gateway Service](https://github.com/Desmondtjc/3102-BackendGateway)
3. [Backend Service](https://github.com/Desmondtjc/3102-BackendServices/edit/master/README.md)
4. YOLO Service (Current Repository)

## Demo
Website: http://35.222.160.149

## Prerequisites

<img alt="Docker" src="https://i.imgur.com/yu0yoI7.png" width="50"> Installed [Docker](https://www.docker.com/products/docker-desktop) / [DockerToolbox (Mac)](https://docs.docker.com/toolbox/toolbox_install_mac/) / [DockerToolbox (Windows)](https://docs.docker.com/toolbox/toolbox_install_windows/)

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

<img alt="Kubernetes" src="https://i.imgur.com/3eJILtc.png" width="350"> 

Pulling the image from Google Container Repository
---
We have the completed full system set up on Google container repository running on Google Kubernetes.
Simply pull the front-end docker image and execute it on your local machine.
These image will communicate directly with our Kubernetes.
```
docker pull asia.gcr.io/united-embassy-259407/frontend:update
```

Related Docker images within this project hosted on Google Container Repository
---
| Image                    | Pull command                                                                 | Routed to           |
| ------------------------ | ---------------------------------------------------------------------------- | ------------------- |
| Frontend Service         | docker pull asia.gcr.io/united-embassy-259407/frontend:update                | API Gateway Service |
| API Gateway Service      | docker pull asia.gcr.io/united-embassy-259407/gateway:latest                 | Backend Service     |
| Backend Service          | docker pull asia.gcr.io/united-embassy-259407/backend:latest                 | YOLO Service        |
| YOLO Service             | docker pull asia.gcr.io/united-embassy-259407/hadee9070/yoloservice:latest   | NIL                 |

### Authors
Team 01
- Low Qing En (Backend), 1701410, [(LinkedIn)](https://www.linkedin.com/in/qing-en-low-4275a0158/)
- Lim Jun Jie (Backend), 1700356, [(LinkedIn)](https://www.linkedin.com/in/grisaille/) 
- Tan Jia Cong Desmond (Backend), 1700623, [(LinkedIn)](https://www.linkedin.com/in/desmond-tjc/) 
- Teng Fu Hong Ryan (React), 1701567, [(LinkedIn)](https://www.linkedin.com/in/ryan-teng-692b28158/)
- Muhammad Hadee (Yolo), 1700048, [(LinkedIn)](https://www.linkedin.com/in/hadee-piperdy/)
- Nur Iffahizzati Bte Mahmood (React), 1602024, [(LinkedIn)](https://www.linkedin.com/in/mnuriffah/)

