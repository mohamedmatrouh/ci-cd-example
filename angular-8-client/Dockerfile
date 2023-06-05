
FROM nginx:alpine

WORKDIR /app

COPY ./static /app/src
COPY ./nginx/nginx.conf /etc/nginx/nginx.conf

CMD ["nginx", "-g", "daemon off;"]
