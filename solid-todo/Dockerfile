FROM node:23 AS builder
LABEL authors="Alkaiir"

RUN mkdir -p /app/
WORKDIR /app/

COPY ./package.json /app/
RUN npm install

COPY . /app/
RUN npm run build



FROM alpine:3.21

COPY --from=builder /app/dist /app/dist
