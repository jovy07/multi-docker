FROM node:alpine
WORKDIR '/app'
ENV REDIS_HOST redis 
ENV REDIS_PORT 6379 
COPY  ./package.json ./
RUN npm install
COPY . .
RUN apk add --no-cache bash
#RUN ["npm", "run" ,"dev","--verbose"]
RUN  ["./wait-for-it.sh","-t","1000","www.google.com:80"] 