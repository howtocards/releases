ARG FRONTEND_VERSION=nightly
ARG SSI_VERSION=nightly

FROM howtocards/frontend/frontend:$FRONTEND_VERSION as static
WORKDIR /build

FROM howtocards/ssi/ssi:$SSI_VERSION
WORKDIR /app

COPY --from=static /var/www /app/static

ENV PUBLIC_URL https://howtocards.io
ENV IMAGE_URL https://howtocards.io/images
ENV BACKEND_URL http://db:9000
ENV LISTEN_HOST 0.0.0.0:4000
ENV SITENAME Howtocards
ENV INDEX_HTML_PATH /app/static/index.html

CMD ["/howtocards_ssi"]
