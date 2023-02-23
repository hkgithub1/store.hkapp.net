FROM node:15.13-alpine as webapp
WORKDIR /react
COPY package.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 80
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d
COPY --from=webapp /react/dist /usr/share/nginx/html

CMD [ "nginx", "-g", "daemon off;" ]
