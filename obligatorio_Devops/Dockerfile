FROM node:22.19.0

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

# Agregamos check visual después del build
RUN npm run build 

RUN npm install -g serve

EXPOSE 3000

CMD ["serve", "-s", "dist", "-l", "3000"]
