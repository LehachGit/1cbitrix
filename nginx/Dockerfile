FROM nginx:1.24

# Установка пакетов
RUN apt-get update && apt-get install -y \
    nano \
    gzip \
    && rm -rf /var/lib/apt/lists/*

RUN rm /etc/nginx/conf.d/default.conf
COPY conf.d/default.conf /etc/nginx/conf.d/default.conf

# Логи
RUN mkdir -p /var/log/nginx && chown -R nginx:nginx /var/log/nginx

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]