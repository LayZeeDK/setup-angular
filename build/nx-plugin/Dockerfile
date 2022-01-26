FROM node:14-alpine
ENV NPM_CONFIG_LOGLEVEL info
ENV NODE_ENV production
COPY package.json yarn.lock ./
RUN YARN_CACHE_FOLDER=/dev/shm/yarn_cache yarn install --frozen-lockfile --non-interactive --production=false
