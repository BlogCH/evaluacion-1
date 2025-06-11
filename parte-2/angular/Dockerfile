FROM nginx:stable-alpine

# Usar volumen para mayor eficiencia
VOLUME /tmp

# Eliminar archivos por defecto de Nginx
RUN rm -rf /usr/share/nginx/html/*

# Configuración de Nginx
COPY nginx.conf /etc/nginx/nginx.conf
COPY mime.types /etc/nginx/mime.types

# Copiar los archivos del frontend Angular al contenedor
COPY sistema-ventas-front /usr/share/nginx/html

# Exponer el puerto 80 (por defecto de Nginx)
EXPOSE 80

# Script de inicio (opcional)
COPY appshell.sh /appshell.sh
ENTRYPOINT ["sh", "/appshell.sh"]
