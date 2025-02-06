# ELL887 Cloud Computing - Assignment 1 (Containers)

## Overview
This assignment consists of three parts:
1. **Modifying an existing web server container** (Nginx)
2. **Creating and pushing a container** (C++ program + MySQL database)
3. **Deploying a web server in Kubernetes**
---

## Part 1: Modifying an Existing Web Server Container

### Objective
This part modifies an Nginx container to serve a custom webpage at `http://localhost/ELL887`.

### Files Provided:
- `Dockerfile` (to create a custom Nginx container)
- `index.html` (to display the required message)

### Steps to Run:
1. **Build the container:**
   ```sh
   docker build -t modified-nginx .

2. **Run the container:**
   ```sh
   docker run -d -p 80:80 modified-nginx


3. **Verify the output:**
   ```sh
   [htttp://localhost/ELL887](http://localhost/ELL887)

   OUTPUT: "Hello world! I am Shailesh Mishra".
![part_a](https://github.com/user-attachments/assets/b518f589-f329-4f73-944c-8315bbe62d3e)


   
## Part 2: Creating and Pushing a Container

### Objective
This part containerizes a C++ program that prints "Hello world!! I am Shailesh Mishra " and includes a MySQL database.

### Files Provided:
- `Dockerfile` (to create a custom Nginx container)
- `docker-compose.yaml` (to include a MySQL database)
- `index.html` (to display the required message)

### Steps to Run:
A. **Run the c++ program container**
1. **Build the C++ container:**
   ```sh
   docker build -t myapp .

2. **Run the container:**
   ```sh
   docker run myapp

3. **Verify the output:**
   ```sh
   OUTPUT: "Hello world!! I am Shailesh Mishra ".
![partb1](https://github.com/user-attachments/assets/48b4c5e7-af2e-4cab-88a1-3ee43eefb50c)



B. **Start the Database using Docker Compose**
1. **Run the services(c++ ap + MySql database)**
   
   ```sh
    docker-compose up

2. **Use different terminal to use MySql**
   ```sh
     docker exec -it mysql-db mysql -u root -p
     #password: shailesh

3. **Repositories pull command**
   ```sh
    docker pull shaileshmishra103/ell887:myapp 
    docker pull shaileshmishra103/ell887:db 


For connecting the cpp and MySQL, I have used the left side docker-compose file and submitted the (right side image_ docker-compose file in which I have updated the image as docker repositories.

![partb2](https://github.com/user-attachments/assets/b8401e47-27e9-4a12-a7e1-f2181b399eb4)![Screenshot (448)](https://github.com/user-attachments/assets/331a11ad-b1e1-45f0-8ca6-599e280eab6f)






4. **To verify the output**
   ```sh
   docker compose up

![partboutput](https://github.com/user-attachments/assets/4c4e615c-e435-4393-8873-d1f57299322d)


## Part 3: Modifying an Existing Web Server Container

### Objective
Deploy a web server in a Kubernetes cluster using Minikube. web server runs on port 30001

### Files Provided:
- `deployment.yaml` (K8s Deployment & service for the web server)

### Steps to Run:
1. **Apply the Kubernetes configuration using:**
   ```sh
   kubectl apply -f deployment.yaml

2. **check the running pods using:**
   ```sh
   kubectl get pods
   
3. **check the service pods using (wait until webserver pod is in running state the use below cmd):**
   ```sh
   minikube service webserver-service



4. **Access the web server using:**
   ```sh
   [htttp://<minikube-ip>:30001](htttp://<minikube-ip>:30001)

   OUTPUT: nginx web page.

![partc](https://github.com/user-attachments/assets/980795ce-dc54-41b4-a833-731775658e3c)

