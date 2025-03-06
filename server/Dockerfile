# For development stage
FROM node:20 AS dev

WORKDIR /user/src/ALX_Project

COPY server/package*.json ./
RUN npm install

COPY server/ ./

EXPOSE 5000

CMD ["npm", "run", "start-dev"]


# For production stage
FROM node:20 AS prod

WORKDIR /user/src/ALX_Project

COPY server/package*.json ./
RUN npm install --only=production

COPY server/ ./

EXPOSE 5000

CMD ["npm", "start"]
