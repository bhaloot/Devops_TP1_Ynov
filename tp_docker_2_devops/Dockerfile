FROM node:18-alpine

WORKDIR /app
ENV PORT 3000 

COPY . /app
RUN npm install --omit=dev

EXPOSE 3000
CMD ["node", "server.js"]