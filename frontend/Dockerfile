# FROM node:18-alpine AS build
FROM node:18-alpine AS frontend-builder
WORKDIR /app
COPY package*.json ./
RUN npm install --force
COPY . .


FROM node:21-slim
WORKDIR /app
COPY --from=frontend-builder /app .
COPY .env.docker .env.local
EXPOSE 5173
CMD ["npm", "run", "dev"]