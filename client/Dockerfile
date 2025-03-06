# For development stage
FROM node:20 AS dev

WORKDIR /user/src/ALX_Project

COPY client/package*.json ./
RUN npm install

COPY client/ ./

EXPOSE 5173

CMD ["npm", "run", "start-dev"]


# For building stage
FROM node:20 AS build

WORKDIR /user/src/ALX_Project

COPY client/package*.json ./
RUN npm install

COPY client/ ./
RUN npm run build


# Final production image with Nginx
FROM nginx:alpine AS prod

COPY --from=build /user/src/ALX_Project/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
