###
# Build stage
###
FROM node:12-alpine AS builder
WORKDIR /build

COPY package.json package-lock.json ./
RUN npm ci

COPY . .
RUN npm run build && rm -rf .next/cache

###
# Exec Stage
###
FROM node:12-alpine
WORKDIR /app

COPY package.json package-lock.json ./
RUN npm ci
COPY --from=builder /build/.next .next
COPY --from=builder /build/public public
RUN mkdir pages



CMD ["npm", "run", "start:production"]