# Try-x Deployment Guide

This guide provides step-by-step instructions to deploy your application on Arpit-VPS.

## Step 1: Update and Upgrade System Packages
First, update and upgrade the system packages to ensure you have the latest versions:
```sh
sudo apt update && sudo apt upgrade -y && clear
```

## Step 2: Clone the Git Repository
Clone the Git repository to your local machine. Replace `<repo-link>` with the actual repository link:
```sh
git clone https://TeamPublik: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@github.com/TeamPublik/try-x
```

## Step 3: Install pip for Python 3
Install pip, the package installer for Python, to manage your Python packages:
```sh
sudo apt install python3-pip -y
```

## Step 4: Create a Virtual Environment
Create a virtual environment to isolate your project's dependencies:
```sh
python3 -m venv ~/try-x/myenv
```

## Step 5: Activate the Virtual Environment
Activate the virtual environment:
```sh
source ~/try-x/myenv/bin/activate
```

## Step 6: Install Python Packages from `requirements.txt`
Install the required Python packages using the `requirements.txt` file:
```sh
pip install -r ~/try-x/requirements.txt
```

## Step 7: Install Docker
Install Docker to containerize your application:
```sh
sudo apt-get install -y docker.io
```

## Step 8: Build the Docker Image
Navigate to the directory where the Dockerfile is located and build the Docker image. Make sure you are in the correct directory:
```sh
cd ~/try-x
sudo docker build -t tryx .
```

## Step 9: Run the Docker Container
Run the Docker container with the specified environment variables and port mappings:
```sh
sudo docker run -p 8087:8087 -e BASE_URL=http://109.230.237.118:8087 -e PORT=8087 tryx
```

## Step 10: List Running Docker Containers
List the currently running Docker containers to verify your container is up and running:
```sh
sudo docker ps
```

## Step 11: Stop a Running Docker Container
To stop a running Docker container, use the container ID obtained from the previous command. Replace `<container-id>` with the actual container ID:
```sh
sudo docker stop <container-id>
```


