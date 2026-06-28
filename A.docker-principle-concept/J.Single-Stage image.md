### 🚀Single-Stage Docker Images & Containers | Application Deployment

- #### 📌Writing a Simple Application on Nodejs

```sh
sudo apt update
sudo apt install -y nodejs npm
node -v
npm -v
mkdir my-node-app
cd my-node-app
npm init -y
npm install express
```

   - #### 📌Create a File Named `app.js` and Add the Following Code

```sh
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
    res.send('Hello World!');
});

app.listen(port, () => {
    console.log(`Example app listening at http://localhost:${port}`);
});

```

   - #### 📌Run and Test Your Application in Host Machine

You should see the message `Example app listening at http://localhost:3000`

`node app.js`

   - #### 📌Write a Dockerfile on Nodejs Application

```sh
# Use an official Node.js runtime as a parent image
FROM node:14
# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Make port 3000 available to the world outside this container
EXPOSE 3000

# Run the app
CMD ["node", "app.js"]

```

   - #### 📌Build an Image: Use the Dockerfile to build a Docker image & Run from local Image

`docker build -t my-node-app .`

`docker run -it -d -p 3000:3000 my-node-app`

   - #### 📌Tag | Login | Push the Docker Image

`docker tag my-node-app csealauddin/my-node-app:latest`
  
`docker login`

`docker push csealauddin/my-node-app:latest`

   - #### 📌Pull and Run - Download the image from Docker Hub

`docker pull csealauddin/my-node-app:latest`

`docker run -it -d -p 3001:3000 csealauddin/my-node-app:latest`

`docker ps -a`
