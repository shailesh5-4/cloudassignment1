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
![image](https://github.com/user-attachments/assets/2e82ec8c-a797-46e3-aea0-8ceee8623b7d)

3. **Verify the output:**
   ```sh
   [htttp://localhost/ELL887](http://localhost/ELL887)

   OUTPUT: "Hello world! I am Shailesh Mishra".
![image](https://github.com/user-attachments/assets/3e8629d2-aacb-4ee6-bbd7-fa8ecfc6ca1e)

   
## Part 2: Creating and Pushing a Container

### Objective
This part containerizes a C++ program that prints "Hello world!! I am Shailesh Mishra (2024EET2354)" and includes a MySQL database.

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
![image](https://github.com/user-attachments/assets/78a262bb-2b73-4c29-8026-48ef21981227)


B. **Start the Database using Docker Compose**
1. **Run the services(c++ ap + MySql database)**
   
   ```sh
    docker-compose up

2. **Use different terminal to use MySql**
   ```sh
     docker exec -it mysql-db mysql -u root -p
     #password: admin@1

3. **Repositories pull command**
   ```sh
    docker pull saurabhbalke/ell887:app 
    docker pull saurabhbalke/ell887:db 


For connecting the cpp and MySQL, I have used the left side docker-compose file and submitted the (right side image_ docker-compose file in which I have updated the image as docker repositories.

![Screenshot from 2025-02-06 15-57-27](https://github.com/user-attachments/assets/5c7db5b3-7915-4a3f-8897-d11ec134f13d) ![image](https://github.com/user-attachments/assets/90c16f5b-500a-40f5-b094-d8163e1bddfd)

4. **To verify the output**
   ```sh
   docker compose up
![image](https://github.com/user-attachments/assets/a889b770-84ab-4d42-a5c7-4f03477a0eb2)


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

![image](https://github.com/user-attachments/assets/0d000183-f0dd-4119-ab95-52a033d69e52)

4. **Access the web server using:**
   ```sh
   [htttp://<minikube-ip>:30001](htttp://<minikube-ip>:30001)

   OUTPUT: nginx web page.

![Screenshot from 2025-02-06 15-19-53](https://github.com/user-attachments/assets/bea9ae8d-4378-4470-9f66-b8bd9f9c62e4)
