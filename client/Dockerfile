FROM node:alpine as builder 
WORKDIR /app 
COPY client/package.json ./
RUN npm install 
COPY client ./
RUN npm run build 

FROM nginx 
EXPOSE 3000 
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf 
COPY --from=builder client/build /usr/share/nginx/html