FROM node:16.19-alpine AS frontend

ENV CLOUDL_SERVER=localhost

WORKDIR /usr/src/app

COPY package*.json .

RUN npm install

COPY . .

RUN npm run build


FROM nginx:1.23.3

WORKDIR /usr/share/nginx/html

RUN rm -rf ./*

COPY --from=frontend /usr/src/app/build .

COPY --from=frontend /usr/src/app/nginx/nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

