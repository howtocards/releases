FROM nginx:alpine

COPY entrypoint.sh /bin/entrypoint
COPY start.sh /bin/start-server
RUN chmod +x /bin/entrypoint && chmod +x /bin/start-server


EXPOSE 80
ENTRYPOINT ["/bin/entrypoint"]
CMD ["/bin/start-server"]

COPY nginx.conf /etc/nginx/nginx.conf
