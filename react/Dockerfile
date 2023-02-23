FROM node:15.13-alpine as webapp
WORKDIR /react
COPY /ComicsDocker/react/package.json .
RUN npm install
COPY /ComicsDocker/react .
RUN npm run build

FROM nginx
EXPOSE 80
RUN rm /etc/nginx/conf.d/default.conf
COPY /ComicsDocker/react/nginx.conf /etc/nginx/conf.d
COPY --from=webapp /react/dist /usr/share/nginx/html

CMD [ "nginx", "-g", "daemon off;" ]
