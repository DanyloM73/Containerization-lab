FROM node:21-alpine AS build
WORKDIR /project
COPY package*.json ./
RUN npm install
COPY . .

FROM node:21-alpine
WORKDIR /project
COPY --from=build /project .
EXPOSE 8080
CMD ["node", "index.js"]
