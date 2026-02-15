FROM node:24 AS backend-builder
WORKDIR /app
COPY . .
RUN npm i
RUN npm run test

FROM node:24-slim
WORKDIR /app
COPY --from=backend-builder /app .
COPY .env.docker .env
EXPOSE 8080
CMD [ "npm", "start"]