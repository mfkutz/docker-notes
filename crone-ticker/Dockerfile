# /app /usr /lib
FROM node:19.2-alpine3.16

# cd app
WORKDIR /app

#Dest /app
COPY package.json ./

# Instalar las dependencias
RUN npm install

#Dest /app
COPY . .

#Realizar testing
RUN npm run test

#Eliminar archivos y directorios no necesarios en Produccion
RUN rm -rf tests && rm -rf node_modules

#Instalamos dependencias solo Produccion
RUN npm install --prod

#Comando run de la imagen
CMD ["node", "app.js"]