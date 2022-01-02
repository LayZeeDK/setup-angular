FROM node:14-alpine
ENV NPM_CONFIG_LOGLEVEL info
ENV NODE_ENV production
COPY package.json yarn.lock ./
RUN yarn install
