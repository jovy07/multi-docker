FROM node:alpine
ENV REDIS_HOST redis 
ENV REDIS_PORT 6379 
ENV PGUSER postgres 
ENV PGHOST postgres 
ENV PGDATABASE postgres
ENV PGPASSWORD mysecretpassword 
ENV PGPORT 5432 
WORKDIR '/app'
COPY  ./package.json ./
RUN npm install
COPY . .
RUN apk add --no-cache bash
RUN  ["./wait-for-it.sh","-t","1000","www.google.com:80"] 

