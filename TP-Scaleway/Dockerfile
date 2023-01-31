FROM node:18-alpine

WORKDIR /app

COPY . /app
RUN rm -rf node_modules
RUN npm install --omit=dev

EXPOSE 3000
CMD ["node", "server.js"]