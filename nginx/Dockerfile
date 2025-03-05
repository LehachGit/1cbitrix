# Используем стабильную версию Nginx
FROM nginx:1.24

# Устанавливаем необходимые пакеты (например, gzip для сжатия)
RUN apt-get update && apt-get install -y \
    nano \
    gzip \
    && rm -rf /var/lib/apt/lists/*

# Удаляем дефолтную конфигурацию и копируем свою
RUN rm /etc/nginx/conf.d/default.conf
COPY conf.d/default.conf /etc/nginx/conf.d/default.conf

# Директория для логов (по желанию)
RUN mkdir -p /var/log/nginx && chown -R nginx:nginx /var/log/nginx

# Открываем порты
EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]