FROM php:5-fpm-alpine

RUN apk update && \
    apk add --no-cache grep