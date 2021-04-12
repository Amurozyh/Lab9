# Lab9

# Example00

OS: Ubuntu 14.04 x86_64

sudo apt-get update

![image](https://user-images.githubusercontent.com/61073477/114331061-c562d680-9b75-11eb-8910-e5e126b9eab7.png)

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
lsb-release

![image](https://user-images.githubusercontent.com/61073477/114331074-cac02100-9b75-11eb-8af6-7e444a03c3ff.png)

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

![image](https://user-images.githubusercontent.com/61073477/114331083-d0b60200-9b75-11eb-81e8-6d7179f5b517.png)

echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

![image](https://user-images.githubusercontent.com/61073477/114331093-d875a680-9b75-11eb-8269-ca15f3c60a87.png)

Then install docker engine

sudo apt-get update

![image](https://user-images.githubusercontent.com/61073477/114331105-de6b8780-9b75-11eb-905c-f9d91160f4bb.png)

sudo add-apt-repository ppa:ubuntu-sdk-team/ppa

![image](https://user-images.githubusercontent.com/61073477/114331124-e6c3c280-9b75-11eb-8b6d-f21f95e36c4a.png)

After sudo apt-get update, run sudo apt-get install docker-ce containerd.io

![image](https://user-images.githubusercontent.com/61073477/114331131-ecb9a380-9b75-11eb-9f45-332be5966f47.png)

docker run docker/whalesay cowsay boo

![image](https://user-images.githubusercontent.com/61073477/114331138-f216ee00-9b75-11eb-84d0-ac445d0f58c4.png)

![image](https://user-images.githubusercontent.com/61073477/114331105-de6b8780-9b75-11eb-905c-f9d91160f4bb.png)

# Example01

## Running the Ubuntu container

sudo docker run -it ubuntu bash

![image](https://user-images.githubusercontent.com/61073477/114331151-fcd18300-9b75-11eb-8fd0-5a68ef430c8a.png)

![image](https://user-images.githubusercontent.com/61073477/114331105-de6b8780-9b75-11eb-905c-f9d91160f4bb.png)

## Installing Vim

Install:
apt update && apt install vim

![image](https://user-images.githubusercontent.com/61073477/114331181-0eb32600-9b76-11eb-9b96-6f1acbb76f72.png)

Test Vim

![image](https://user-images.githubusercontent.com/61073477/114331226-27234080-9b76-11eb-87b3-d933fc3d05d1.png)

## Installing Cowsay

apt install cowsay

![image](https://user-images.githubusercontent.com/61073477/114331235-2f7b7b80-9b76-11eb-96f2-6228712db8c3.png)

Run game

![image](https://user-images.githubusercontent.com/61073477/114331250-3609f300-9b76-11eb-9cf5-82db286a228a.png)


# Example02

## Start an instance of mongo in background

docker run --name db -d mongo:3.2 mongod –smallfiles

![image](https://user-images.githubusercontent.com/61073477/114331278-41f5b500-9b76-11eb-966d-9048c33277c7.png)

## Start Rocket.Chat application.

sudo docker run --name rocketchat -p 3000:3000 --env ROOT_URL=http://localhost --link db:db -d rocket.chat:0.62

![image](https://user-images.githubusercontent.com/61073477/114331294-4ae68680-9b76-11eb-90da-e67cc5ab6017.png)

Now see running containers: sudo docker ps

![image](https://user-images.githubusercontent.com/61073477/114331310-5043d100-9b76-11eb-8510-6f1f83e3da19.png)

Now browse the web application in container

![image](https://user-images.githubusercontent.com/61073477/114331320-55088500-9b76-11eb-93c1-7487da58f416.png)

# Example03

## Create the Dockerfile

touch Dockerfile

![image](https://user-images.githubusercontent.com/61073477/114331345-60f44700-9b76-11eb-8b1c-c92d426d96c9.png)

## Dockerfile Contents

Docker file

![image](https://user-images.githubusercontent.com/61073477/114331363-6b164580-9b76-11eb-9877-848e9e9263cf.png)

hello.py

![image](https://user-images.githubusercontent.com/61073477/114331383-736e8080-9b76-11eb-9b18-2a852d302903.png)

## Build and run the Dockerfile

Build the Dockerfile “hellodocker”
docker build -t hellodocker .

![image](https://user-images.githubusercontent.com/61073477/114331403-7ec1ac00-9b76-11eb-853f-1fa2ad707b02.png)

Run the container

![image](https://user-images.githubusercontent.com/61073477/114331413-84b78d00-9b76-11eb-8a93-05d86420fddd.png)

## Browse

![image](https://user-images.githubusercontent.com/61073477/114331434-8c773180-9b76-11eb-8820-3eab054a148c.png)


# Example04

## Dockerfile

![image](https://user-images.githubusercontent.com/61073477/114331450-95680300-9b76-11eb-9874-ba0e0004df03.png)

## Image creation

docker build -t message-app .

![image](https://user-images.githubusercontent.com/61073477/114331464-9dc03e00-9b76-11eb-9fe3-a0e5bd312516.png)

Then list and find the Docker image created.

![image](https://user-images.githubusercontent.com/61073477/114331474-a4e74c00-9b76-11eb-9da5-5f3a5e56e6d8.png)

## Writing a docker compose file

![image](https://user-images.githubusercontent.com/61073477/114331491-add81d80-9b76-11eb-9518-50c4bf2f3b12.png)

Then build it
docker-compose build

![image](https://user-images.githubusercontent.com/61073477/114331501-b4ff2b80-9b76-11eb-8598-4677d396478b.png)

Run service
docker-compose up

![image](https://user-images.githubusercontent.com/61073477/114331509-ba5c7600-9b76-11eb-97b6-e8dfe34a0682.png)
