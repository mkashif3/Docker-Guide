# DOCKER PROJECT HANDSON

Step1 - Take the EC2 Ubuntu instance from AWS with below configurations
    Type - Ubuntu 
    Size - T2.Micro 
    GB - 8

Step 2 Install tools like 
  Maven -
    
      sudo apt update -y
      sudo apt install maven -y mvn -version
      
  Docker -
      
      sudo apt update -y
      sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
      curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
      sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable" -y
      sudo apt update -y
      apt-cache policy docker-ce -y
      sudo apt install docker-ce -y
      #sudo systemctl status docker
      sudo chmod 777 /var/run/docker.sock 
      
  Git
      
      apt install git

Step 3 - Clone the code

      git clone https://github.com/DEVOPS-WITH-WEB-DEV/spring-clo ud-kubernetes.git

Step 4 - Go over the docker file in above repo
   https://github.com/DEVOPS-WITH-WEB-DEV/spring-cloud-kubernetes/blob/main/kubernetes-configmap-reload/Dockerfile

Step 5 - Build the code with maven 
  
      mvn clean install -DskipTests

![Screenshot 2024-08-18 at 00 41 48](https://github.com/user-attachments/assets/402da827-c272-442f-9147-8c346500ce95)

Step 6 - Go to project folder in Ubuntu where dockerfile is present

Step 7 - Run the below command to create the docker image

     docker build -t bahubali/1:latest .
     
![Screenshot 2024-08-18 at 00 42 37](https://github.com/user-attachments/assets/66584a7c-90dd-4a19-801e-c76dd0d0d683)

Step 8 - Run the below command to create the image into container

    docker run -itd <imageID> –name chirutha

Here chirutha is container name ImageId is from above screenshot

![Screenshot 2024-08-18 at 00 43 27](https://github.com/user-attachments/assets/fa55e9dd-7eb9-47bc-a8ff-bad9188849a8)

Step 9 - Go inside the container and check the data 

    docker exec -it <containerID> /bin/sh
 
 Step 9 - Check the app.jar file in docker
  
![Screenshot 2024-08-18 at 00 44 15](https://github.com/user-attachments/assets/98f607da-0ab5-4dc0-a2e6-1959ee506a69)
