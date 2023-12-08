# Containerizing a simple Flask app

This is a simple Python Flask web server project that displays "Hello World!". The project includes a Dockerfile for containerization and can be hosted on an Amazon EC2 Ubuntu 22.04 instance.

## Prerequisites
- An [Amazon EC2](https://aws.amazon.com/ec2) Ubuntu 22.04 instance set up and running
- [Python3](https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-programming-environment-on-an-ubuntu-20-04-server) installed on your EC2 machine
- [Python3-pip](https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-programming-environment-on-an-ubuntu-20-04-server) installed on your EC2 machine
- [Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04) installed on your EC2 machine

## SSH into EC2

1. **SSH into your EC2 instance:**
    ```bash
    ssh -i your-key.pem ec2-user@your-ec2-ip
    ```

## Steps to Run Locally

1. **Clone the repository:**
    ```bash
    git clone https://github.com/shamim-iq/containerizing-a-simple-python-app.git
    ```

2. **Change to the project directory:**
    ```bash
    cd containerizing-a-simple-python-app
    ```

3. **Install Flask:**
    ```bash
    pip install Flask
    ```

4. **Run the Flask app:**
    ```bash
    python3 app.py
    ```

5. **Open your browser and go to "http://<public_ec2_ip>:8000" to see the "Hello World!" message.**

## Dockerize the App

1. **Build the Docker image:**
    ```bash
    docker build -t flask-hello-world .
    ```

2. **Run the Docker container:**
    ```bash
    docker run -itd -p 8000:8000 flask-hello-world
    ```

3. **Open your browser and go to "http://<public_ec2_ip>:8000" to see the "Hello World!" message.**

## Push to Docker Hub

1. **Log in to Docker Hub:**
    ```bash
    docker login
    ```

2. **Tag the Docker image:**
    ```bash
    docker tag flask-hello-world your-username/flask-hello-world
    ```

3. **Push the Docker image to Docker Hub:**
    ```bash
    docker push your-username/flask-hello-world
    ```
