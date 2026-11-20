# Test image for ReleaseProof runs of this fork.
#
# The same Alpine release and PHP packages as Kanboard's own Dockerfile,
# without the web server, process supervisor and mail tools: PHP's built-in
# server runs the application as one unprivileged process. The application's
# files are copied in unchanged.
#
# No VOLUME, on purpose: the sandbox refuses an image that declares storage
# outside its control. Writable directories are listed in releaseproof.yml.
FROM alpine:3.24

RUN apk --no-cache add \
    php85 php85-phar php85-curl php85-json php85-zlib php85-xml php85-dom php85-ctype php85-zip \
    php85-iconv php85-pdo php85-pdo_sqlite php85-mbstring php85-session php85-bcmath php85-gd \
    php85-openssl php85-sockets php85-posix php85-simplexml php85-xmlwriter \
    && ln -sf /usr/bin/php85 /usr/bin/php

WORKDIR /app
COPY . .

USER 10001:10001
CMD ["php", "-S", "0.0.0.0:8080", "-t", "/app"]
