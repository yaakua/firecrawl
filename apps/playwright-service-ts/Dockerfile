FROM node:18-slim

WORKDIR /usr/src/app
COPY package*.json ./
RUN npm config set registry https://registry.npmmirror.com
RUN npm install

COPY . .

# Install Playwright dependencies
RUN npx playwright install --with-deps

RUN npm run build

ARG PORT
ENV PORT=${PORT}

EXPOSE ${PORT}

CMD [ "npm", "start" ]
