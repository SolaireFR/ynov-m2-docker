FROM nginx:alpine

# GIT
RUN apk add --no-cache git

# SUPPRESSION ANCIEN HTML
RUN rm -rf /usr/share/nginx/html/*

# CLONE /usr/share/nginx/html
RUN git clone https://github.com/withaarzoo/3D-Rotate-Tube.git /usr/share/nginx/html

# PORT 80
EXPOSE 80