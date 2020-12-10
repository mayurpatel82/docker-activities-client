
How to Dockerize a React App and Deploy in Elastic Beanstalk


Docker Configuartion Steps
1. Create file called "Dockerfile" and add the following lines, be sure to change version to a number i.e: 10.12.0 Use node -v to find version

FROM node:version
container .

WORKDIR /app

COPY . /app

RUN npm install

CMD npm start

EXPOSE 3000
2. Create .dockerignore file and add in the following lines

node_modules
npm-debug.log
Docker Build Steps
1. Build docker first

docker build -t docker-name .
2. Run docker to test.

docker run -p 8081:3000 professional-portfolio
Elastic Beanstalk Steps
1. Commit changes to git

git add .

git commit -m "Eb Deploy Settings"

git push
2. Initialize EB

eb init 

Select default -> Create new application -> Enter application name -> Setup ssh
3. Create EB Environment

eb create

Select default -> Select Name
4. Deploy EB

eb use environment name

eb deploy
5. Confirm EB is deployed

eb open
Author:
Ryan LeBon
AWS, Docker & React
