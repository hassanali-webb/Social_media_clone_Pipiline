# Stage 1: Build
FROM node:18 AS builder

WORKDIR /app

COPY package*.json ./
RUN npm install --legacy-peer-deps

COPY . .

# Stage 2: Production
FROM node:18-slim

WORKDIR /app

COPY --from=builder /app /app

EXPOSE 3001

CMD ["npm", "start"]