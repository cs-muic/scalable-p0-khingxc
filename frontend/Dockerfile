FROM node:16 as builder
CMD mkdir /app
WORKDIR /app
COPY /scalable-ums-frontend/package.json /scalable-ums-frontend/yarn.lock ./
COPY /scalable-ums-frontend/ ./
RUN yarn 
RUN yarn build

FROM nginx:1.21-alpine
COPY --from=builder /app/dist /usr/share/nginx/html/