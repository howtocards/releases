ARG FRONTEND_VERSION=v0.6.0
ARG SSI_VERSION=v0.1.2-pre.1

FROM howtocards/frontend:$FRONTEND_VERSION as static
WORKDIR /build

FROM howtocards/ssi:$SSI_VERSION
WORKDIR /app

COPY --from=static /var/www /app/static

ENV PUBLIC_URL https://howtocards.io
ENV BACKEND_URL http://db:9000
ENV LISTEN_HOST 0.0.0.0:4000
ENV SITENAME Howtocards

CMD ["/howtocards_ssi"]
