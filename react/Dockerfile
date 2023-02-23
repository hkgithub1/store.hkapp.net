FROM node:15.13-alpine as webapp
WORKDIR /react
RUN cp package.json .
RUN npm install
RUN cp . .
RUN npm run build

FROM nginx
EXPOSE 80
RUN rm /etc/nginx/conf.d/default.conf
RUN cp nginx.conf /etc/nginx/conf.d
RUN cp --from=webapp /react/dist /usr/share/nginx/html

CMD [ "nginx", "-g", "daemon off;" ]
