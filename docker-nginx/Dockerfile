FROM alpine
RUN apk update
RUN apk add nginx git
RUN apk add --no-cache --repository=https://dl-cdn.alpinelinux.org/alpine/edge/community hugo
RUN hugo new site quickstart
RUN cd quickstart && git init && git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke && echo "theme = 'ananke'" >> hugo.toml && hugo
EXPOSE 80
RUN mkdir -p /var/www/html
RUN cp -R /quickstart/public/* /var/www/html/
COPY default.conf /etc/nginx/http.d/default.conf
CMD ["nginx", "-g", "daemon off;"]
