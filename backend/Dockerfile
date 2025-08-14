FROM node:21 AS backend-builder
WORKDIR /app
COPY package*.json ./
RUN npm install
RUN npm run test
COPY ..
FROM node:21-slim
WORKDIR /app
COPY --from=backend-builder /app .
COPY .env.docker .env
EXPOSE 5005
