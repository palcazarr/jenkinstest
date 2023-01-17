# 🐐
FROM nginx
ARG REDIRECTPORT
ARG HOSTNAME
ENV REDIRECTPORT=$REDIRECTPORT
ENV HOSTNAME=$HOSTNAME
COPY nginx/index.html /usr/share/nginx/html/index.html
COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf
COPY nginx/openssl /etc/nginx/openssl
RUN echo "REDIRECTPORT : $REDIRECTPORT"
RUN echo "HOSTNAME: $HOSTNAME"
EXPOSE 80
EXPOSE 443