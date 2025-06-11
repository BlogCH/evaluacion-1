# Imagen base
FROM node:18.17.1-alpine

# Crear directorio de trabajo
WORKDIR /usr/src/app

# Copiar los archivos de dependencias
COPY package*.json ./

# Instalar solo dependencias necesarias para producción
RUN npm install --production

# Copiar todo el código fuente al contenedor
COPY . .

# Exponer el puerto donde corre el backend
EXPOSE 3000

# Comando para iniciar la aplicación
CMD ["node", "index.js"]
