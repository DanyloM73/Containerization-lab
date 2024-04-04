FROM node:21-alpine AS build
WORKDIR /project
COPY package*.json ./
RUN npm install
COPY . .

FROM alpine
WORKDIR /project
COPY --from=build /project .
RUN apk add --update nodejs npm
EXPOSE 8080
CMD ["node", "index.js"]
