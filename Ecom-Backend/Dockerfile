FROM node:18-alpine

WORKDIR /app

RUN apk add --no-cache python3 make g++ sqlite

COPY .env .env
COPY package.json package-lock.json ./
RUN npm install

COPY . .

ENV NODE_OPTIONS=--max-old-space-size=2048

RUN npm run build

EXPOSE 1337

CMD ["npm", "run", "develop"]