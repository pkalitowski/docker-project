FROM alpine
RUN apk update
RUN apk add nginx
EXPOSE 80
RUN mkdir -p /var/www/html
COPY default.conf /etc/nginx/http.d/default.conf
CMD ["nginx", "-g", "daemon off;"]
