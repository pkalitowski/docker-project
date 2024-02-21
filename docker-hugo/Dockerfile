FROM alpine
RUN apk update
RUN apk add git
RUN apk add --no-cache --repository=https://dl-cdn.alpinelinux.org/alpine/edge/community hugo
RUN hugo new site quickstart
RUN cd quickstart && git init && git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke && hugo new posts/some-post.md && echo "theme = 'ananke'" >> hugo.toml && hugo
CMD [ "sleep", "infinity" ]