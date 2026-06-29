https://github.com/pravinmishraaws/Docker-Demo/blob/main/04_Sharing_Docker_Image.md

#### 📌Build an Image: Use the Dockerfile to build a Docker image & Run from local Image - Multi-Stage 

`docker build -t my-node-app .`

`docker run -it -d -p 3000:3000 my-node-app`

   - #### 📌Tag | Login | Push the Docker Image - Multi-Stage 

`docker tag my-node-app csealauddin/my-node-app:latest`
  
`docker login`\
`docker login -u alauddin94`\
`docker info | grep Username`\
`docker logout`

`docker push alauddin94/my-node-app:latest`

   - #### 📌Pull and Run - Download the image from Docker Hub - Multi-Stage 

`docker pull alauddin94/my-node-app:latest`

`docker run -it -d -p 3001:3000 alauddin94/my-node-app:latest`

`docker ps -a`
